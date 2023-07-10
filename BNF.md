
---

<p class="titletext">MOVIE CREDIT EXTRACTOR</p>

---

<p class="articletext">The French National Library (BnF) was founded in 1537 by François 1er. It's mission is to collect, preserve, enrich and communicate the national documentary heritage. On top of its massive collection of books, it also contains 390 000 video documents, many of which are in the process of being numerized in order to make them accessible by the public on <a href="https://gallica.bnf.fr/accueil/fr/content/accueil-fr" class="linkedinlink">Gallica</a>. However, the process of documenting every movie with the appropriate metadata is very time-consuming, and performed by the same specialized personnel in charge of the numerization, who (surprisingly enough) told me that they do not appreciate spending their time filling out charts with the name of the second assistant cameraman. As part as my 4 month internship, I was tasked by the library to produce a proof of concept algorithm capable of :<br><br>
1) Automatically detecting the beginning and the end of the credits in a movie<br>
2) Performing OCR to extract all the relevant information<br>
3) Structure said information in a standardized way, so that it would be ready for querying on Gallica.</p> 

---

<p class="articletext">Segmenting the movie credits was the first part of the job. My first idea was to first build a model capable of detecting whether or not a specific frame was part of a credit scene or not. Then, I would just have to select a frame from the movie every so and so, and decide that the credits have begun to roll when a few consecutive frames were identified as belonging to a credit scene. After a little bit of research, I found pre-trained models that could fullfill this purpose, such as <a href="https://github.com/parallel-places/closing-credits-recognizer" class="linkedinlink">this one</a> or <a href="https://github.com/nielstenboom/recurring-content-detector" class="linkedinlink">that one</a>. After a few test on actual videos from the BnF collection, I noticed that such models were pretty efficient to detect the credit sequences when they looked like black screen with white next appearing on it, but failed completely whenever the credit scene was anything else. As it turns out, many of the BnF's movie have ending sequences that completely differs from this stereotypical design. See the following picture for an idea of what I had to deal with :</p>

<img src="images/uchida_mnist.png?raw=true" alt="uchida watermark mnist"/>

  
---

<p class="articletext">Uchida's method works as follows : once we have our n-bit binary message to embed, we select the convolutional layer of the CNN that we would like to watermark. Then, we generate a random matrix whose elements are drawn from the normal centered distribution. This matrix will be our secret key used to embed the secret message during the training process, and will also be used in order to recover the message. To do so, Uchida's amazing idea is to add one more term to the loss function, that will act like a regularizer (think of a weight decay term, but instead of penalizing big weights, it penalizes weights distributions that don't "match" the secret message we want to embed). Of course, by now, the burning question is : how do we force a weight distribution to "match" a secret message? and what role does the secret key has to play in this? The answer is pretty simple : n linear combinations involving both the weight distribution and the secret key elements are generated. Each of these linear combinations is supposed to add up to one of the message bit at the end of the training process. Therefore, the neural network is incited to modify its weights such that : <br><br>
1) It acquires a good accuracy (that's the role of the first part of the loss function) <br>
2) The weights involved in each of the n linear combinations are set to values such that the combinations produce all of the message bits, in a given order.<br><br>
In practice, the way we achieve this is through a cross-entropy loss function, since this problem is analoguous to a binary classification, with the labels being either 0 or 1 (the bits of the message) </p>

---


---

<p class="articletext">RIGA adresses the issue of weighth distribution by cleverly drawing inspiration from GANs. To simplify a little bit, RIGA ditches the linear combinations that we mentioned earlier, and replaces them with a multi-layer perceptron whose job is to take as inputs the current model's weight, and map them to the appropriate message values. This update is not very surprising since, as we mentioned, the initial problem was identical to a classification task using cross-entropy. Moreover, by replacing the rigid linear combinations with a flexible neural network, we can now embed not only binary messages, but pretty much anything we want! However, the real kicker added by RIGA is the introduction of yet another neural network, whose job is to analyse the current model's weights, and predict whether or not these weights have been tampered with. The model in charge of mapping the weights to the message then receives a penality if the weight has been deemed suspicious by the second neural network. This is of course very similar to the way GANs work, with a generator trying to produce an element belonging to a specific distribution (The distribution of all possible non-watermarked weights), and a discriminator tasked to identify the outliers. To make this work, we first need to generate a bunch of non-watermarked weights so our discriminator can have a reference to decide whether or not a new weight distribution is watermarked or not. The following diagram is a brief summary of the whole scheme, where wnon stands for non-watermarked weights, m is the message to embed and Ftgt is the target model for our watermark.</p>


<img src="images/schemawm.png?raw=true" alt="schemawm"/>

---

<p class="articletext">Not only is this method supposed to hide the watermark seemlessly, but it is also said in the original article that it is robust to pruning and overwriting. Let's try it out! Once again, the code is available in <a href="https://colab.research.google.com/drive/1DUnfiuhqV2FR3V9jndP47zLTmsFhyNh2" class="linkedinlink">the notebook</a>.</p>

<p class="articletext">This algorithm implementation was definitely harder than the previous one, mainly due to the multiple neural networks interacting with each other and the three chained backpropagations required to update the weights. First, let's look at the weight distribution in the embedded layer :</p>

<img src="images/riga_mnist.png?raw=true" alt="riga mnist"/>

<p class="articletext">Much better! After training was complete, I pruned progressively more and more of the network and kept track of both the accuracy and the watermark recovery rate at each step. Here are the results for both Uchida and RIGA :</p>

<img src="images/cifar_riga_pruning.png?raw=true" alt="pruning with riga"/>
<img src="images/cifar_uchida_pruning.png?raw=true" alt="pruning with uchida"/>

<p class="articletext">In both cases, the watermark only begins to degrade long after the accuracy is completely destroyed, so we can safely say that both methods are resistant to pruning, at least on this small test case. Now, for the really interesting part, I wanted to see how both models would react to an overwriting attack. To do so, I have progressively retrained the models by adding a new watermark at the same time, and kept track of both the old watermark recovery rate (in red) and the new watermark recovery rate as it is slowly added to the model. (in blue). Here are the results for both RIGA and Uchida methods :</p>

<img src="images/overwriting_mnist_riga.png?raw=true" alt="overwriting with riga"/>
<img src="images/overwriting_mnist_uchida.png?raw=true" alt="overwriting with uchida"/>

<p class="articletext">The difference here is obvious : with Uchida's algorithm, the more epochs we retrain with a new watermark, the more the previous watermark begins to degrade. However, with RIGA, the old matermark remains entirely recoverable even after a new watermark has been added to the weights. Therefore, RIGA adds a lot more robustness as well as being virtually impossible to detect from weight distribution alone. <br><br>
Other algorithms I have not covered are designed so that the watermark can be introduced in the model during the process of fine-tuning, or even during distillation. The field of neural network watermarking is still relatively new and expanding, so there is no doubt that more of these clever algorithms will pop up in the years to come!</p>
