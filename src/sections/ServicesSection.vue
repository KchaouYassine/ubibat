<template>
    <div class="serviceSection 100-vh">
      <nav class="container nav nav-pills justify-content-center flex-column flex-sm-row">
      <a class="mx-5 cursor-pointer flex-sm-fill text-sm-center nav-link pill-outline-red active" aria-current="page" @click="(event) => onChangeService(event,'diagnostic')">Diagnostic</a>
      <a class="mx-5 cursor-pointer flex-sm-fill text-sm-center nav-link pill-outline-green" @click="(event) =>  onChangeService(event, 'etudes')">Etudes</a>
      <a class="mx-5 cursor-pointer flex-sm-fill text-sm-center nav-link pill-outline-orange"  @click=" (event) => onChangeService(event , 'chantier')">Chantier</a>
    </nav>
    <div v-show="showDiagnosticSection" class="diagnostic" >
      <DiagnosticService />
    </div>
    <div v-show="showEtudesSection" class="etudes">
      <EtudesService />
    </div>
    <div  v-show="showChantierSection" class="chantier">
      <ChantierService />
    </div>
    </div>
</template>

<script>
import DiagnosticService from '@/components/DiagnosticService.vue'
import EtudesService from '@/components/EtudesService.vue'
import ChantierService from '@/components/ChantierService.vue'


export default {
  name:"Services",
  components:{DiagnosticService, EtudesService, ChantierService},
  data(){
    return{
      showDiagnosticSection:true,
      showEtudesSection:false,
      showChantierSection:false
    }
  },
  methods:{
    onChangeService(event,type){
      const pills = document.querySelectorAll('.serviceSection a');
      pills.forEach(pill => pill.classList.remove('active'));
      event.target.classList.add('active');

      if(type === 'diagnostic'  ) {
        this.showDiagnosticSection = true,
        this.showEtudesSection = false
        this.showChantierSection = false
      }else if(type === 'etudes') {
        this.showDiagnosticSection = false,
        this.showEtudesSection = true
        this.showChantierSection = false
      }else{
        this.showDiagnosticSection = false,
        this.showEtudesSection = false
        this.showChantierSection = true
      }

    }
  }
};
</script>

<style lang="scss" >
.pill-outline-green {
  border: 1px solid var(--main-green-color) !important;
  color: var(--main-green-color) !important;
  &:hover, &.active{
    background: var(--main-green-color) !important;
    color: #fff !important;
  }
}
.pill-outline-orange {
  border: 1px solid var(--main-orange-color) !important;
  color: var(--main-orange-color) !important;
  &:hover, &.active{
    background: var(--main-orange-color) !important;
    color: #fff !important;
  }
}.pill-outline-red {
  border: 1px solid var(--main-red-color) !important;
  color: var(--main-red-color) !important;
  &:hover, &.active{
    background: var(--main-red-color) !important;
    color: #fff !important;
  }
}
</style>