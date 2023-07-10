
---

<p class="titletext">EVOLUTION OF MUSICAL TRENDS OVER THE YEARS WORLDWIDE</p>

---

<p class="articletext"> This project was realised along with 3 other students of IMT Atlantique : <a href="https://www.linkedin.com/in/martin-rouesn%C3%A9-81a489182/" class="linkedinlink">Martin Rouesné</a>, <a href="https://www.linkedin.com/in/camillefrancoismartin/" class="linkedinlink">Camille François-Martin</a> and <a href="https://www.linkedin.com/in/guyllian-gomez/" class="linkedinlink">Guyllian Gomez</a></p>

---

<p class="articletext"> We scrapped the top 100 weekly Youtube charts since 2016 from over 60 countries and analyzed their main musical characteristics using Spotify's API. The API provides informations on various aspects such as the song's length, key, tempo and loudness, as well as pre-made metrics such as "danceability", "acousticnes" or "valence", which describes the felt sadness/hapiness of the song. The following diagram details the way our data was acquired and structured.</p>

---

<img src="images/flow1spotify.png?raw=true" alt="flow1" class="flow1"/>

---

<p class="articletext">Our objective was ultimately to create a model capable of predicting the popularity of any given song in various countries, and at different timescale. This model could serve as tool for market analysis, to guide the promotional campaign of upcoming artists. Before building the model, I was tasked with developping visualizations to help our team better grasp the dataset, and find interesting trends and correlations. </p>

---

<p class="articletext">We can perform a first basic analysis by checking the evolution of some characteristics over the years. For instance, the average song duration has increased over the year in some countries, like South Africa, but diminished in other, like in Japan, and has overall stayed the same worldwide</p>

<img src="images/duration.png?raw=true" alt="duration" class="duration"/>

<p class="articletext">Other characteristics seem to follow a periodic trend. That's the case of "danceability" in Italy and France, which always jumps in summer. </p>

<img src="images/danceability.png?raw=true" alt="danceability" class="danceability"/>

<p class="articletext">For a more thorough inspection, we can calculate the correlation between each characteristic and the average performance of a song. We can also split the results by country and by week for maximum specificity. This gives us some nice insight that I chose to display in a circular fashion to account for the periodic nature of musical trends. This powerful way of vizualising gives us immediately the broad trend over the year for a specific country. For instance, in Italy, There seem to be a massive popularity "of high-valence" (aka happy) songs between the weeks 25 to 24, which corresponds roughly to summer. </p>

<img src="images/wheel_Italy.png?raw=true" alt="wheel_Italy" class="danceability"/>

<p class="articletext">Though this could be easily expected, there are still huge differences in the correlations across various countries. For instance, the Nicaraguan wheel looks widely different from the Italian one : </p>

<img src="images/wheel_Nicaragua.png?raw=true" alt="wheel_Italy"/>

<p class="articletext">Just for fun, let's plot every country at the same time and animate based on the current week of the year</p>

<img src="images/featuresovertheyear.gif?raw=true" alt="wheel_Italy"/>

<p class="articletext">Even though this last animation highlights both a great diversity across countries and some variability over time, we need to keep in mind that the correlations showed here are rather weak on average, as most of them are below 0,2. This is a hint that it would be hard to produce a predictive model based solely on these explanatory variables, and indeed, our model turned out to be rather mediocre for popularity prediction.</p>

---

<p class="articletext">Another interesting visualization we can make is performing PCA on the 10 explanatory variables, and plot each countries in the resulting latent space. This allows us to see immediately which countries are "close" to each other and which one are "far away" in their music. From this first plot, it appears that Dominican Republic, Indonesia and Japan have very diverse musical tastes.</p>

<img src="images/PCAcountry.png?raw=true" alt="PCA country"/>

<p class="articletext">Let's color the points by continent :</p>

<img src="images/PCAcontinents.png?raw=true" alt="PCA country"/>

<p class="articletext">Interestingly, it seems like Europe has overall uniform tastes, South America has very similar tastes, which can easily be explained by the massive popularity of Raeggeton in the whole continent. Asia seems to have the most diverse musical culture overall. </p>

---
