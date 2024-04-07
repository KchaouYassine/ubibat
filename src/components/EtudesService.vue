<template>
  <div class="etudeSection p-5 position-relative text-center overflow-hidden">
    <div class="etudeContent">
      <h1 class="fw-bold mb-4 ">Etudes</h1>
      <p class="my-4 fs-6 textContent fw-bold">Un diagnostic se définit par l´indentication de la nature dune situation, d’un désordre dans le domaine de la construction.
        Nous garantissons une evaluation exacte et détaillée des structures existantes afin de mettre en avant les éventuels défauts pouvant impacter la valeur et la durabilité dun ouvrage
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
      title: 'AUSCULTATION ET RECONNAISSANCE',
      icon: 'fa-gear',
      content : ['Auscultation non-destructive par géoradar', 'Mesure de potentiel de corrosion des aciers', 'Réalisation de sondages et prélèvements d’échantillons', 'Réalisation de fouilles de reconnaissance de fondations' ]
    },
    { 
      title: 'DIAGNOSTIC ET EXPERTISE',
      icon: 'fa-gear',
      content : ['Diagnostic visuel/Audit due Diligence', 'Diagnostic technique réglementaire et pathologique', 'Calcul de stabilité au feu/degré coupe-feu', 'Expertise structurelle avant modification (extension, réhabilitation, surélévation)' ]
    },
    { 
      title: 'INGÉNIERIE ET PRÉCONISATION',
      icon: 'fa-gear',
      content : ['Calcul des capacités portantes', 'Préconisations de renforcement', 'Dimensionnement et optimisation de solutions et renforcements', 'Conseils pour ouvertures ou modifications d’éléments porteurs' ]
    },
    { 
      title: 'ANALYSE DES MATERIAUX',
      icon: 'fa-gear',
      content : ['Bétons (essais mécaniques, mesures physiques, analyse chimique et minéralogiques, etc.)', 'Aciers (essais physiques, observations au microscope électronique à balayage)', 'Réalisation de sondages et prélèvements d’échantillons', 'Sols (mesures de PH, analyses granulométriques / chimiques, observations microscopiques)' ]
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
