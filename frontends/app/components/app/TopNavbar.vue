<script setup lang="ts">
const links = [
  { label: "Why Influencers?", to: "/why-influencers" },
  { label: "Pricing", to: "/pricing" },
  { label: "How it Works", to: "/how-it-works" },
  { label: "For Creators", to: "/for-creators" },
  { label: "Contact Us", to: "/contact" },
];

const isMenuVisible = ref(false);
</script>

<template>
  <div class="fixed top-0 z-50 w-full bg-white">
    <UContainer class="py-4">
      <nav class="flex items-center justify-between">
        <div class="items-center lg:flex">
          <AppLogo class="h-8" />

          <ul
            class="hidden ml-16 space-x-8 text-sm font-medium tracking-wider lg:flex"
          >
            <li v-for="link in links" :key="link.label">
              <ULink
                :to="link.to"
                class="transition-all duration-300 hover:text-indigo-500"
              >
                {{ link.label }}
              </ULink>
            </li>
          </ul>
        </div>
        <div class="flex items-center space-x-4">
          <BookDemo class="hidden sm:inline-block">
            Schedule a consultation
          </BookDemo>

          <SecondaryButton to="/login" class="hidden lg:inline-block">
            Login
          </SecondaryButton>

          <UPopover
            :open="isMenuVisible"
            :popper="{
              placement: 'bottom-end',
              width: 300,
              offsetDistance: 24,
            }"
          >
            <UButton
              icon="i-heroicons-bars-3-solid"
              color="black"
              variant="ghost"
              size="xl"
              class="lg:hidden"
              @click="isMenuVisible = true"
            />

            <template #panel>
              <div class="bg-white">
                <ul class="py-8 space-y-4 font-bold text-slate-600">
                  <li v-for="link in links" :key="link.label" class="px-8">
                    <ULink
                      :to="link.to"
                      class="transition-all duration-300 hover:text-indigo-500"
                      @click="isMenuVisible = false"
                    >
                      {{ link.label }}
                    </ULink>
                  </li>
                </ul>
                <div
                  class="border-t py-8 flex flex-col justify-center items-center w-[94vw]"
                >
                  <div class="sm:hidden">
                    <BookDemo class="w-42"> Schedule a consultation </BookDemo>
                  </div>
                  <div class="mt-8 sm:mt-0">
                    <SecondaryButton to="/login" variant="ghost" block>
                      Login
                    </SecondaryButton>
                  </div>
                </div>
              </div>
            </template>
          </UPopover>
        </div>
      </nav>
    </UContainer>
  </div>
</template>

<style scoped></style>
