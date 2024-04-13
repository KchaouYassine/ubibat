<template>
  <div class="member text-center mb-3 bg-white overflow-hidden ">
    <div class="member-img position-relative ">
      <img src="@/assets/team/team-1.jpg" class="img-fluid" alt="" />
      <div class="icons">
        <a @click="onChooseInfo('profession')"> <font-awesome-icon icon="fa-solid fa-user-tie"  class="d-inline-block mx-2 mt-3 cursor-pointer" /></a>
        <a @click="onChooseInfo('email')"> <font-awesome-icon icon="fa-solid fa-envelope fa-lg" class="d-inline-block mx-2 mt-3 cursor-pointer" /></a>
        <a @click="onChooseInfo('phoneNumber')"> <font-awesome-icon icon="fa-solid fa-phone fa-lg" class="d-inline-block mx-2 mt-3 cursor-pointer" /></a>
        <a :href="linkedIn"> <font-awesome-icon icon="fa-brands fa-linkedin" class="d-inline-block mx-2 mt-3 cursor-pointer" /></a>
      </div>
    </div>
    <div class="member-infos py-3">
      <h4 class=" fw-bold fs-4 mb-2 text-red">{{ name }}</h4>
      <span v-if="showProfession" class="text-black d-block fw-bold " >{{profession}}</span>
      <span v-if="showEmail" class="text-black d-block fw-bold " >{{email}}</span>
      <span v-if="showPhoneNumber" class="text-black d-block fw-bold" >{{ phoneNumber }}</span>
    </div>
  </div>
</template>
<script>

export default {
  name:"Team",
  props:{
    name: String,
    profession: String,
    email: String,
    phoneNumber: String,
    linkedIn: String
  },
  data(){
    return {
      showProfession: true,
      showEmail:false,
      showPhoneNumber:false
    }
  },
  methods:{
    onChooseInfo(info){
      if(info === 'profession'){
        this.showProfession = true
        this.showEmail = false,
        this.showlinkedIn = false
        this.showPhoneNumber = false
      }else if(info === 'email'){
        this.showEmail = true,
        this.showProfession = false
        this.showlinkedIn = false
        this.showPhoneNumber = false
      }else if(info === 'phoneNumber') {
        this.showProfession = false
        this.showPhoneNumber = true
        this.showEmail = false,
        this.showlinkedIn = false
      }else{
        this.showEmail = false,
        this.showPhoneNumber = false
        this.showProfession = false
      }
    }
  }
}
</script>
