<template>
    <div class="diagnosticSection p-5 position-relative text-center">
      <div class="w-50">
        <h1 class="fw-bold mb-4 ">Diagnostic</h1>
        <p class="my-4 fs-5">Un diagnostic se définit par l´indentication de la nature dune situation, d’un désordre dans le domaine de la construction.
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
  name:"DiagnosticServices",
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

<style lang="scss" >
.diagnosticSection{
  background: url(@/assets/services/diagnostic.jpg);
  background-size: cover;

}

.services {
  .icon-box {
    height: 320px;
    box-shadow: 0px 2px 15px rgba(0, 0, 0, 0.1);
    border-radius: 0.375rem;

    .icon {
      top: -36px;
      left: calc(50% - 36px);
      transition: 0.3s ease-in-out;
      border-radius: 50%;
      border: 6px solid #fff;
      background:var(--main-red-color);
      width: 72px;
      height: 72px;
    }
    &:hover{
    .icon {
        font-size: 30px;
        color: var(--main-red-color) !important;
        background: #fff !important;
        border: 2px solid var(--main-red-color);
      }
      h4{
        font-weight: bold ;
        color: var(--main-red-color) ;
      }

    }
  }
}

</style>
