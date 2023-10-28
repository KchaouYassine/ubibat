<template>
  <div class="container my-3" data-aos="fade-up">
    <h1 class="fw-bold my-2">Ils nous font confiences</h1>
    <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="carousel">
      <div class="carousel-indicators mt-3">
        <button class="indicator active" type="button" data-bs-target="#carouselExampleIndicators"  data-bs-slide-to="0" aria-current="true" aria-label="Slide 1"></button>
        <button class="indicator" type="button" data-bs-target="#carouselExampleIndicators"  data-bs-slide-to="1" aria-label="Slide 2"></button>
      </div>
      <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="@/assets/clients/client-1.png" alt="">
      <img src="@/assets/clients/client-2.png" alt="">
      <img src="@/assets/clients/client-3.png" alt="">
      <img src="@/assets/clients/client-4.png" alt="">
    </div>
    <div class="carousel-item">
      <img src="@/assets/clients/client-5.png" alt="">
      <img src="@/assets/clients/client-6.png" alt="">
      <img src="@/assets/clients/client-7.png" alt="">
      <img src="@/assets/clients/client-8.png" alt="">
    </div>

  </div>

</div>
  </div>
</template>
<style scoped>
img {
  width: 15%;
  margin-right: 5%;
  opacity: 0.5;
  transition: ease-in-out 0.3s;
  filter: grayscale(100%);
}
img:hover {
  filter: none;
  opacity: 1;
}
.carousel-indicators{
  border-top: none;
}
.indicator {
  background: #5c5959 !important;
  height: 0.5px !important
}
.indicator.active{
  background: #6d0101  !important;
}
.carousel-item {
  height: 150px;
}
</style>