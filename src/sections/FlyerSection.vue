<template>
  <div class="flyerSection d-flex justify-content-center align-items-center my-5">
    <p class="fs-4 fw-bold text-white">Découvrez notre univers captivant ! Téléchargez notre brochure pour en savoir plus !
      <a href="@/assets/Documents/flyer.pdf" download class="btn text-white fw-bold px-4 ms-3 ">
        <i class="fa fa-download"></i> Télécharger
      </a>
    </p>
  </div>
</template>
<style lang="scss">
.flyerSection{
  background-image: url('@/assets/flyer.jpg');
  background-size: cover;
  height: 40vh;
  position: relative;
  &::before{
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(3, 17, 54, .5) !important ;
  }
  p, a{
    z-index: 99; 
  }
  a{
    border: 2px solid  var(--main-red-color);
    color: var(--main-red-color) !important ;
    vertical-align: baseline;
    &:hover{
      color: #fff !important ;
      background-color: var(--main-red-color) !important ;
    }
  }
}

</style>