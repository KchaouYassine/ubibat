<template>
  <div class="chantierSection p-5 position-relative text-center overflow-hidden">
    <div class="chantierContent">
      <h1 class="fw-bold mb-4 ">Chantier</h1>
      <p class="my-4 fs-6 textContent fw-bold">Un conducteur de travaux joue un rôle central et indispensable dans la réussite d'un chantier de construction, Le conducteur de travaux fait le lien entre tous les intervenants.
      </p>
      <div class="services row margin-auto">
        <div v-for="diagnosticItem in  chantierData" :key="diagnosticItem.title"  class="col-md-6">
          <div class="icon-box position-relative  bg-white mb-5 mt-3 py-5 px-4 ">
              <div class="icon position-absolute text-white d-flex align-items-center justify-content-center"><font-awesome-icon icon="fa-solid fa-screwdriver-wrench fa-lg" /></div>
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
  const chantierData = ref([
    { 
      title: 'Planification et préparation du chantier',
      icon: 'fa-gear',
      content : ["Établir le planning d\'exécution détaillé", "Analyser les plans, définir les modes opératoires et méthodes constructives", "Préparer l'installation du chantier (accès, raccordements, etc.)"]
    },
    { 
      title: 'Gestion technique et financière',
      icon: 'fa-gear',
      content : ["Définir les moyens matériels, humains et financiers nécessaires", "Négocier et gérer les contrats avec sous-traitants et fournisseurs", "Contrôler les coûts, suivre le budget et l'avancement"]
    },
    { 
      title: 'Management et supervision',
      icon: 'fa-gear',
      content : ["Recruter et encadrer les équipes de chantier", "Diriger et superviser les travaux au quotidien", "Veiller au respect des normes de sécurité"]
    },
    { 
      title: 'Assurer la livraison du chantier',
      icon: 'fa-gear',
      content : ["Assurer la qualité des travaux réalisés", "Détecter et résoudre les problèmes, gérer les imprévus", "Coordonner les interventions des différents corps de métier"]
    }
  ])

  return {
    iconCheck:'fa-check',
    chantierData
  }
}

};
</script>

<style lang="scss" scoped>
.chantierSection{
  background: url(@/assets/services/chantier.jpg);
  background-size: cover;
  }

.services {
.icon-box {
  height: 400px;
  box-shadow: 0px 2px 15px rgba(0, 0, 0, 0.1);

  .icon {
    background:var(--main-orange-color);
  }
  &:hover{
    .icon {
      color: var(--main-orange-color) !important;
      border: 2px solid var(--main-orange-color);
    }
    h4{
      color: var(--main-orange-color) ;
    }

  }
}
}

// Large devices
@media (min-width: 992px) {
  .chantierContent{
    width: 50%;
  }
  .chantierSection > div{
    margin-left: 50%;
  }
}

</style>
