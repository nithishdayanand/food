<script setup lang="ts">
const plans = [
  {
    name: "Starter",
    price: 500,
    features: [
      "**1 influencer visit** per month",
      "Alternating **High and Medium-exposure** influencers",
      "**Vetted, real creators** from our network",
      "**Scheduling & payment** done for you",
      "Month-to-month basis; **pause anytime**",
    ],
    link: "https://buy.stripe.com/3cs6oP9dRc233ja000",
  },
  {
    name: "Growth",
    price: 700,
    highlight: true,
    features: [
      "**1 influencer visit** per month",
      "**High-exposure influencers** every month",
      "**Vetted, real creators** from our network",
      "**Scheduling & payment** done for you",
      "Month-to-month basis; **pause anytime**",
    ],
    link: "https://buy.stripe.com/cN214v9dRgij2f6aEF",
  },
  {
    name: "Custom",
    price: 1000,
    features: [
      "**1 influencer visit** per month",
      "**Ability to choose** influencers from our network",
      "**Vetted, real creators** from our network",
      "**Scheduling & payment** done for you",
      "Month-to-month basis; **pause anytime**",
    ],
    link: "https://buy.stripe.com/00g8wX0HlaXZbPG146",
  },
];

const title = ref("We're investing in you, just as you are in us. - FoodiFy");

useHead({
  title,
  meta: [
    {
      name: "description",
      content: "Restaurant marketing redefined for the social media age.",
    },
  ],
});

useSharedSeoData({
  title,
});
</script>

<template>
  <UContainer class="py-24 md:py-32 lg:py-36">
    <h1
      class="text-3xl leading-snug text-center heading md:text-4xl lg:text-5xl"
    >
      We're Investing in You,
      <span class="highlight">Just as You Are in Us.</span>
    </h1>

    <div
      class="flex flex-col justify-center items-center mx-auto mt-16 max-w-6xl lg:flex-row lg:items-stretch lg:space-x-8"
    >
      <SubscriptionPlan
        v-for="plan in plans"
        :key="plan.name"
        :plan="plan"
        class="w-full max-w-md lg:w-1/3"
      />
    </div>
  </UContainer>
</template>

<style scoped>
.highlight {
  @apply text-primary-600;
}
</style>
