<script setup lang="ts">
const props = defineProps<{
  plan: object;
}>();

const openPaymentPage = () => {
  window.open(props.plan.link, "_blank", "rel=noopener noreferrer");
};

const renderFeature = (feature: string) => {
  // First sanitize the string by escaping HTML
  const escaped = feature
    .replace(/&/g, "&amp;")
    .replace(/</g, "&lt;")
    .replace(/>/g, "&gt;")
    .replace(/"/g, "&quot;")
    .replace(/'/g, "&#039;");

  // Then replace markdown bold with HTML strong tags
  return escaped.replace(/\*\*(.*?)\*\*/g, "<strong>$1</strong>");
};
</script>

<template>
  <div
    class="flex flex-col justify-between p-6 bg-white rounded-lg shadow-lg"
    :class="{ 'ring-2 ring-indigo-500': plan?.highlight }"
  >
    <div>
      <div class="">
        <div class="flex justify-between">
          <div class="text-xl font-medium">
            {{ plan.name }}
          </div>
          <div v-if="plan?.highlight">
            <span
              class="px-4 py-1 text-sm font-medium text-indigo-600 whitespace-nowrap bg-indigo-50 rounded-full"
              >Most popular</span
            >
          </div>
        </div>
        <div class="mt-2">
          <span class="text-3xl font-bold">${{ plan.price }}</span
          ><span class="text-slate-600">/month</span>
        </div>
      </div>
      <div class="mt-8">
        <ul class="space-y-4 text-sm">
          <li
            v-for="feature in plan.features"
            :key="feature"
            class="flex items-baseline space-x-3"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="16"
              height="16"
              viewBox="0 0 256 256"
              class="flex-shrink-0 mt-0.5 text-indigo-500"
            >
              <path
                fill="currentColor"
                d="m243.33 90.91l-128.41 128.4a16 16 0 0 1-22.63 0l-71.62-72a16 16 0 0 1 0-22.61l24-24a16 16 0 0 1 22.57-.06l36.64 35.27l.11.11l92.73-91.37a16 16 0 0 1 22.58 0l24 23.56a16 16 0 0 1 .03 22.7"
              />
            </svg>
            <span
              class="leading-snug text-slate-600"
              v-html="renderFeature(feature)"
            ></span>
          </li>
        </ul>
      </div>
    </div>
    <div>
      <PrimaryButton block class="mt-8" @click="openPaymentPage">
        Choose Plan
      </PrimaryButton>
    </div>
  </div>
</template>

<style scoped>
strong {
  @apply font-semibold text-gray-900;
}

.text-slate-600 :deep(strong) {
  @apply font-semibold text-gray-900;
}
</style>
