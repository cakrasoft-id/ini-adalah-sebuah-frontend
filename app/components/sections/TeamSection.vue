<script setup lang="ts">
import { team } from '~/data/profile'

// Role-specific colors
interface RoleColor {
  bg: string
  text: string
  ring: string
}

const defaultColor: RoleColor = { bg: 'bg-purple-600', text: 'text-purple-400', ring: 'ring-purple-500/30' }

const roleColors: Record<string, RoleColor> = {
  CEO: defaultColor,
  CFO: { bg: 'bg-amber-600', text: 'text-amber-400', ring: 'ring-amber-500/30' },
  CMO: { bg: 'bg-blue-600', text: 'text-blue-400', ring: 'ring-blue-500/30' },
  CTO: { bg: 'bg-emerald-600', text: 'text-emerald-400', ring: 'ring-emerald-500/30' }
}

const getRoleColor = (role: string): RoleColor => {
  return roleColors[role] || defaultColor
}
</script>

<template>
  <section id="team" class="py-24 bg-gray-900/50">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <div class="inline-flex items-center gap-2 px-4 py-2 bg-purple-500/10 rounded-full border border-purple-500/20 mb-4">
          <UIcon name="i-heroicons-user-group" class="w-4 h-4 text-purple-400" />
          <span class="text-purple-400 text-sm font-medium">Our Leadership</span>
        </div>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">
          Meet the <span class="text-purple-400">Team</span>
        </h2>
        <p class="text-gray-400 max-w-2xl mx-auto">
          The passionate leaders driving innovation and excellence at CakraSoft.
        </p>
      </div>

      <!-- Team Grid -->
      <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
        <div
          v-for="member in team"
          :key="member.id"
          class="group relative bg-gray-800/30 rounded-2xl p-6 border border-gray-700/50 hover:border-purple-500/30 transition-all duration-300 text-center"
        >
          <!-- Avatar -->
          <div class="relative mx-auto mb-5">
            <div 
              class="w-24 h-24 rounded-full flex items-center justify-center text-white text-3xl font-bold ring-4 transition-all duration-300"
              :class="[getRoleColor(member.role).bg, getRoleColor(member.role).ring, 'group-hover:ring-8']"
            >
              {{ member.name.charAt(0) }}
            </div>
            <!-- Role Badge -->
            <div 
              class="absolute -bottom-2 left-1/2 -translate-x-1/2 px-3 py-1 rounded-full text-xs font-semibold bg-gray-900 border border-gray-700"
              :class="getRoleColor(member.role).text"
            >
              {{ member.role }}
            </div>
          </div>

          <!-- Info -->
          <h3 class="text-xl font-semibold text-white mb-1">
            {{ member.name }}
          </h3>
          <p class="text-gray-500 text-sm mb-3">
            {{ member.fullRole }}
          </p>
          <p class="text-gray-400 text-sm">
            {{ member.description }}
          </p>

          <!-- Social Links (placeholder) -->
          <div class="mt-5 flex justify-center gap-3 opacity-0 group-hover:opacity-100 transition-opacity">
            <button class="w-8 h-8 rounded-full bg-gray-700/50 flex items-center justify-center hover:bg-purple-600/30 transition-colors">
              <UIcon name="i-heroicons-link" class="w-4 h-4 text-gray-400" />
            </button>
            <button class="w-8 h-8 rounded-full bg-gray-700/50 flex items-center justify-center hover:bg-purple-600/30 transition-colors">
              <UIcon name="i-heroicons-envelope" class="w-4 h-4 text-gray-400" />
            </button>
          </div>
        </div>
      </div>

      <!-- Team Philosophy -->
      <div class="mt-16 bg-gradient-to-br from-purple-900/20 to-gray-800/30 rounded-2xl p-8 border border-purple-500/10">
        <div class="max-w-3xl mx-auto text-center">
          <UIcon name="i-heroicons-sparkles" class="w-8 h-8 text-amber-400 mx-auto mb-4" />
          <p class="text-xl text-gray-300 leading-relaxed italic">
            "Together, we transform diverse client requests into high-value solutions through an intelligent customization process."
          </p>
          <p class="text-purple-400 font-medium mt-4">— CakraSoft Team</p>
        </div>
      </div>
    </div>
  </section>
</template>
