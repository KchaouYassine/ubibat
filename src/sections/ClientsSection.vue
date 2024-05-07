<template>
  <div class="clientSection container text-center my-3">
    <h1 class="sectionTitle fw-bold my-5">Nos Clients</h1>
    <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="carousel">
      <div class="d-none carousel-indicators mt-1">
        <button class="indicator active" type="button" data-bs-target="#carouselExampleIndicators"  data-bs-slide-to="0" aria-current="true"></button>
        <button class="indicator" type="button" data-bs-target="#carouselExampleIndicators"  data-bs-slide-to="1" aria-label="Slide 2"></button>
      </div>
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img src="@/assets/clients/ParisCity.png" alt="" width="60" height="50">
          <img src="@/assets/clients/Esiris.png" alt="" width="60" height="50">
          <img src="@/assets/clients/vinci.png" alt="vinci" width="60" height="50">
          <img src="@/assets/clients/Batiegere.png" alt="" width="60" height="50">
        </div>
        <div class="carousel-item">
          <img src="@/assets/clients/Dior.png" alt="" width="60" height="50">
          <img src="@/assets/clients/sncf2.png" alt="" width="60" height="50">
          <img src="@/assets/clients/Edys.png" alt="" width="60" height="50">
          <img src="@/assets/clients/Infraneo.png"  alt="" width="60" height="50">
        </div>
      </div>
    </div>
  </div>
</template>
<style >
.clientSection {
  img {
    height: 50px !important;
    width: 60px !important;
    margin-right: 20px;
    /* opacity: 0.5; */
    /* filter: grayscale(100%); */
    transition: ease-in-out 0.3s;
    
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
    height: 150px;
  }
}
@media (min-width: 768px) {
  img{
    margin-right: 30px;
  }
  .clientSection  img {
    height: 90px  !important;
    width: 120px !important;
    &:hover{
      height: 100px !important;
      width: 20% !important;
    }
  }
  .indicator {
    height: 7px !important;
  }
}
</style>