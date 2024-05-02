<template>
    <div class="goToContact show rounded text-white fs-5 cursor-pointer" id="goToContact" @click="goToContact">contact</div>
    <LandingSection />
    <WhoWeAreSection />
    <ServicesSection />
    <ClientsSection/>
    <FlyerSection />
    <TeamSection />
    <ContactSection />
    <!-- <FooterSection /> -->
</template>

<script>
import LandingSection from '@/sections/LandingSection.vue'
import WhoWeAreSection from '@/sections/WhoWeAreSection.vue'
import ServicesSection from '@/sections/ServicesSection.vue'
import ClientsSection from '@/sections/ClientsSection.vue'
import FlyerSection from '@/sections/FlyerSection.vue'
import TeamSection from '@/sections/TeamSection.vue'
import ContactSection from '@/sections/ContactSection.vue'
import FooterSection from '@/sections/FooterSection.vue'

export default{
  name:'home',
  components: {
    LandingSection, 
    WhoWeAreSection, 
    ServicesSection,
    ClientsSection,
    FlyerSection,
    TeamSection,
    ContactSection,
    FooterSection
  },
  methods: {
    goToContact(){
      console.log(document.getElementById('goToContact').classList.remove)
      window.scrollTo(0, document.body.scrollHeight)
    },

    handleScroll() {
      const goToContactElement = document.getElementById('goToContact')
      if (window.scrollY > 3730) {
        goToContactElement.classList.remove('show')
        goToContactElement.classList.add('hide')
      } else {
        goToContactElement.classList.remove('hide')
        goToContactElement.classList.add('show')
      }
    }
  },

  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="scss">
.show{
  position: fixed;
}
.hide{
  display: none;
}
.sectionTitle{
  font-size: 40px;
}
.textContent{
  line-height: 28px;
}
.goToContact {
  right: -35px;
  top: 200px;
  z-index: 99;
  width: 100px;
  height: 30px;
  background: var(--main-green-color);
  transform: rotate(270deg);
  letter-spacing: 2px
}

@media (min-width: 768px) {
  .sectionTitle{
    font-size: 45px
  }
  .textContent{
    line-height: 30px
  }
}
@media (min-width: 992px) {
  .sectionTitle{
    font-size: 50px;
  }
  .textContent{
    line-height: 35px;
  }
}
</style>
