<template>
  <div class="flyerSection d-flex justify-content-center align-items-center my-5 px-3 text-center">
    <p class="fs-4 fw-bold text-white">Découvrez notre univers captivant ! Téléchargez notre brochure pour en savoir plus !
      <a href="@/assets/Documents/flyer.pdf" download class="btn text-white fw-bold px-3 mt-1">
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
    display: block;
    margin-left: auto;
    margin-right: auto;
    width: 40%;
    border: 2px solid  var(--main-red-color);
    color: var(--main-red-color) !important ;
    vertical-align: baseline;
    &:hover{
      color: #fff !important ;
      background-color: var(--main-red-color) !important ;
    }
  }
}
@media (min-width: 992px) {
  .flyerSection  a {
    display: inline-flex;
    width: auto;
  }

}
</style>