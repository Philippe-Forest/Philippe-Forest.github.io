---
---

<p class="titletext" >10 REASONS WHY I LOVE SKUTIE</p>

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

<p class="titletext" >NUMBER 5 : SHE IS VERY SMALL</p>
<p class="titletext" >(And I can lift her)</p>


<div class="demo">
  <div class="perspective-container">
    <div class="card" id = "bebzou3"></div>
  </div>
</div>

---

<p class="titletext" >NUMBER 6 : SHE IS VERY SMALL</p>
<p class="titletext" >(And I can lift her)</p>


<div class="demo">
  <div class="perspective-container">
    <div class="card" id = "bebzou3"></div>
  </div>
</div>

 <script type="text/javascript">

      
      const pictureElement = document.getElementById('bebzou');
      pictureElement.onmousemove = handleMouseMove;
     
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

      function setSheenPosition(xRatio, yRatio) {
  // This creates a "distance" up to 400px each direction to offset the sheen
  const xOffset = 1 - (xRatio - 0.5) * 800;
  const yOffset = 1 - (yRatio - 0.5) * 800;
  event.target.style.setProperty('--sheenX', `${xOffset}px`)
  event.target.style.setProperty('--sheenY', `${yOffset}px`)
}

    </script>
