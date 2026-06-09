<template>
  <div class="app">
    <NavBar />
    <HeroSection />
    <PortfolioSection />
    <AboutSection />
    <ContactSection />
    <FooterSection />
  </div>
</template>

<script setup>
import NavBar from '@/components/NavBar.vue'
import HeroSection from '@/components/HeroSection.vue'
import PortfolioSection from '@/components/PortfolioSection.vue'
import AboutSection from '@/components/AboutSection.vue'
import ContactSection from '@/components/ContactSection.vue'
import FooterSection from '@/components/FooterSection.vue'
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
  color: #1e293b;
  background: #f8fafc;
  line-height: 1.6;
}
</style>
