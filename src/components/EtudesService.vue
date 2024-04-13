<template>
  <div class="etudeSection p-5 position-relative text-center overflow-hidden">
    <div class="etudeContent">
      <h1 class="fw-bold mb-4 ">Etudes</h1>
      <p class="my-4 fs-6 textContent fw-bold">L'étude de structure est incontournable dans la réalisation de votre projet, que ce soit en réhabilitation ou en construction.
          Il s'agit dune entité se chargeant notamment des calculs et notes relatifs a l'étude de faisabilité d'un projet de construction.
      </p>
      <div class="services row margin-auto">
        <div v-for="diagnosticItem in  diagnosticData" :key="diagnosticItem.title"  class="col-md-6">
          <div class="icon-box position-relative  bg-white mb-5 mt-3 py-5 px-4 ">
              <div class="icon position-absolute text-white d-flex align-items-center justify-content-center"><font-awesome-icon icon="fa-solid fa-check fa-lg" /></div>
              <h4 class="fs-5 mb-3 text-center">{{ diagnosticItem.title }}</h4>
              <ul class=" list-unstyled text-start">
                <li class="mb-1" v-for="info in  diagnosticItem.content" :key="info"> 
                  <font-awesome-icon :icon="'fa-solid fa-check fa-lg'"  class="me-2" />
                  {{ info }}
                </li>
              </ul> 
            </div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
import { ref } from 'vue'
export default {
name:"EtudeServices",

setup() {
  const diagnosticData = ref([
    { 
      title: 'Études de structures phase APS/APD',
      icon: 'fa-gear',
      content : []
    },
    { 
      title: "Etudes d'exécutions de structures en phase d'EXE",
      icon: 'fa-gear',
      content : []

    },
    { 
      title: "Conseils en structure: conception et optimisation pour le bâtiment",
      icon: 'fa-gear',
      content : []

    },
    { 
      title: "Études en réhabilitation ou en neuf",
      icon: 'fa-gear',
      content : []

    }
  ])

  return {
    iconCheck:'fa-check',
    diagnosticData
  }
}

};
</script>

<style lang="scss" scoped>
.etudeSection{
  background: url(@/assets/services/etude.jpg);
  background-size: cover;
  
}

.services {
  .icon-box {
    height: 400px;
    box-shadow: 0px 2px 15px rgba(0, 0, 0, 0.1);

    .icon {
      background:var(--main-green-color);
    }
    &:hover{
      .icon {
        color: var(--main-green-color) !important;
        border: 2px solid var(--main-green-color);
      }
      h4{
        color: var(--main-green-color) ;
      }

    }
  }
}

// Large devices
@media (min-width: 992px) {
  .etudeContent{
    width: 50%;
  }
  .etudeSection > div{
    margin-left: 50%;
  }
}
</style>
