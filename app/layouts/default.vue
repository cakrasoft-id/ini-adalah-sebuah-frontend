<script setup lang="ts">
import { companyInfo, navLinks } from '~/data/profile'

const isMenuOpen = ref(false)

const scrollToSection = (href: string) => {
  isMenuOpen.value = false
  const element = document.querySelector(href)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<template>
  <div class="min-h-screen bg-gray-950 text-white">
    <!-- Navigation -->
    <header class="fixed top-0 left-0 right-0 z-50 bg-gray-950/80 backdrop-blur-lg border-b border-gray-800">
      <nav class="container mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex items-center justify-between h-16">
          <!-- Logo -->
          <a href="#home" class="flex items-center gap-2" @click.prevent="scrollToSection('#home')">
            <div class="w-10 h-10 rounded-full bg-gradient-to-br from-purple-600 to-purple-800 flex items-center justify-center">
              <span class="text-amber-400 font-bold text-lg">C</span>
            </div>
            <span class="text-xl font-bold text-white">{{ companyInfo.name }}</span>
          </a>

          <!-- Desktop Navigation -->
          <div class="hidden md:flex items-center gap-6">
            <a
              v-for="link in navLinks"
              :key="link.href"
              :href="link.href"
              class="text-gray-300 hover:text-amber-400 transition-colors text-sm font-medium"
              @click.prevent="scrollToSection(link.href)"
            >
              {{ link.label }}
            </a>
            <UButton color="primary" variant="solid" size="sm">
              Get Started
            </UButton>
          </div>

          <!-- Mobile Menu Button -->
          <button
            class="md:hidden p-2 text-gray-300 hover:text-white"
            @click="isMenuOpen = !isMenuOpen"
          >
            <UIcon :name="isMenuOpen ? 'i-heroicons-x-mark' : 'i-heroicons-bars-3'" class="w-6 h-6" />
          </button>
        </div>

        <!-- Mobile Navigation -->
        <div v-if="isMenuOpen" class="md:hidden py-4 border-t border-gray-800">
          <div class="flex flex-col gap-4">
            <a
              v-for="link in navLinks"
              :key="link.href"
              :href="link.href"
              class="text-gray-300 hover:text-amber-400 transition-colors text-sm font-medium"
              @click.prevent="scrollToSection(link.href)"
            >
              {{ link.label }}
            </a>
            <UButton color="primary" variant="solid" size="sm" class="w-fit">
              Get Started
            </UButton>
          </div>
        </div>
      </nav>
    </header>

    <!-- Main Content -->
    <main>
      <slot />
    </main>

    <!-- Footer -->
    <footer class="bg-gray-900 border-t border-gray-800">
      <div class="container mx-auto px-4 sm:px-6 lg:px-8 py-12">
        <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
          <!-- Company Info -->
          <div class="md:col-span-2">
            <div class="flex items-center gap-2 mb-4">
              <div class="w-10 h-10 rounded-full bg-gradient-to-br from-purple-600 to-purple-800 flex items-center justify-center">
                <span class="text-amber-400 font-bold text-lg">C</span>
              </div>
              <span class="text-xl font-bold text-white">{{ companyInfo.name }}</span>
            </div>
            <p class="text-gray-400 text-sm mb-4 max-w-md">
              {{ companyInfo.tagline }}
            </p>
            <p class="text-gray-500 text-sm">
              {{ companyInfo.location }}
            </p>
          </div>

          <!-- Quick Links -->
          <div>
            <h4 class="text-white font-semibold mb-4">Quick Links</h4>
            <ul class="space-y-2">
              <li v-for="link in navLinks" :key="link.href">
                <a
                  :href="link.href"
                  class="text-gray-400 hover:text-amber-400 text-sm transition-colors"
                  @click.prevent="scrollToSection(link.href)"
                >
                  {{ link.label }}
                </a>
              </li>
            </ul>
          </div>

          <!-- Contact -->
          <div>
            <h4 class="text-white font-semibold mb-4">Contact Us</h4>
            <ul class="space-y-2 text-sm">
              <li class="flex items-center gap-2 text-gray-400">
                <UIcon name="i-heroicons-globe-alt" class="w-4 h-4 text-purple-400" />
                <a :href="`https://${companyInfo.website}`" target="_blank" class="hover:text-amber-400 transition-colors">
                  {{ companyInfo.website }}
                </a>
              </li>
              <li class="flex items-center gap-2 text-gray-400">
                <UIcon name="i-heroicons-phone" class="w-4 h-4 text-purple-400" />
                <a :href="`tel:${companyInfo.phone}`" class="hover:text-amber-400 transition-colors">
                  {{ companyInfo.phone }}
                </a>
              </li>
              <li class="flex items-center gap-2 text-gray-400">
                <UIcon name="i-heroicons-envelope" class="w-4 h-4 text-purple-400" />
                <a :href="`mailto:${companyInfo.email}`" class="hover:text-amber-400 transition-colors">
                  {{ companyInfo.email }}
                </a>
              </li>
            </ul>
          </div>
        </div>

        <!-- Copyright -->
        <div class="mt-12 pt-8 border-t border-gray-800 text-center">
          <p class="text-gray-500 text-sm">
            © {{ new Date().getFullYear() }} {{ companyInfo.name }}. All rights reserved.
          </p>
        </div>
      </div>
    </footer>
  </div>
</template>
