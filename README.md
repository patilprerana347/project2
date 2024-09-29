# project2<html>
<head>
<body>

<div class="slider">
  <div class="slides">
    <img src="image1.jpg" alt="Image 1">
    <img src="images2.jpg" alt="Image 2">
    <img src="sdf.jpg" alt="Image 3">
  </div>
  <button class="prev">Prev</button>
  <button class="next">Next</button>
</div>
<style >

.slider {
  position: relative;
  width: 600px;
  height: 400px;
}

.slides {
  position: absolute
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.slides img {
  width: 100%;
  height: 100%;
  display: none;
}

.slides img.active {
  display: block;
}

.prev, .next {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  cursor: pointer;
}

.prev {
  left: 0;
}

.next {
  right: 0;
}
</style>
<script>

const slides = document.querySelectorAll('.slides img');
let currentSlide = 0;



document.querySelector('.prev').addEventListener('click', () => {
  currentSlide = (currentSlide - 1 + slides.length) % slides.length;
  updateSlide();
});

document.querySelector('.next').addEventListener('click', () => {
  currentSlide = (currentSlide + 1) % slides.length;
  updateSlide();
});

function updateSlide() {
  slides.forEach((slide) => slide.classList.remove('active'));
  slides[currentSlide].classList.add('active');
}

updateSlide();

</script>
</body>
</
