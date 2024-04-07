<template>
  <div class="contactSection text-center p-4">
    <div class="contactContent d-flex align-items-center flex-wrap">
      <div class="d-none d-lg-inline-flex">
        <img src="@/assets/parisMaps.jpg" class="img-fluid" alt="" height="300" width="300" />
      </div>
      
      <div class="text-start">
        <h3>Contact</h3>
        <div>
          <p>
              Medicusstrasse 5<br>
              kaiserslautern, 676555<br>
              France<br>
            </p>
            <p>
              <strong>Phone:</strong> 06 41 27 38 32<br>
              <strong>Phone:</strong> 06 64 27 86 57<br>
              <strong>Email:</strong> contact@ubibat.fr<br>
              <strong>Email:</strong> etude@ubibat.fr<br>
            </p>
        </div>
      </div>

      <div class="text-start">
        <h3>Domaines d'intervention</h3>
        <div class="row domaineInterventionsImg">
            <div class="col-12 mb-1">
              <img src="@/assets/clients/client-4.png" class="me-1" width="80" alt="">
              <img src="@/assets/clients/client-5.png" class="me-1" width="80" alt="">
              <img src="@/assets/clients/client-5.png" class="me-1" width="80" alt="">
            </div>
            <div class="col-12 mb-1">
              <img src="@/assets/clients/client-4.png" class="me-1"  width="80" alt="">
              <img src="@/assets/clients/client-5.png" class="me-1"  width="80" alt="">
              <img src="@/assets/clients/client-5.png" class="me-1"  width="80" alt="">
            </div>
        </div>
      </div>

    </div>
  </div>

</template>
<style>
.contactSection{
  background: rgba(240, 105, 15, 0.6);
}
.contactContent{
  justify-content: start;
  .domaineInterventionsImg{
    height: 80px
  } 
}
@media (min-width: 768px) {
  .contactContent   {
    justify-content: space-around; 
    .domaineInterventionsImg{
      height: 60px
    }
  }

}
</style>