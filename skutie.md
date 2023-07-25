---
---

<p class="titletext" >✨❤️ 10 REASONS WHY I LOVE SKUTIE ❤️✨</p>

---

<p class="titletext" >NUMBER 1 : SHE IS THE CUTEST THING IN THE WORLD</p>
<p class="titletext" >(And that's a fact)</p>


<div class="demo">
  <div class="perspective-container">
    <div class="card" id = "bebzou"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 2 : SHE IS VERY SMART</p>
<p class="titletext" >(And she will go far in life)</p>


<div class="demo">
  <div class="perspective-container">
    <div class="card" id = "bebzou2"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 3 : SHE IS VERY SMALL</p>
<p class="titletext" >(And I can lift her)</p>


<div class="demo">
  <div class="perspective-container">
    <div class="card" id = "bebzou3"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 4 : ELLE EST BONNE SA MERE</p>
<p class="titletext" >(Et elle twerk sur la piste)</p>


<div class="demo">
  <div class="perspective-container">
    <div class="card" id = "bebzou3"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 5 : SHE MAKES ME WANT TO BE THE BEST VERSION OF MYSELF</p>
<p class="titletext" >(Even though I'm already the top G)</p>


<div class="demo">
  <div class="perspective-container">
    <div class="card" id = "bebzou3"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 6 : SHE CRIES FOR ANYTHING</p>
<p class="titletext" >(Even flowers and little llama toys)</p>


<div class="demo">
  <div class="perspective-container">
    <div class="card" id = "bebzou3"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 7 : SHE MAKES BABY NOISES</p>
<p class="titletext" >(And animal noises too)</p>


<div class="demo">
  <div class="perspective-container">
    <div class="card" id = "bebzou3"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 8 : SHE IS ALWAYS THERE FOR ME</p>
<p class="titletext" >(And she brightens my day when I'm sad)</p>


<div class="demo">
  <div class="perspective-container">
    <div class="card" id = "bebzou3"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 9 : SHE NEEDS CONSTANT ATTENTION AND CUDDLES</p>
<p class="titletext" >(And she needs to get squized)</p>


<div class="demo">
  <div class="perspective-container">
    <div class="card" id = "bebzou3"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 10 : SHE IS VERY KIND AND A GOOD HUMAN BEING</p>
<p class="titletext" >(And that's why everyone likes her)</p>


<div class="demo">
  <div class="perspective-container">
    <div class="card" id = "bebzouu"></div>
  </div>
</div>

 <script type="text/javascript">

      const objectList = document.querySelectorAll('.c');
      objectList.forEach((object) => {
      object.onmousemove = handleMouseMove; })
   
      const pictureElement = document.getElementById('bebzou');
      pictureElement.onmousemove = handleMouseMove;
      const pictureElementt = document.getElementById('bebzouu');
      pictureElementt.onmousemove = handleMouseMovee;
     
      function handleMouseMove(event) {
  const height = window.innerHeight;
  const width = window.innerWidth;
  // Creates angles of (-20, -20) (left, bottom) and (20, 20) (right, top)
  const yAxisDegree = event.pageX / width * 40 - 20;
  const xAxisDegree = event.pageY / height * -1 * 40 + 20;
  event.target.style.transform = `rotateY(${yAxisDegree}deg) rotateX(${xAxisDegree}deg)`;
  // Set the sheen position
  setSheenPosition(event.pageX / width, event.pageY / width);
}

     function handleMouseMovee(event) {
  const height = window.innerHeight;
  const width = window.innerWidth;
  // Creates angles of (-20, -20) (left, bottom) and (20, 20) (right, top)
  const yAxisDegree = event.pageX / width * 40 - 20;
  const xAxisDegree = event.pageY / height * -1 * 40 + 20;
  event.target.style.transform = `rotateY(${yAxisDegree}deg) rotateX(${xAxisDegree}deg)`;
  // Set the sheen position
  setSheenPosition(event.pageX / width, event.pageY / width);
}

      function setSheenPosition(xRatio, yRatio) {
  // This creates a "distance" up to 400px each direction to offset the sheen
  const xOffset = 1 - (xRatio - 0.5) * 800;
  const yOffset = 1 - (yRatio - 0.5) * 800;
  event.target.style.setProperty('--sheenX', `${xOffset}px`)
  event.target.style.setProperty('--sheenY', `${yOffset}px`)
}

    </script>
