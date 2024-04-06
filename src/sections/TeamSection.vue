<template>
  <!-- prettier-ignore -->
  <div class="team container">
      <h1 class="sectionTitle fw-bold my-5">Notre team</h1>
       <div class="d-flex justify-content-around align-items-center">
        <TeamCard :name="ahmedInfos.name" :email="ahmedInfos.email" :phoneNumber="ahmedInfos.phoneNumber" :linkedIn="ahmedInfos.linkedIn" :imgPath="ahmedInfos.imgPath" />
        <TeamCard :name="azmiInfos.name" :email="azmiInfos.email" :phoneNumber="azmiInfos.phoneNumber" :linkedIn="azmiInfos.linkedIn" :imgPath="azmiInfos.imgPath" />
      </div> 

  </div>
</template>

<script>
import TeamCard from "@/components/TeamCard.vue";
export default {
  components: { TeamCard },
  data() {
    return {
      ahmedInfos: {
        name: "Ahmed kchaou",
        email: "kchaou.ahmed24@gmail.com",
        phoneNumber: "52565555",
        linkedIn: "https://www.linkedin.com/in/ahmed-kchaou-9829a0110",
        imgPath:"ahmed"
      },
      azmiInfos: {
        name: "Azmi Ammar",
        email: "azmi@live.fr",
        phoneNumber: "52565555",
        linkedIn: "https://www.linkedin.com/in/azmi-ammar-2a93bb169/",
        imgPath:"azmi"
      },
    };
  },
};
</script>

<style lang="scss">
.team {
  .member {
    width: 300px;
    height: 400px;
    text-align: center;
    border-radius: 5px;
    box-shadow: 0px 2px 15px rgba(0, 0, 0, 0.1);
    .icons {
      position: absolute;
      left: 0;
      bottom: 0;
      right: 0;
      height: 40px;
      opacity: 0;
      transition: ease-in-out 0.3s;
      text-align: center;
      background: rgba(255, 255, 255, 0.85);
      a {
        font-size: 18px;
        transition: color 0.3s ease-in-out;
        color: var(--main-black-color);
        &:hover{
          color: var(--main-red-color) !important;
        }
      }
    }
    &:hover .icons{
      opacity: 1;
    }

  }
}
</style>
