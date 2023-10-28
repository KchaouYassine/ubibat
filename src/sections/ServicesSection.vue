<template>
    <div class="100-vh">
      <nav class="container nav nav-pills justify-content-center flex-column flex-sm-row">
      <a class="flex-sm-fill text-sm-center nav-link active" aria-current="page" @click="onChangeService('diagnostic')">Diagnostic</a>
      <a class="flex-sm-fill text-sm-center nav-link" @click="onChangeService('etudes')">Etudes</a>
      <a class="flex-sm-fill text-sm-center nav-link"  @click="onChangeService('chantier')">Chantier</a>
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
    onChangeService(type){
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
<styple>

</styple>