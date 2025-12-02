<script setup lang="ts">
import { companyInfo } from '~/data/profile'
</script>

<template>
  <section id="home" class="relative min-h-screen flex items-center justify-center overflow-hidden pt-16">
    <!-- Background Gradient -->
    <div class="absolute inset-0 bg-gradient-to-br from-gray-950 via-purple-950/20 to-gray-950" />
    
    <!-- Animated Background Elements -->
    <div class="absolute inset-0 overflow-hidden">
      <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-purple-600/10 rounded-full blur-3xl animate-pulse" />
      <div class="absolute bottom-1/4 right-1/4 w-80 h-80 bg-amber-500/10 rounded-full blur-3xl animate-pulse" style="animation-delay: 1s" />
      <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[600px] bg-purple-800/5 rounded-full blur-3xl" />
    </div>

    <!-- Grid Pattern Overlay -->
    <div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDAiIGhlaWdodD0iNDAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGRlZnM+PHBhdHRlcm4gaWQ9ImdyaWQiIHdpZHRoPSI0MCIgaGVpZ2h0PSI0MCIgcGF0dGVyblVuaXRzPSJ1c2VyU3BhY2VPblVzZSI+PHBhdGggZD0iTSAwIDEwIEwgNDAgMTAgTSAxMCAwIEwgMTAgNDAgTSAwIDIwIEwgNDAgMjAgTSAyMCAwIEwgMjAgNDAgTSAwIDMwIEwgNDAgMzAgTSAzMCAwIEwgMzAgNDAiIGZpbGw9Im5vbmUiIHN0cm9rZT0iIzM3NDE1MSIgc3Ryb2tlLW9wYWNpdHk9IjAuMiIgc3Ryb2tlLXdpZHRoPSIxIi8+PC9wYXR0ZXJuPjwvZGVmcz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSJ1cmwoI2dyaWQpIi8+PC9zdmc+')] opacity-30" />

    <!-- Content -->
    <div class="relative z-10 container mx-auto px-4 sm:px-6 lg:px-8 text-center">
      <!-- Company Logo/Icon -->
      <div class="mb-8 flex justify-center">
        <div class="w-24 h-24 rounded-full bg-gradient-to-br from-purple-600 to-purple-800 flex items-center justify-center shadow-2xl shadow-purple-500/30 ring-4 ring-purple-500/20">
          <span class="text-amber-400 font-bold text-4xl">C</span>
        </div>
      </div>

      <!-- Company Name -->
      <h1 class="text-5xl sm:text-6xl lg:text-7xl font-bold mb-4">
        <span class="bg-gradient-to-r from-purple-400 via-purple-300 to-purple-400 bg-clip-text text-transparent">
          {{ companyInfo.name }}
        </span>
      </h1>

      <!-- Tagline -->
      <p class="text-xl sm:text-2xl lg:text-3xl font-medium text-amber-400 mb-6">
        {{ companyInfo.tagline }}
      </p>

      <!-- Description -->
      <p class="text-gray-400 text-lg max-w-2xl mx-auto mb-8 leading-relaxed">
        Transforming businesses through innovative and adaptive digital solutions. 
        Your trusted IT partner for custom software development and technology consulting.
      </p>

      <!-- Location Badge -->
      <div class="flex justify-center mb-10">
        <div class="inline-flex items-center gap-2 px-4 py-2 bg-gray-800/50 rounded-full border border-gray-700">
          <UIcon name="i-heroicons-map-pin" class="w-4 h-4 text-purple-400" />
          <span class="text-gray-300 text-sm">Based in Bandung, Indonesia</span>
        </div>
      </div>

      <!-- CTA Buttons -->
      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <UButton 
          color="primary" 
          size="xl" 
          class="px-8"
          trailing-icon="i-heroicons-arrow-right"
        >
          Explore Our Services
        </UButton>
        <UButton 
          color="neutral" 
          variant="outline" 
          size="xl" 
          class="px-8"
        >
          Contact Us
        </UButton>
      </div>

      <!-- Stats -->
      <div class="mt-16 grid grid-cols-2 sm:grid-cols-4 gap-8 max-w-3xl mx-auto">
        <div class="text-center">
          <div class="text-3xl font-bold text-purple-400">4+</div>
          <div class="text-gray-500 text-sm mt-1">Core Services</div>
        </div>
        <div class="text-center">
          <div class="text-3xl font-bold text-purple-400">4</div>
          <div class="text-gray-500 text-sm mt-1">Expert Leaders</div>
        </div>
        <div class="text-center">
          <div class="text-3xl font-bold text-amber-400">100%</div>
          <div class="text-gray-500 text-sm mt-1">Dedication</div>
        </div>
        <div class="text-center">
          <div class="text-3xl font-bold text-amber-400">∞</div>
          <div class="text-gray-500 text-sm mt-1">Innovation</div>
        </div>
      </div>
    </div>

    <!-- Scroll Indicator -->
    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 animate-bounce">
      <UIcon name="i-heroicons-chevron-down" class="w-6 h-6 text-gray-500" />
    </div>
  </section>
</template>
