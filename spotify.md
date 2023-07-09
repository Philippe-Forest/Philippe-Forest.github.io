
---

<p class="titletext">EVOLUTION OF MUSICAL TRENDS OVER THE YEARS WORLDWIDE</p>

---

<p class="articletext"> This project was realised along with 3 other students of IMT Atlantique : <a href="https://www.linkedin.com/in/martin-rouesn%C3%A9-81a489182/" class="linkedinlink">Martin Rouesné</a>, <a href="https://www.linkedin.com/in/camillefrancoismartin/" class="linkedinlink">Camille François-Martin</a> and <a href="https://www.linkedin.com/in/guyllian-gomez/" class="linkedinlink">Guyllian Gomez</a></p>

---

<p class="articletext"> We scrapped the top 100 Youtube charts since 2016 from over 60 countries and analyzed their main musical characteristics using Spotify's API. The API provides informations on various aspects such as the song's length, key, tempo and loudness, as well as pre-made metrics such as "danceability", "acousticnes" or "valence", which describes the felt sadness/hapiness of the song. The following diagram details the way our data was acquired and structured.</p>

---

<img src="images/flow1spotify.png?raw=true" alt="flow1" class="flow1"/>

---

<p class="articletext">Our objective was ultimately to create a model capable of predicting the popularity of any given song in various countries, and at different timescale. This model could serve as tool for market analysis, to guide the promotional campaign of upcoming artists. Before building the model, I was tasked with developping visualizations to help our team better grasp the dataset, and find interesting trends and correlations. </p>

---

<p class="articletext">We can perform a first basic analysis by checking the evolution of some characteristics over the years. For instance, the average song duration has increased over the year in some countries, like South Africa, but diminished in other, like in Japan, and has overall stayed the same worldwide</p>

<img src="images/duration.png?raw=true" alt="duration" class="duration"/>

<p class="articletext">Other characteristics seem to follow a periodic trend. That's the case of "danceability" in Italy and France, which always jumps in summer. </p>

<img src="images/danceability.png?raw=true" alt="danceability" class="danceability"/>
