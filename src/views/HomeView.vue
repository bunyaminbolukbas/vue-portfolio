<script setup>
import MainNavbar from '../components/MainNavbar.vue'
import HeroSection from '../components/HeroSection.vue'
import AboutSection from '../components/AboutSection.vue'
import ProjectsSection from '../components/ProjectsSection.vue'
import TechStack from '../components/TechStack.vue'
import ContactForm from '../components/ContactForm.vue'
import FooterSection from '../components/FooterSection.vue'
import ParticleBackground from '../components/ParticleBackground.vue'
</script>

<template>
  <div class="relative">
    <ParticleBackground />

    <MainNavbar />
    <HeroSection />
    <AboutSection />
    <ProjectsSection />
    <TechStack />
    <ContactForm />
    <FooterSection />
  </div>
</template>
