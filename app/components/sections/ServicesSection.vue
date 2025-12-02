<script setup lang="ts">
import { services } from '~/data/profile'
</script>

<template>
  <section id="services" class="py-24 bg-gray-950">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <div class="inline-flex items-center gap-2 px-4 py-2 bg-amber-500/10 rounded-full border border-amber-500/20 mb-4">
          <UIcon name="i-heroicons-rocket-launch" class="w-4 h-4 text-amber-400" />
          <span class="text-amber-400 text-sm font-medium">What We Offer</span>
        </div>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">
          Our <span class="text-amber-400">Services</span>
        </h2>
        <p class="text-gray-400 max-w-2xl mx-auto">
          We provide integrated technology solutions to support your business's digital transformation.
        </p>
      </div>

      <!-- Services Grid -->
      <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
        <div
          v-for="service in services"
          :key="service.id"
          class="group relative bg-gray-900/50 rounded-2xl p-6 border border-gray-800 hover:border-purple-500/50 transition-all duration-300 hover:-translate-y-2"
        >
          <!-- Glow Effect on Hover -->
          <div class="absolute inset-0 bg-gradient-to-br from-purple-600/10 to-amber-500/5 rounded-2xl opacity-0 group-hover:opacity-100 transition-opacity" />
          
          <!-- Content -->
          <div class="relative z-10">
            <!-- Icon -->
            <div class="w-14 h-14 rounded-xl bg-gradient-to-br from-purple-600/20 to-purple-800/20 flex items-center justify-center mb-5 group-hover:from-purple-600/30 group-hover:to-purple-800/30 transition-colors">
              <UIcon :name="service.icon" class="w-7 h-7 text-purple-400" />
            </div>

            <!-- Title -->
            <h3 class="text-lg font-semibold text-white mb-3 group-hover:text-purple-300 transition-colors">
              {{ service.title }}
            </h3>

            <!-- Description -->
            <p class="text-gray-400 text-sm leading-relaxed">
              {{ service.description }}
            </p>

            <!-- Learn More Link -->
            <div class="mt-5 flex items-center gap-2 text-purple-400 text-sm font-medium opacity-0 group-hover:opacity-100 transition-opacity">
              <span>Learn more</span>
              <UIcon name="i-heroicons-arrow-right" class="w-4 h-4" />
            </div>
          </div>
        </div>
      </div>

      <!-- Bottom CTA -->
      <div class="mt-16 text-center">
        <div class="bg-gradient-to-r from-purple-900/30 via-gray-800/50 to-amber-900/30 rounded-2xl p-8 border border-gray-700/50">
          <h3 class="text-2xl font-semibold text-white mb-3">
            Need a Custom Solution?
          </h3>
          <p class="text-gray-400 mb-6 max-w-xl mx-auto">
            We understand that every business is unique. Let us design a tailored solution that fits your specific needs.
          </p>
          <UButton 
            color="primary" 
            size="lg"
            trailing-icon="i-heroicons-arrow-right"
          >
            Get a Free Consultation
          </UButton>
        </div>
      </div>
    </div>
  </section>
</template>
