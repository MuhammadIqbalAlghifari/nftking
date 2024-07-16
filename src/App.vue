<template>
  <Navbar/>
  <Hero/>
  <Trending/>
  <Marketplace/>
  <TopCreator/>
  <Footer/>
</template>
<script setup>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Trending from './components/Trending.vue'
import Marketplace from './components/Marketplace.vue'
import TopCreator from './components/TopCreator.vue'
import Footer from './components/Footer.vue'
import Lenis from 'lenis'
import { onMounted } from 'vue'

onMounted(() => {
  const lenis = new Lenis()
  
  function raf(time) {
    lenis.raf(time)
    requestAnimationFrame(raf)
  }

  requestAnimationFrame(raf)
})


</script>