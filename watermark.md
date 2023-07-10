
---

<p class="titletext">WATERMARKING OF DEEP CNN</p>

---

<p class="articletext"> Inspired by the use of classical watermarking techniques for the protection of property rights associated to multimedia contents, neural network watermarking is receiving increasing attention over the last several years. Lots of factor need to be taken into account when designing a watermarking scheme : among them is the robusntess criterion, which stipulates that the watermark should be resistant to retraining of the model, pruning of the model, and overwriting (putting another watermark on the same model should not erase the previous one). Moreover, the watermarking scheme should not affect the model's accuracy. The first idea and implementation of such an algorithm was proposed <a href="https://arxiv.org/abs/1701.04082" class="linkedinlink">by Uchida et al. in 2017.</a> The idea was to embed a binary message inside of the weight repartition of a deep convolutional neural network. The message is embedded during the training phase and can be recovered by anyone having access to the weight distribution, as well as the secret key that was used in the process of embedding. It may not seem ideal that one need to have access to the weights in order to recover the message (what is called a "white-box approach", but <a href="https://arxiv.org/abs/1906.07745" class="linkedinlink">it has been showed</a> that the alternative (i.e recover the watermark only by querying the model) necessarily impact the model's accuracy. Here, I will implement Uchida's algorithm, highlight his weaknesses on the CIFAR 10 and MNIST datasets, and implement a more recent, robust algorithm, <a href="https://arxiv.org/abs/1910.14268" class="linkedinlink">RIGA</a>, that takes inspiration from GANs to make up for the shortcomings of Uchida. The notebook with all the codes is available <a href="https://colab.research.google.com/drive/1DUnfiuhqV2FR3V9jndP47zLTmsFhyNh2" class="linkedinlink">here</a> </p> 

---

<p class="articletext">Uchida's method works as follows : once we have our n-bit binary message to embed, we select the convolutional layer of the CNN that we would like to watermark. Then, we generate a random matrix whose elements are drawn from the normal centered distribution. This matrix will be our secret key used to embed the secret message during the training process, and will also be used in order to recover the message. To do so, Uchida's amazing idea is to add one more term to the loss function, that will act like a regularizer (think of a weight decay term, but instead of penalizing big weights, it penalizes weights distributions that don't "match" the secret message we want to embed). Of course, by now, the burning question is : how do we force a weight distribution to "match" a secret message? and what role does the secret key has to play in this? The answer is pretty simple : n linear combinations involving both the weight distribution and the secret key elements are generated. Each of these linear combinations is supposed to correspond to one of the message bit at the end of the training process. Therefore, the neural network is incited to modify its weights such that : <br>
1) It acquires a good accuracy (that's the role of the first part of the loss function) <br>
2) The weights involved in the n linear combinations are set to values such that the various combinations produce all of the message bits, in a precise order.<br>
In practice, the way we achieve this is through a cross-entropy loss function, since this problem is analoguous to a binary classification, with the labels being either 0 or 1 (the bits of the message) </p>

---

<p class="articletext">The implementation of this algorithm is pretty straightworfard, and can be found in <a href="https://colab.research.google.com/drive/1DUnfiuhqV2FR3V9jndP47zLTmsFhyNh2" class="linkedinlink">the notebook.</a> I implemented it on the CIFAR-10 and MNIST datasets, using a slighty improved version of <a href="https://en.wikipedia.org/wiki/LeNet" class="linkedinlink">LeNet.</a> I noticed a 2% decrease in accuracy on the CIFAR dataset when applying the watermarking, but I was able to successfully embed and retreive the message with a 100% recovery rate. However, upon looking at the weight distribution of the embedded layer, it is obvious that the repartition had been tampered with :</p>

<img src="images/no_wm_mnist.png?raw=true" alt="nowm"/>
<img src="images/uchida_mnist.png?raw=true" alt="nowm"/>

<p class="articletext">This breaks the principle of security, which states that the matermark should be inpossible to detect. It is one of the biggest flaws with Uchida's algorithm. Now let's try to implement RIGA in order to see if it fares better .</p>

---

<p class="articletext">RIGA adress the issue of weighth distribution by cleverly drawing inspiration from GANs. To simplify a little bit, RIGA ditches the linear combinations that we mentioned earlier, and replaces them with a multi-layer perceptron whose job is to take as inputs the current model's weight, and map them to the appropriate message bit. This update is not very surprising since, as we mentioned, the problem is identical to a classification task. However, by replacing the rigid linear combinations with a flexible neural network, we can now embed not only binary messages, but pretty much anything we want! The real kicker added by RIGA is the introduction of yet another neural network, whose job is to analyse the current model's weights, and predict wheter or not these weights have been tampered with. The model in charge </p>

---


<img src="images/duration.png?raw=true" alt="duration"/>

<p class="articletext">Other characteristics seem to follow a periodic trend. That's the case of "danceability" in Italy and France, which always jumps in summer. </p>

---

