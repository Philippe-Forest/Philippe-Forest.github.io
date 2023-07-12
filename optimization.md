
---

<p class="titletext">CNN EFFICIENCY OPTIMIZATION</p>

---

<p class="articletext">Given that where the latest LLM can have up to 100 trillions parameters, the task of optimizing the efficiency of deep neural networks is becoming more critical than ever. Some initiatives, such as the <a href="https://micronet-challenge.github.io/" class="linkedinlink">Micronet challenge</a> aim to "incentivize the development of efficient models and model compression techniques, as well as providing a forum for more rigorous benchmarking and comparison of existing techniques and for the study of combinations of approaches like sparsity, quantization, distillation, and neural architecture search." As part of a class during my final year at IMT Atlantique, we competed as teams of 2 in a smaller scale challenge, with the objective of attaining at least 90% accuracy on the CIFAR-10 dataset, with a model as efficient as possible. Me and my friend  <a href="https://www.linkedin.com/in/camillefrancoismartin/" class="linkedinlink">Camille François-Martin</a> teamed up and achieved second best overall, with an accuracy of 90.1% and a total of 112.000 parameters. This is how we did it</p>

---

<p class="articletext">The first part of the project was obviously chosing our base model architecture. We initially tried with the smallest version of ResNet that we could make, with only 10 convolutional layers, but even this was far too big for our purpose. Instead, we opted for a <a href="https://arxiv.org/abs/1608.06993" class="linkedinlink">Densenet</a> architecture. Densenets were introduced in 2016, and exploit the parameter redundancy of classical CNN by connecting the output of  every convolutional layer with every other layer of the same simension, thus reducing the need for parameter redundancy. The following image illustrate this principle :

<img src="images/densenet1.png?raw=true" alt="densenet" class="imgarticle"/>

<p class="articletext">Since the densenet architecture is highly configurable, the question is : how big (or small) should the initial model be? Of course, if we chose a bigger model, we always have the possibility to prune it later, but pruned models typicallt don't tend to perform as well as unpruned models with the same size.</p>

<img src="images/densenet1.png?raw=true" alt="densenet" class="imgarticle"/>

