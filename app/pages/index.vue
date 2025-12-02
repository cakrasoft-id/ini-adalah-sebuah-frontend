<script setup lang="ts">
import HeroSection from '~/components/sections/HeroSection.vue'
import AboutSection from '~/components/sections/AboutSection.vue'
import ServicesSection from '~/components/sections/ServicesSection.vue'
import TeamSection from '~/components/sections/TeamSection.vue'
import VisionMissionSection from '~/components/sections/VisionMissionSection.vue'
import ContactSection from '~/components/sections/ContactSection.vue'

useHead({
  title: 'CakraSoft - Innovate. Empower. Solve.',
  meta: [
    { name: 'description', content: 'CakraSoft is a leading technology company providing custom software development, web applications, IT consulting, and UI/UX design services in Bandung, Indonesia.' }
  ]
})
</script>

<template>
  <NuxtLayout>
    <HeroSection />
    <AboutSection />
    <ServicesSection />
    <TeamSection />
    <VisionMissionSection />
    <ContactSection />
  </NuxtLayout>
</template>
