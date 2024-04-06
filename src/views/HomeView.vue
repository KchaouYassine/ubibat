<template>
  <LandingSection />
  <WhoWeAreSection />
  <ServicesSection />
  <ClientsSection/>
  <FlyerSection />
  <TeamSection />
  <ContactSection />
  <FooterSection />
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
  }
}

</script>

<style>


.redBg{
  background: #e74c3c !important;
}
.greenBg {
  background: #0f9c22 !important;
}
.orangeBg {
  background: #f0690f !important;
}


</style>