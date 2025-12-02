<script setup lang="ts">
import { vision, missions } from '~/data/profile'

// Mission icons mapping
const missionIcons: Record<string, string> = {
  Innovate: 'i-heroicons-light-bulb',
  Empower: 'i-heroicons-bolt',
  Solve: 'i-heroicons-puzzle-piece'
}
</script>

<template>
  <section id="vision" class="py-24 bg-gray-950">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <div class="inline-flex items-center gap-2 px-4 py-2 bg-amber-500/10 rounded-full border border-amber-500/20 mb-4">
          <UIcon name="i-heroicons-eye" class="w-4 h-4 text-amber-400" />
          <span class="text-amber-400 text-sm font-medium">Our Direction</span>
        </div>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">
          Vision & <span class="text-amber-400">Mission</span>
        </h2>
        <p class="text-gray-400 max-w-2xl mx-auto">
          Guiding principles that drive everything we do.
        </p>
      </div>

      <!-- Vision Card -->
      <div class="mb-12">
        <div class="relative bg-gradient-to-br from-purple-900/30 to-purple-800/10 rounded-3xl p-8 md:p-12 border border-purple-500/20 overflow-hidden">
          <!-- Background decoration -->
          <div class="absolute top-0 right-0 w-64 h-64 bg-purple-600/10 rounded-full blur-3xl -translate-y-1/2 translate-x-1/2" />
          <div class="absolute bottom-0 left-0 w-48 h-48 bg-amber-500/10 rounded-full blur-3xl translate-y-1/2 -translate-x-1/2" />
          
          <div class="relative z-10 max-w-4xl mx-auto text-center">
            <div class="inline-flex items-center justify-center w-16 h-16 rounded-2xl bg-purple-600/20 mb-6">
              <UIcon name="i-heroicons-eye" class="w-8 h-8 text-purple-400" />
            </div>
            <h3 class="text-2xl font-bold text-white mb-4">Our Vision</h3>
            <p class="text-xl md:text-2xl text-gray-300 leading-relaxed">
              "{{ vision }}"
            </p>
          </div>
        </div>
      </div>

      <!-- Mission Cards -->
      <div>
        <h3 class="text-2xl font-bold text-white text-center mb-8">Our Mission</h3>
        <div class="grid md:grid-cols-3 gap-6">
          <div
            v-for="(mission, index) in missions"
            :key="mission.id"
            class="group relative bg-gray-900/50 rounded-2xl p-6 border border-gray-800 hover:border-amber-500/30 transition-all duration-300"
          >
            <!-- Number Badge -->
            <div class="absolute -top-3 -left-3 w-8 h-8 rounded-full bg-amber-500 flex items-center justify-center text-gray-900 font-bold text-sm">
              {{ index + 1 }}
            </div>

            <!-- Icon -->
            <div class="w-14 h-14 rounded-xl bg-gradient-to-br from-amber-500/20 to-amber-600/10 flex items-center justify-center mb-5">
              <UIcon :name="missionIcons[mission.keyword]" class="w-7 h-7 text-amber-400" />
            </div>

            <!-- Keyword -->
            <h4 class="text-xl font-bold text-amber-400 mb-3">
              {{ mission.keyword }}
            </h4>

            <!-- Description -->
            <p class="text-gray-400 leading-relaxed">
              {{ mission.description }}
            </p>

            <!-- Decorative line -->
            <div class="mt-6 h-1 w-16 bg-gradient-to-r from-amber-500 to-purple-500 rounded-full group-hover:w-full transition-all duration-500" />
          </div>
        </div>
      </div>

      <!-- Values Summary -->
      <div class="mt-16 grid sm:grid-cols-3 gap-6">
        <div class="text-center p-6 bg-gray-800/30 rounded-xl border border-gray-700/30">
          <div class="text-3xl mb-2">💡</div>
          <h4 class="text-white font-semibold mb-1">Innovation First</h4>
          <p class="text-gray-500 text-sm">Cutting-edge solutions for modern challenges</p>
        </div>
        <div class="text-center p-6 bg-gray-800/30 rounded-xl border border-gray-700/30">
          <div class="text-3xl mb-2">🤝</div>
          <h4 class="text-white font-semibold mb-1">Client Partnership</h4>
          <p class="text-gray-500 text-sm">Building lasting relationships</p>
        </div>
        <div class="text-center p-6 bg-gray-800/30 rounded-xl border border-gray-700/30">
          <div class="text-3xl mb-2">⚡</div>
          <h4 class="text-white font-semibold mb-1">Agile Delivery</h4>
          <p class="text-gray-500 text-sm">Fast, adaptive, and reliable</p>
        </div>
      </div>
    </div>
  </section>
</template>
