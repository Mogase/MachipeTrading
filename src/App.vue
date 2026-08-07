<template>
  <Header />
  <Hero />
  <Overview />
  <Mission />
  <Values />
  <Services />
  <Projects />
  <WhyChoose />
  <CompanyDetails />
  <Footer />
</template>

<script>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import Overview from './components/Overview.vue'
import Mission from './components/Mission.vue'
import Values from './components/Values.vue'
import Services from './components/Services.vue'
import Projects from './components/Projects.vue'
import WhyChoose from './components/WhyChoose.vue'
import CompanyDetails from './components/CompanyDetails.vue'
import Footer from './components/Footer.vue'

export default {
  components: {
    Header,
    Hero,
    Overview,
    Mission,
    Values,
    Services,
    Projects,
    WhyChoose,
    CompanyDetails,
    Footer
  }
}
</script>