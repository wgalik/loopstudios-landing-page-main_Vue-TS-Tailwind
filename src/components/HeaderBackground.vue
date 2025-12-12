<script setup lang="ts">
const { scrollY } = defineProps<{
  scrollY: number
}>()
</script>

<template>
  <div
    id="menu-background"
    :class="scrollY ? 'bg-(--black)' : ''"
    class="fixed top-0 z-10 flex h-25 w-full transition duration-500 ease-linear"
    aria-hidden="true"
  ></div>
  <div
    id="hero-background"
    class="absolute inset-0 z-1 h-[90dvh] w-full bg-cover bg-bottom bg-no-repeat"
    aria-hidden="true"
  ></div>
</template>

<style scoped lang="scss">
#hero-background {
  background-image: url('../images/mobile/image-hero.jpg');
  @media (min-width: 40rem) {
    background-image: url('../images/desktop/image-hero.jpg');
  }
}
</style>
