
---

<p class="titletext">Neuroscience</p>

---

<p class="articletext">Since the advances of functional Magnetic Resonance Imagery (fMRI), neuroscience have seen a surge of highly-advanced statistical techniques to try to uncover meaningful patterns in the functional data of the brain. The following project present a handful of these techniques applied to functional brain data in order to make predictions on the gender, as well as the musical affinity of 152 subjects.</p> 

---
<h1 class="articletext">Data and Dataset</h1>

<p class="articletext">First, we need to understand what is fMRI data and how it is structured. To summarize quickly, the data corresponds to measured variations of the oxygen level in the blood, which is correlated to the activity of specific brain regions. Therefore, the higher the fMRI signal is, the more active the corresponding region  is supposed to be. Inside of the scanner, one complete acquisition of the brain takes typically around 1s, so the temporal dimension has a low resolution. However, the space is discretized in small regions called "voxels" which are typically cubes of 1 mm, so the spatial dimension is fairly high resolution. Every voxel has an associated time serie that traces its evolution over time.</p>

<figure>
<img src="images/voxels.png?raw=true" alt="neuroscience" class="imgarticle"/>
<figcaption>Each brain volume is divided in small cubic regions called voxels.</figcaption>
</figure>

<p class="articletext">Now, we need to find a resting-state fMRI dataset. Resting-state fMRI data (data acquired when the subject is not performing any particular task) is a great way to analyze the natural connectivity patterns of individuals, and its study has revealed a number of networks which are consistently found in healthy subjects, and that represent specific patterns of synchronous activity. Furthermore, our dataset need to be pre-processed, as raw fMRI data needs to be standardized, detrended, motion corrected, smoothed, and a bunch of other steps that we will not cover in this article.

<figure>
<img src="images/neuro1.png?raw=true" alt="neuroscience" class="imgarticle"/>
<figcaption>The leibniz Mind-Brain-Body Dataset.</figcaption>
</figure>

<figure>
<img src="images/neuro1.png?raw=true" alt="neuroscience" class="imgarticle"/>
<figcaption>The leibniz Mind-Brain-Body Dataset.</figcaption>
</figure>

<figure>
<img src="images/neuro2.png?raw=true" alt="neuroscience" class="imgarticle"/>
<figcaption>Three different approaches to the problem.</figcaption>
</figure>

<figure>
<img src="images/neuro3.png?raw=true" alt="neuroscience" class="imgarticle"/>
<figcaption></figcaption>
</figure>

<figure>
<img src="images/neuro4.png?raw=true" alt="neuroscience" class="imgarticle"/>
<figcaption>Our pipeline.</figcaption>
</figure>

<figure>
<img src="images/neuro5.png?raw=true" alt="neuroscience" class="imgarticle"/>
<figcaption>Results regarding gender classification.</figcaption>
</figure>

<figure>
<img src="images/neuro6.png?raw=true" alt="neuroscience" class="imgarticle"/>
<figcaption>Results regarding musical sophistication classification.</figcaption>
</figure>
