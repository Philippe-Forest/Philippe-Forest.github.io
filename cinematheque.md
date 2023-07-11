
---

<p class="titletext">AUTOMATIZED VIDEO DESCRIPTION</p>

---

<p class="articletext">The "Cinémathèque de Bretagnes" possess a collection of more than 30000 movies, half of which are amateur and half of which are professional. After their numerization, they are uploaded on the <a href="https://www.cinematheque-bretagne.bzh/" class="imgarticle">Cinémathèque website</a>, along with a short summary and a few keywords descriptors : </p> 

<img src="images/resumecinematheque.png?raw=true" alt="resumecinematheque" class="imgarticle"/>
<img src="images/keywordscinematheque.png?raw=true" alt="keywordscinematheque" class="imgarticle"/>

<p class="articletext">If you can speak French, you will notice that a lot of the words above are highly specific and sometimes impossible to recover from the footage alone, such as the name of the city for instance. During our first meeting with the client, we made it clear that we couldn't expect our algorithm to provide such detailled descriptions, but we could expect to transcribe simple descriptions of the scene succession as they are happening on the screen. As for what the final product should look like, we agreed that a simple notebook with detailed instructions was enough, as the clients had already a little bit of experience with running jupyter notebooks.</p>

---

<p class="articletext">The first part of our work consisted in retrieving the video direclty from the website, as we didn't have access to the full database. With the client's agreement, we set up a scrapping mechanism that could recover every video from the website, by providing the corresponding id. We then used the library <a href="https://www.scenedetect.com/" class="imgarticle">pyscenedetect</a> to automatically segment the video into different scenes, by looking for sudden jumps in pixel values on every frame. Once this was done, we began experimenting with various pre-trained models to see which architecture yielded the best results on our dataset. Eventually, it is <a href="https://github.com/salesforce/BLIP" class="imgarticle">BLIP</a> that took the cake. It performed remarkably well in various context and was overall relatively consistent. The main issue was the vagueness of its description, but given the current state of the art at the time, we did not believe we could make a significant improvement in this area. Fine-tuning the model on keywords and footage from the Cinémathèque was out of the question given our limited time and resources, so we decided to use the model as is. After generating one sentence for every scene, we saved them in a dictionarry along with the timestamp associated to the scene. (The clients asked to use the timestamps displayed on the video as reference, instead of the time since the beginning of the video, so we extracted them using OpenCV) </p>

<img src="images/12.png?raw=true" alt="timestamp example" class="imgarticle"/>
<p class="articletext">An example of timestamp on a video.</p>

---

<p class="articletext">Now that we had our description </p>

---


<p class="articletext">evaluation, scrapping, audio analysis, timestamps</p>

<img src="images/poster.png?raw=true" alt="poster cinematheque" class="imgarticle"/>

---


