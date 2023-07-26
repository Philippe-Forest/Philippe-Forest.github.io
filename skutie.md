---
---

<p class="titletextskutie" >✨❤️ 10 REASONS WHY I LOVE SKUTIE ❤️✨</p>

---

<p class="titletext" >NUMBER 1 : SHE IS THE CUTEST THING IN THE WORLD</p>
<p class="skutietext" >(And that's a fact)</p>

<div class="demo">
  <div class="perspective-container">
    <div class="card card1" id="image1"></div>
  </div>
</div>

---
<img class="keur" src="/background/keur.png" />
<p class="titletext" >NUMBER 2 : SHE IS VERY SMART</p>
<p class="skutietext" >(And she will go far in life)</p>

<div class="demo">
  <div class="perspective-container">
    <div class="card card2" id="image2"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 3 : SHE IS VERY SMALL</p>
<p class="skutietext" >(And I can lift her)</p>
<img class="keur" src="/background/oiseau.png" />
<div class="demo">
  <div class="perspective-container">
    
    <div class="card card3" id="image3"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 4 : ELLE EST BONNE SA MERE</p>
<p class="skutietext" >(Et elle twerk sur la piste)</p>

<div class="demo">
  <div class="perspective-container">
    <div class="card card4" id="image4"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 5 : SHE MAKES ME WANT TO BE THE BEST VERSION OF MYSELF</p>
<p class="skutietext" >(Even though I'm already the top G)</p>

<div class="demo">
  <div class="perspective-container">
    <div class="card card5" id="image5"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 6 : SHE CRIES FOR ANYTHING</p>
<p class="skutietext" >(Even flowers and little llama toys)</p>

<div class="demo">
  <div class="perspective-container">
    <div class="card card6" id="image6"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 7 : SHE MAKES BABY NOISES</p>
<p class="skutietext" >(And animal noises too)</p>

<div class="demo">
  <div class="perspective-container">
    <div class="card card7" id="image7"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 8 : SHE NEEDS CONSTANT ATTENTION AND CUDDLES</p>
<p class="skutietext" >(And she needs to get squized)</p>

<div class="demo">
  <div class="perspective-container">
    <div class="card card9" id="image9"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 9 : SHE IS ALWAYS THERE FOR ME</p>
<p class="skutietext" >(And she brightens my day when I'm sad)</p>

<div class="demo">
  <div class="perspective-container">
    <div class="card card8" id="image8"></div>
  </div>
</div>


---

<p class="titletext" >NUMBER 10 : SHE IS VERY KIND AND A GOOD HUMAN BEING</p>
<p class="skutietext" >(And that's why everyone likes her)</p>

<div class="demo">
  <div class="perspective-container">
    <div class="card card10" id="image10"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 11 : SHE IS THE LOVE OF MY LIFE</p>
<p class="skutietext" >(And I will marry her one day 💍)</p>

<div class="demo">
  <div class="perspective-container">
    <div class="card card11" id="image11"></div>
  </div>
</div>

---

<p class="titletextskutie" >THANKS FOR THE MEMORIES !</p>

<div id="stage">
      <div id="rotate">
        <div id="ring-1" class="ring"></div>
        <div id="ring-2" class="ring"></div>
        <div id="ring-3" class="ring"></div>
      </div>
    </div>

<style type="text/css">

      #stage {
        margin: 200px auto;
        width: 900px;
        height: 600px;
        /*
        
        Setting the perspective of the contents of the stage
        but not the stage itself
        
        */
        -webkit-perspective: 1600;
      }

      #rotate {
        margin: 0 auto;
        width: 900px;
        height: 600px;
        /* Ensure that we're in 3D space */
        -webkit-transform-style: preserve-3d;
        /*
        Make the whole set of rows use the x-axis spin animation
        for a duration of 7 seconds, running infinitely and linearly
        */
        -webkit-animation-name: x-spin;
        -webkit-animation-duration: 14s;
        -webkit-animation-iteration-count: infinite;
        -webkit-animation-timing-function: linear;
      }

      .ring {
        margin: 0 auto;
        height: 165px;
        width: 900px;
        -webkit-transform-style: preserve-3d;
        -webkit-animation-iteration-count: infinite;
        -webkit-animation-timing-function: linear;
      }
      
  

      .poster {
        position: absolute;
        left: 375px;
        height: 150px
        width: 100%;
        object-fit: cover;
        opacity: 0.85;
        color: rgba(0,0,0,0.9);
        -webkit-border-radius: 10px;
      }
      
      .poster > p {
        font-family: 'Georgia', serif;
        font-size: 36px;
        font-weight: bold;
        text-align: center;
        margin-top: 28px;
      }

      /*
      Set up each row to have a different animation duration
      and alternating y-axis rotation directions.
      */
      #ring-1 {
        -webkit-animation-name: y-spin;
        -webkit-animation-duration: 22s;
      }

      #ring-2 {
        -webkit-animation-name: back-y-spin;
        -webkit-animation-duration: 18s;
      }

      #ring-3 {
        -webkit-animation-name: y-spin;
        -webkit-animation-duration: 14s;
      }

      /*

      Here we define each of the three individual animations that
      we will be using to have our 3D rotation effect. The first
      animation will perform a full rotation on the x-axis, we'll
      use that on the whole set of objects. The second and third
      animations will perform a full rotation on the y-axis in
      opposite directions, alternating directions between rows.
    
      Note that you currently have to specify an intermediate step
      for rotations even when you are using individual transformation
      constructs.

      */
      @-webkit-keyframes x-spin {
        0%    { -webkit-transform: rotateX(0deg); }
        
        25%   { -webkit-transform: rotateX(20deg); }
  
        75%   { -webkit-transform: rotateX(-20deg); }
  
        100%  { -webkit-transform: rotateX(0deg); }
      }

      @-webkit-keyframes y-spin {
        0%    { -webkit-transform: rotateY(0deg); }
        50%   { -webkit-transform: rotateY(180deg); }
        100%  { -webkit-transform: rotateY(360deg); }
      }

      @-webkit-keyframes back-y-spin {
        0%    { -webkit-transform: rotateY(360deg); }
        50%   { -webkit-transform: rotateY(180deg); }
        100%  { -webkit-transform: rotateY(0deg); }
      }

  .keur { position: absolute; top: -1000px; width: 10% /* <- not relevant for the animation */ }
    </style>

  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js"> </script>
 <script type="text/javascript">

  const audio1 = new Audio('/skutie_pics/songs/1.ogg');
  const audio11 = new Audio('/skutie_pics/songs/iseethelight.mp3');
   audio11.loop = true;
   
  const image1 = document.getElementById('image1');
  image1.addEventListener('click', function() {
  // Play the song when the button is clicked
  audio1.play();
  audio11.play();
});

   const audio2 = new Audio('/skutie_pics/songs/2.ogg');
  const image2 = document.getElementById('image2');
  image2.addEventListener('click', function() {
  // Play the song when the button is clicked
  audio2.play();
    audio11.play();
});

   const audio3 = new Audio('/skutie_pics/songs/3.ogg');
  const image3 = document.getElementById('image3');
  image3.addEventListener('click', function() {
  // Play the song when the button is clicked
  audio3.play();
    audio11.play();
});

   const audio4 = new Audio('/skutie_pics/songs/4.ogg');
  const image4 = document.getElementById('image4');
  image4.addEventListener('click', function() {
  // Play the song when the button is clicked
  audio4.play();
    audio11.play();
});

   const audio5 = new Audio('/skutie_pics/songs/5.ogg');
  const image5 = document.getElementById('image5');
  image5.addEventListener('click', function() {
  // Play the song when the button is clicked
  audio5.play();
    audio11.play();
});

   const audio6 = new Audio('/skutie_pics/songs/7.ogg');
  const image6 = document.getElementById('image6');
  image6.addEventListener('click', function() {
  // Play the song when the button is clicked
  audio6.play();
    audio11.play();
});

   const audio7 = new Audio('/skutie_pics/songs/6.ogg');
  const image7 = document.getElementById('image7');
  image7.addEventListener('click', function() {
  // Play the song when the button is clicked
  audio7.play();
    audio11.play();
});

   const audio8 = new Audio('/skutie_pics/songs/8.ogg');
  const image8 = document.getElementById('image8');
  image8.addEventListener('click', function() {
  // Play the song when the button is clicked
  audio8.play();
    audio11.play();
});

   const audio9 = new Audio('/skutie_pics/songs/9.ogg');
  const image9 = document.getElementById('image9');
  image9.addEventListener('click', function() {
  // Play the song when the button is clicked
  audio9.play();
    audio11.play();
});

   const audio10 = new Audio('/skutie_pics/songs/10.ogg');
  const image10 = document.getElementById('image10');
  image10.addEventListener('click', function() {
  // Play the song when the button is clicked
  audio10.play();
    audio11.play();
});

   const audiobonus = new Audio('/skutie_pics/songs/happy.mp3');
  const image11 = document.getElementById('image11');
  image11.addEventListener('click', function() {
  // Play the song when the button is clicked
  audiobonus.play();
    audio11.play();
});

 
  const objectList = document.querySelectorAll('.card');
   
  objectList.forEach((object) => {
  object.onmousemove = handleMouseMove; })
  
 
  function handleMouseMove(event) {
  const height = window.innerHeight;
  const width = window.innerWidth;

  console.log(height);
  console.log(width);
        
  // Creates angles of (-20, -20) (left, bottom) and (20, 20) (right, top)
  const yAxisDegree = event.pageX / width * 40 - 20;
  const xAxisDegree = event.offsetY / height * -1 * 20 + 10;

  console.log(event.pageX);
  console.log(event.pageY);
        
  event.target.style.transform = `rotateY(${yAxisDegree}deg) rotateX(${xAxisDegree}deg)`;
  // Set the sheen position
  setSheenPosition(event.pageX / width, event.offsetY / width);
}

      function setSheenPosition(xRatio, yRatio) {
  // This creates a "distance" up to 400px each direction to offset the sheen
  const xOffset = 1 - (xRatio - 0.7) * 800;
  const yOffset = 1 - (yRatio - 0.4) * 800;
  event.target.style.setProperty('--sheenX', `${xOffset}px`)
  event.target.style.setProperty('--sheenY', `${yOffset}px`)
}

  const POSTERS_PER_ROW = 12;
  const RING_RADIUS = 300;

  function setup_posters (row, value)
  {
    var posterAngle = 360 / POSTERS_PER_ROW;
    for (var i = 0; i < POSTERS_PER_ROW; i ++) {
      var poster = document.createElement('div');
      poster.className = 'poster';
      // compute and assign the transform for this poster
      var transform = 'rotateY(' + (posterAngle * i) + 'deg) translateZ(' + RING_RADIUS + 'px)';
      poster.style.webkitTransform = transform;
      // setup the number to show inside the poster
      
      var content = poster.appendChild(document.createElement('img'));
      if (value == 1) {
      content.setAttribute('src', 'skutie_pics/'+i+'.jpg'); }
      else if (value == 2) {
        content.setAttribute('src', 'skutie_pics/'+i+'_.jpg'); }
      else if (value == 3) {
        content.setAttribute('src', 'skutie_pics/'+i+'__.jpg'); }
  
      content.setAttribute('alt', 'na');
      content.setAttribute('height', '150');
      content.setAttribute('width', '150');
      
    
      
      // add the poster to the row
      row.appendChild(poster);
    }

  }

  function init ()
  {
    setup_posters(document.getElementById('ring-1'), 1);
    setup_posters(document.getElementById('ring-2'), 2);
    setup_posters(document.getElementById('ring-3'), 3);
  }

  // call init once the document is fully loaded
  window.addEventListener('load', init, false);
  
$(function() {
    var img = $(".keur"),
        height = img.get(0).height,
        screenWidth = $(window).height(),
        duration = 10000;

    function animatePlane() {
        img.css("top", -height).animate({
            "top": screenWidth*10
        }, duration, animatePlane);
    }

    animatePlane();
});
    </script>

