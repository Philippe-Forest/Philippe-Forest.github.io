
---

<p class="titletext">WATERMARKING DEEP CNN</p>

---

<p class="articletext"> Inspired by the use of classical watermarking techniques for the protection of property rights associated to multimedia contents, neural network watermarking is receiving increasing attention over the last several years. The first idea and implementation of such an algorithm was proposed <a href="https://arxiv.org/abs/1701.04082" class="linkedinlink">by Uchida et al. in 2017.</a> The idea was to embed a binary message inside of the weight repartition of a deep convolutional neural network. The message is embedded during the training phase and can be recovered by anyone having access to the weight distribution, as well as the secret key that was used in the process of embedding. It may not seem ideal that one need to have access to the weights in order to recover the message (what is called a "white-box approach", but <a href="https://arxiv.org/abs/1906.07745" class="linkedinlink">it has been showed</a> that the alternative (i.e recover the watermark only by querying the model) necessarily impact the model's accuracy. Here, I will implement Uchida's algorithm, highlight his weaknesses on the CIFAR 10 and MNIST datasets, and implement a more recent, robust algorithm, <a href="https://arxiv.org/abs/1910.14268" class="linkedinlink">RIGA</a>, that takes inspiration from GANs to make up for the shortcomings of Uchida. </p> 

---

<p class="articletext">Uchida's method works as follows : once we have our n-bit binary message to embed, we select the convolutional layer of the CNN that we would like to watermark. Then, we generate a random matrix whose elements are drawn from the normal centered distribution. This matrix will be our secret key used to embed the secret message during the training process, and also used when deciphering the watermark. To do so, the Uchida's amazing idea is to add one term to the loss function</p>

---

<p class="articletext"> Lots of factor need to be taken into account when designing a watermarking scheme : among them is the robusntess criterion, which stipuulates that the watermark should be resistant to retraining of the model, pruning of the model, and overwriting (putting another watermark on the same model should not erase the previous one). Moreover, the watermarking scheme should not affect the model's accuracy. </p>

---


<img src="images/duration.png?raw=true" alt="duration"/>

<p class="articletext">Other characteristics seem to follow a periodic trend. That's the case of "danceability" in Italy and France, which always jumps in summer. </p>

---

