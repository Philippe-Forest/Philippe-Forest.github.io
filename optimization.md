
---

<p class="titletext">CNN EFFICIENCY OPTIMIZATION</p>

---

<p class="articletext">At a time where the latest LLM can have up to 100 trillions parameters, the task of optimizing the efficiency of deep neural networks is becoming more critical than ever. Some initiatives, such as the <a href="https://micronet-challenge.github.io/" class="linkedinlink">Micronet challenge</a> aim to "incentivize the development of efficient models and model compression techniques, as well as providing a forum for more rigorous benchmarking and comparison of existing techniques and for the study of combinations of approaches like sparsity, quantization, distillation, and neural architecture search." As part of a class during my final year at IMT Atlantique, we competed as teams of 2 in a smaller scale challenge, with the objective of attaining at least 90% accuracy on the CIFAR-10 dataset, with a model as efficient as possible. Me and my friend  <a href="https://www.linkedin.com/in/camillefrancoismartin/" class="linkedinlink">Camille François-Martin</a> teamed up and achieved second best overall, with an accuracy of 90.1% and a total of 112.000 parameters. This is how we did it</p>

---

<p class="articletext">The first part of the project was obviously to chose our initial model architecture. We initially tried with the smallest version of ResNet that we 
