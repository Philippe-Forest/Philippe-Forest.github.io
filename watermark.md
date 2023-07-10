
---

<p class="titletext">WATERMARKING DEEP CNN</p>

---

<p class="articletext"> Inspired by the use of classical watermarking techniques for the protection of property rights associated to multimedia contents, neural network watermarking is receiving increasing attention over the last several years. The first idea and implementation of such an algorithm was proposed <a href="https://arxiv.org/abs/1701.04082" class="linkedinlink">by Uchida et al. in 2017.</a> The idea was to embed a binary message inside of the weight repartition of a deep convolutional neural network. The message is embedded during the training phase and can be recovered by anyone having access to the weight distribution, as well as the secret key that was used in the process of embedding. It may not seem ideal that one need to have access to the weights in order to recover the message (what is called a "white-box approach", but <a href="https://arxiv.org/abs/1906.07745" class="linkedinlink">it has been showed</a> that the alternative (i.e recover the watermark only by querying the model) necessarily impact the model's accuracy. Here, I will implement Uchida's algorithm, highlight his weaknesses on the CIFAR 10 and MNIST datasets, and implement a more recent, robust algorithm, <a href="https://arxiv.org/abs/1910.14268" class="linkedinlink">RIGA</a>, that takes inspiration from GANs to make up for the shortcomings of Uchida. </p> 

---


---


<img src="images/duration.png?raw=true" alt="duration"/>

<p class="articletext">Other characteristics seem to follow a periodic trend. That's the case of "danceability" in Italy and France, which always jumps in summer. </p>

---

