<template>
  <!-- prettier-ignore -->
  <div class="team container">
    <div class="section-title">
      <h2 data-aos="fade-up">Team</h2>
      <p data-aos="fade-up">
        Magnam dolores commodi suscipit. Necessitatibus eius consequatur ex
        aliquid fuga eum quidem. Sit sint consectetur velit. Quisquam quos
        quisquam cupiditate. Et nemo qui impedit suscipit alias ea. Quia fugiat
        sit in iste officiis commodi quidem hic quas.
      </p>
    </div>
    <div class="row">
      <div class="col-3 d-flex align-items-stretch" data-aos="fade-up">
        <TeamCard :name="ahmedInfos.name" :email="ahmedInfos.email" :phoneNumber="ahmedInfos.phoneNumber" :linkedIn="ahmedInfos.linkedIn" />
      </div>
      <div class="col-3 d-flex align-items-stretch" data-aos="fade-up">
        <TeamCard :name="azmiInfos.name" :email="azmiInfos.email" :phoneNumber="azmiInfos.phoneNumber" :linkedIn="azmiInfos.linkedIn" />
      </div>
    </div>
  </div>
</template>

<script>
import TeamCard from "@/components/TeamCard.vue";
export default {
  data() {
    return {
      ahmedInfos: {
        name: "ahmed kchaou",
        email: "dscdscdscsdcsd",
        phoneNumber: "52565555",
        linkedIn: "j;njn;j",
      },
      azmiInfos: {
        name: "Azmi Ammar",
        email: "dscdscdscsdcsd",
        phoneNumber: "52565555",
        linkedIn: "j;njn;j",
      },
    };
  },
  components: { TeamCard },
};
</script>

<style>
.team .member {
  margin-bottom: 20px;
  overflow: hidden;
  text-align: center;
  border-radius: 5px;
  background: #fff;
  box-shadow: 0px 2px 15px rgba(0, 0, 0, 0.1);
}

.team .member .member-img {
  position: relative;
  overflow: hidden;
}

.team .member .social {
  position: absolute;
  left: 0;
  bottom: 0;
  right: 0;
  height: 40px;
  opacity: 0;
  transition: ease-in-out 0.3s;
  text-align: center;
  background: rgba(255, 255, 255, 0.85);
}

.team .member .social a {
  transition: color 0.3s;
  color: #473d3a;
  margin: 0 10px;
  padding-top: 8px;
  display: inline-block;
}

.team .member .social a:hover {
  color: #ff5821;
}

.team .member .social i {
  font-size: 18px;
  margin: 0 2px;
}

.team .member .member-info {
  padding: 25px 15px;
}

.team .member .member-info h4 {
  font-weight: 700;
  margin-bottom: 5px;
  font-size: 18px;
  color: #473d3a;
}

.team .member .member-info span {
  display: block;
  font-size: 13px;
  font-weight: 400;
  color: #989595;
}

.team .member .member-info p {
  font-style: italic;
  font-size: 14px;
  line-height: 26px;
  color: #656262;
}

.team .member:hover .social {
  opacity: 1;
}
</style>
