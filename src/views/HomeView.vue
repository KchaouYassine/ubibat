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
.sectionTitle{
  font-size: 40px;
}
.textContent{
    line-height: 28px;
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
