<script setup lang="ts">
import { companyInfo } from '~/data/profile'

const formData = ref({
  name: '',
  email: '',
  company: '',
  message: ''
})

const isSubmitting = ref(false)

const handleSubmit = async () => {
  isSubmitting.value = true
  // Simulate form submission
  await new Promise(resolve => setTimeout(resolve, 1000))
  alert('Thank you for your message! We will get back to you soon.')
  formData.value = { name: '', email: '', company: '', message: '' }
  isSubmitting.value = false
}
</script>

<template>
  <section id="contact" class="py-24 bg-gray-900/50">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <div class="inline-flex items-center gap-2 px-4 py-2 bg-purple-500/10 rounded-full border border-purple-500/20 mb-4">
          <UIcon name="i-heroicons-chat-bubble-left-right" class="w-4 h-4 text-purple-400" />
          <span class="text-purple-400 text-sm font-medium">Get in Touch</span>
        </div>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">
          Contact <span class="text-purple-400">Us</span>
        </h2>
        <p class="text-gray-400 max-w-2xl mx-auto">
          Ready to transform your business? Let's start a conversation.
        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-12">
        <!-- Contact Info -->
        <div class="space-y-8">
          <div>
            <h3 class="text-2xl font-semibold text-white mb-6">
              Let's Build Something Amazing Together
            </h3>
            <p class="text-gray-400 leading-relaxed">
              Whether you have a project in mind or just want to explore possibilities, 
              we're here to help. Reach out to us through any of the channels below, 
              or fill out the form and we'll get back to you within 24 hours.
            </p>
          </div>

          <!-- Contact Cards -->
          <div class="space-y-4">
            <a 
              :href="`https://${companyInfo.website}`" 
              target="_blank"
              class="flex items-center gap-4 p-4 bg-gray-800/30 rounded-xl border border-gray-700/30 hover:border-purple-500/30 transition-colors group"
            >
              <div class="w-12 h-12 rounded-lg bg-purple-500/20 flex items-center justify-center group-hover:bg-purple-500/30 transition-colors">
                <UIcon name="i-heroicons-globe-alt" class="w-6 h-6 text-purple-400" />
              </div>
              <div>
                <p class="text-gray-500 text-sm">Website</p>
                <p class="text-white font-medium">{{ companyInfo.website }}</p>
              </div>
            </a>

            <a 
              :href="`tel:${companyInfo.phone}`"
              class="flex items-center gap-4 p-4 bg-gray-800/30 rounded-xl border border-gray-700/30 hover:border-purple-500/30 transition-colors group"
            >
              <div class="w-12 h-12 rounded-lg bg-amber-500/20 flex items-center justify-center group-hover:bg-amber-500/30 transition-colors">
                <UIcon name="i-heroicons-phone" class="w-6 h-6 text-amber-400" />
              </div>
              <div>
                <p class="text-gray-500 text-sm">Phone</p>
                <p class="text-white font-medium">{{ companyInfo.phone }}</p>
              </div>
            </a>

            <a 
              :href="`mailto:${companyInfo.email}`"
              class="flex items-center gap-4 p-4 bg-gray-800/30 rounded-xl border border-gray-700/30 hover:border-purple-500/30 transition-colors group"
            >
              <div class="w-12 h-12 rounded-lg bg-purple-500/20 flex items-center justify-center group-hover:bg-purple-500/30 transition-colors">
                <UIcon name="i-heroicons-envelope" class="w-6 h-6 text-purple-400" />
              </div>
              <div>
                <p class="text-gray-500 text-sm">Email</p>
                <p class="text-white font-medium">{{ companyInfo.email }}</p>
              </div>
            </a>

            <div class="flex items-center gap-4 p-4 bg-gray-800/30 rounded-xl border border-gray-700/30">
              <div class="w-12 h-12 rounded-lg bg-gray-600/20 flex items-center justify-center">
                <UIcon name="i-heroicons-map-pin" class="w-6 h-6 text-gray-400" />
              </div>
              <div>
                <p class="text-gray-500 text-sm">Location</p>
                <p class="text-white font-medium">{{ companyInfo.location }}</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Contact Form -->
        <div class="bg-gray-800/30 rounded-2xl p-8 border border-gray-700/30">
          <h3 class="text-xl font-semibold text-white mb-6">Send us a Message</h3>
          
          <form class="space-y-5" @submit.prevent="handleSubmit">
            <div>
              <label class="block text-gray-400 text-sm mb-2">Your Name</label>
              <UInput
                v-model="formData.name"
                placeholder="John Doe"
                size="lg"
                required
              />
            </div>

            <div>
              <label class="block text-gray-400 text-sm mb-2">Email Address</label>
              <UInput
                v-model="formData.email"
                type="email"
                placeholder="john@example.com"
                size="lg"
                required
              />
            </div>

            <div>
              <label class="block text-gray-400 text-sm mb-2">Company (Optional)</label>
              <UInput
                v-model="formData.company"
                placeholder="Your Company Name"
                size="lg"
              />
            </div>

            <div>
              <label class="block text-gray-400 text-sm mb-2">Message</label>
              <UTextarea
                v-model="formData.message"
                placeholder="Tell us about your project or inquiry..."
                :rows="4"
                size="lg"
                required
              />
            </div>

            <UButton
              type="submit"
              color="primary"
              size="lg"
              block
              :loading="isSubmitting"
              trailing-icon="i-heroicons-paper-airplane"
            >
              Send Message
            </UButton>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>
