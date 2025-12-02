<script setup lang="ts">
import { companyInfo, logoPhilosophy } from '~/data/profile'
</script>

<template>
  <section id="about" class="py-24 bg-gray-900/50">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <div class="inline-flex items-center gap-2 px-4 py-2 bg-purple-500/10 rounded-full border border-purple-500/20 mb-4">
          <UIcon name="i-heroicons-building-office-2" class="w-4 h-4 text-purple-400" />
          <span class="text-purple-400 text-sm font-medium">Our Story</span>
        </div>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">
          About <span class="text-purple-400">{{ companyInfo.name }}</span>
        </h2>
        <p class="text-gray-400 max-w-2xl mx-auto">
          Discover the journey behind our company and what drives us to deliver excellence.
        </p>
      </div>

      <!-- Content Grid -->
      <div class="grid lg:grid-cols-2 gap-12 items-center">
        <!-- Left: Story -->
        <div class="space-y-6">
          <div class="bg-gray-800/50 rounded-2xl p-6 border border-gray-700/50">
            <h3 class="text-xl font-semibold text-white mb-4 flex items-center gap-2">
              <UIcon name="i-heroicons-book-open" class="w-5 h-5 text-amber-400" />
              Our Origin
            </h3>
            <p class="text-gray-400 leading-relaxed">
              {{ companyInfo.description }}
            </p>
          </div>

          <!-- Key Info Cards -->
          <div class="grid sm:grid-cols-2 gap-4">
            <div class="bg-gray-800/30 rounded-xl p-5 border border-gray-700/30">
              <div class="flex items-center gap-3 mb-2">
                <div class="w-10 h-10 rounded-lg bg-purple-500/20 flex items-center justify-center">
                  <UIcon name="i-heroicons-user" class="w-5 h-5 text-purple-400" />
                </div>
                <span class="text-gray-500 text-sm">Founder</span>
              </div>
              <p class="text-white font-medium">{{ companyInfo.founder }}</p>
            </div>

            <div class="bg-gray-800/30 rounded-xl p-5 border border-gray-700/30">
              <div class="flex items-center gap-3 mb-2">
                <div class="w-10 h-10 rounded-lg bg-amber-500/20 flex items-center justify-center">
                  <UIcon name="i-heroicons-calendar" class="w-5 h-5 text-amber-400" />
                </div>
                <span class="text-gray-500 text-sm">Established</span>
              </div>
              <p class="text-white font-medium">{{ companyInfo.established }}</p>
            </div>

            <div class="bg-gray-800/30 rounded-xl p-5 border border-gray-700/30 sm:col-span-2">
              <div class="flex items-center gap-3 mb-2">
                <div class="w-10 h-10 rounded-lg bg-purple-500/20 flex items-center justify-center">
                  <UIcon name="i-heroicons-map-pin" class="w-5 h-5 text-purple-400" />
                </div>
                <span class="text-gray-500 text-sm">Headquarters</span>
              </div>
              <p class="text-white font-medium">{{ companyInfo.location }}</p>
            </div>
          </div>
        </div>

        <!-- Right: Logo Philosophy -->
        <div class="bg-gradient-to-br from-purple-900/20 to-gray-800/50 rounded-2xl p-8 border border-purple-500/20">
          <h3 class="text-xl font-semibold text-white mb-6 flex items-center gap-2">
            <UIcon name="i-heroicons-sparkles" class="w-5 h-5 text-amber-400" />
            The Meaning Behind Our Name
          </h3>

          <div class="space-y-6">
            <!-- Cakra Meaning -->
            <div class="flex gap-4">
              <div class="flex-shrink-0 w-12 h-12 rounded-full bg-gradient-to-br from-purple-600 to-purple-800 flex items-center justify-center">
                <span class="text-amber-400 font-bold text-lg">C</span>
              </div>
              <div>
                <h4 class="text-white font-medium mb-1">Cakra</h4>
                <p class="text-gray-400 text-sm leading-relaxed">
                  {{ logoPhilosophy.cakra }}
                </p>
              </div>
            </div>

            <!-- Soft Meaning -->
            <div class="flex gap-4">
              <div class="flex-shrink-0 w-12 h-12 rounded-full bg-gray-700/50 flex items-center justify-center border border-gray-600">
                <span class="text-purple-400 font-bold text-lg">S</span>
              </div>
              <div>
                <h4 class="text-white font-medium mb-1">Soft</h4>
                <p class="text-gray-400 text-sm leading-relaxed">
                  {{ logoPhilosophy.soft }}
                </p>
              </div>
            </div>

            <!-- Color Meanings -->
            <div class="pt-4 border-t border-gray-700/50">
              <h4 class="text-white font-medium mb-4">Our Color Philosophy</h4>
              <div class="grid grid-cols-3 gap-3">
                <div class="text-center">
                  <div class="w-full h-3 rounded-full bg-gradient-to-r from-purple-600 to-purple-400 mb-2" />
                  <span class="text-gray-400 text-xs">Wisdom & Creativity</span>
                </div>
                <div class="text-center">
                  <div class="w-full h-3 rounded-full bg-gradient-to-r from-amber-500 to-amber-400 mb-2" />
                  <span class="text-gray-400 text-xs">Quality & Success</span>
                </div>
                <div class="text-center">
                  <div class="w-full h-3 rounded-full bg-gradient-to-r from-gray-800 to-gray-600 mb-2" />
                  <span class="text-gray-400 text-xs">Professionalism</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
