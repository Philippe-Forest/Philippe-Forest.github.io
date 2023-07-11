
---

<p class="titletext">MOVIE CREDIT EXTRACTOR</p>

---

<p class="articletext">The French National Library (BnF) was founded in 1537 by François 1er. It's mission is to collect, preserve, enrich and communicate the national documentary heritage. On top of its massive collection of books, it also contains 390 000 video documents, many of which are in the process of being numerized in order to make them accessible by the public on <a href="https://gallica.bnf.fr/accueil/fr/content/accueil-fr" class="linkedinlink">Gallica</a>. However, the process of documenting every movie with the appropriate metadata is very time-consuming, and performed by the same specialized personnel in charge of the numerization, who (surprisingly enough) told me that they do not appreciate spending their time filling out charts with the name of the second assistant cameraman. As part as my 4 month internship, I was tasked by the library to produce a proof of concept algorithm capable of :<br><br>
1) Automatically detecting the beginning and the end of the credits in a movie<br>
2) Performing OCR to extract all the relevant information<br>
3) Structure said information in a standardized way, so that it would be ready for querying on Gallica.</p> 

---

<p class="articletext">Segmenting the movie credits was the first part of the job. My first idea was to first build a model capable of detecting whether or not a specific frame was part of a credit scene or not. Then, I would just have to select a frame from the movie every so and so, and decide that the credits have begun to roll when a few consecutive frames were identified as belonging to a credit scene. After a little bit of research, I found pre-trained models that could fullfill this purpose, such as <a href="https://github.com/parallel-places/closing-credits-recognizer" class="linkedinlink">this one</a> or <a href="https://github.com/nielstenboom/recurring-content-detector" class="linkedinlink">that one</a>. After a few test on actual videos from the BnF collection, I noticed that such models were pretty efficient to detect the credit sequences when they looked like black screen with white next appearing on it, but failed completely whenever the credit scene was anything else. As it turns out, many of the BnF's movie have ending sequences that completely differs from this stereotypical design. See the following picture for an idea of what I had to deal with :</p>

<img src="images/creditszazie.png?raw=true" alt="credits sample"/>

<p class="articletext">The next step was to retrain/finetune an existing model using more diverse and colorful credit sequences, so I spent some time building a collection of screenshots from the most original pieces I could find in the BnF database. The new model performed slightly better on colorful samples, but was still overall pretty unreliable. Inspired by a different idea presented on <a href="https://github.com/yanglinz/detect-show-episode-credits" class="linkedinlink">this project</a>, I decided to switch strategies : instead of identifying whole frames as being either "credit" or "non credit", it could be interesting to instead simply detect the presence of text on the screen, regardless of everything else. After a little empirical experimentation, I added a moving average of 10 seconds in order to rule out the occasional shots mid-movie that showed a sign on the road, or an eventual text interlude (think old chaplin movie), and bingo! Our new method correctly identified both beginning and ending credits with more than 95% accuracy! One last addition consisted in detecting if the movie had subtitles or not, and ignoring them if that was the case. It was now time to actually extract the information from the movie.</p>

---

<p class="articletext">This part of the process was pretty straightforward : I experimented with many different OCR algorithms available, some open source and other not, among which : EasyOCR, ABBY Finereader, pyTesseract, Google OCR and CRAFT (which I also used for text detection in the previous part). The absolute unmatched winner emerged as Google OCR, with results that quite honestly almost matched human performance. Given the difficulty posed by some of the images (see screenshot above if you don't believe me), we decided to continue with this solution. I performed a brief estimation of the pricing and estimated that we could process the entirety of the video collection for less than a hundred euros. It was now time for the final step, the data processing, formatting and structuring. </p>

---

<p class="articletext">Though it might not seem that way at first, this part of the process is actually by far the hardest. Think about it : some credits sequences roll from bottom to top, some other just jump from screen to screen, some have the name displayed before the corresponding role and some have the opposite. Some have one column, two column, or even three columns of text. A lot of time, the format of the display changes during the same credit sequence! Let's see two examples from the BnF to try to identify all the things our algorithms should do correctly :</p>

<img src="images/credits1.png?raw=true" alt="pruning with riga"/>
<img src="images/credits2.png?raw=true" alt="pruning with uchida"/>

