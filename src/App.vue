<template>
  <div id="app">
    <Header />
    <Hero />
    <About />
    <Hobbies />
    <favoritos />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Hobbies from './components/Hobbies.vue'
import Favoritos from './components/Favoritos.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Hero,
    About,
    Hobbies,
    Favoritos,
    Footer
  }
}
</script>

<style>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css');
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700;800&family=Press+Start+2P&display=swap');
@import './assets/main.css';
</style>
