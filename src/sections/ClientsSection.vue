<template>
  <div class="clientSection container text-center my-3">
    <h1 class="sectionTitle fw-bold my-5">Nos Clients</h1>
    <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="carousel">
      <div class="carousel-indicators mt-1">
        <button class="indicator active" type="button" data-bs-target="#carouselExampleIndicators"  data-bs-slide-to="0" aria-current="true"></button>
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
          <img src="@/assets/clients/client-3.png" alt="">
          <img src="@/assets/clients/client-4.png" alt="">
          <img src="@/assets/clients/client-9.svg" alt="">
        </div>
      </div>
    </div>
  </div>
</template>
<style >
.clientSection {
  img {
    height: 50px;
    width: 50px;
    margin-right: 5%;
    /* opacity: 0.5; */
    /* filter: grayscale(100%); */
    transition: ease-in-out 0.3s;
    &:hover{
      /* filter: none;
      opacity: 1; */
      height: 100px;
      width: 20%;
    }
  }

  .carousel-indicators{
  border-top: none;
  }
  .indicator {
    border: 0 !important;
    border-radius: 0.375rem;
    background: #c0bcbc !important;
    height: 5px !important;
    &.active{
      background: var(--main-orange-color)  !important;
    }
  }

  .carousel-item {
    height: 100px;
  }
}
@media (min-width: 768px) {
  .clientSection  img {
    height: 90px;
    width: 120px;
  }
  .carousel-item {
    height: 150px !important;
  }
  .indicator {
    height: 7px !important;
  }
}


</style>