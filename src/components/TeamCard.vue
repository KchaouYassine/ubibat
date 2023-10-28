<template>
  <div class="member">
    <div class="member-img">
      <img src="@/assets/team/team-1.jpg" class="img-fluid" alt="" />
      <div class="social">
        <a @click="onChooseInfo('email')"><i class="icofont-twitter"> email</i></a>
        <a @click="onChooseInfo('phoneNumber')"><i class="icofont-facebook">lin</i></a>
        <a @click="onChooseInfo('linkedIn')"><i class="icofont-instagram">Phone</i></a>
      </div>
    </div>
    <div class="member-info">
      <h4>{{ name }}</h4>
      <span v-show="showEmail" >{{email}}</span>
      <span v-show="showPhoneNumber" >{{ phoneNumber }}</span>
      <span v-show="showlinkedIn" >{{ linkedIn }}</span>
    </div>
  </div>
</template>
<script>

export default {
  name:"Team",
  props:{
    name: String,
    email: String,
    phoneNumber: String,
    linkedIn: String
  },
  data(){
    return {
      showEmail:true,
      showlinkedIn:false,
      showPhoneNumber:false

    }
  },
  methods:{
    onChooseInfo(info){
      if(info === 'email') {
        this.showEmail = true,
        this.showlinkedIn = false
        this.showPhoneNumber = false
      }else if(info === 'phoneNumber') {
        this.showEmail = false,
        this.showlinkedIn = true
        this.showPhoneNumber = false
      }else{
        this.showEmail = false,
        this.showlinkedIn = false
        this.showPhoneNumber = true
      }
    }
  }
}
</script>
