<script setup lang="ts">
const plans = [
  {
    name: 'Starter',
    price: 500,
    features: [
      '1 influencer visit per month',
      'Alternating High and Medium-exposure influencers',
      'Vetted, real creators from our network',
      'Scheduling & payment done for you',
      'Month-to-month basis; pause anytime'
    ],
    link: 'https://buy.stripe.com/3cs6oP9dRc233ja000',
  },
  {
    name: 'Growth',
    price: 700,
    highlight: true,
    features: [
      '1 influencer visit per month',
      'High-exposure influencers every month',
      'Vetted, real creators from our network',
      'Scheduling & payment done for you',
      'Month-to-month basis; pause anytime'
    ],
    link: 'https://buy.stripe.com/cN214v9dRgij2f6aEF',
  },
  {
    name: 'Custom',
    price: 1000,
    features: [
      '1 influencer visit per month',
      'Ability to choose influencers from our network',
      'Vetted, real creators from our network',
      'Scheduling & payment done for you',
      'Month-to-month basis; pause anytime'
    ],
    link: 'https://buy.stripe.com/00g8wX0HlaXZbPG146',
  },
  {
    name: 'Full',
    price: 2500,
    features: [
      'Social media management included',
      'Monthly content shoots and daily Instagram management',
      '1 influencer post per month',
      'Exposure on Instagram and TikTok',
      'High exposure influencers only',
      'Local influencers matched for you',
    ],
    link: 'https://buy.stripe.com/6oEeVl9dR1np4neeUX',
  },
]

const title = ref('We're investing in you, just as you are in us. - FoodiFy')

useHead({
  title,
  meta: [
    { name: 'description', content: 'Restaurant marketing redefined for the social media age.' },
  ],
})

useSharedSeoData({
  title,
})
</script>

<template>
  <UContainer class="my-32">
    <h1
      class="text-3xl leading-snug text-center heading md:text-4xl lg:text-5xl"
    >
      We're Investing in You,
      <span class="highlight">Just as You Are in Us.</span>
    </h1>

    <div
      class="flex flex-col mt-16 space-y-8 lg:flex-row lg:space-x-4 lg:space-y-0"
    >
      <SubscriptionPlan
        v-for="plan in plans"
        :key="plan.name"
        :plan="plan"
        class="lg:w-1/4"
      />
    </div>
  </UContainer>
</template>

<style scoped></style>
