<script setup lang="ts">
useHead({
  title: "Contact Us - FoodiFy",
  meta: [
    { name: "description", content: "Get in touch with the FoodiFy team." },
  ],
});
</script>

<template>
  <div class="pt-24 pb-16 md:pt-32 md:pb-24 lg:pt-36 lg:pb-30">
    <UContainer>
      <div class="mx-auto max-w-3xl">
        <h1 class="mb-8 text-4xl font-bold tracking-tight text-gray-900">
          Contact Us
        </h1>

        <div class="max-w-none prose prose-slate prose-lg">
          <p class="mb-8 text-lg text-gray-600">
            Have questions or need assistance? We're here to help! Get in touch
            with our team using the contact information below.
          </p>

          <div class="p-8 mb-8 bg-gray-50 rounded-lg shadow-sm">
            <h2 class="mb-4 text-2xl font-semibold text-gray-900">Email Us</h2>
            <p class="mb-2 text-gray-600">For general inquiries:</p>
            <a
              href="mailto:contact@foodifyapp.com"
              class="text-primary-600 hover:text-primary-700 font-medium"
            >
              contact@foodifyapp.com
            </a>
          </div>

          <div class="p-8 bg-gray-50 rounded-lg shadow-sm">
            <h2 class="mb-4 text-2xl font-semibold text-gray-900">
              Response Time
            </h2>
            <p class="text-gray-600">
              We strive to respond to all inquiries within 24-48 hours during
              business days. For urgent matters, please include "URGENT" in your
              email subject line.
            </p>
          </div>
        </div>
      </div>
    </UContainer>
  </div>
</template>

<style scoped>
.prose h2 {
  @apply text-2xl font-semibold mt-12 mb-6 text-gray-900;
}
.prose p {
  @apply mb-6 text-gray-600;
}
</style>
