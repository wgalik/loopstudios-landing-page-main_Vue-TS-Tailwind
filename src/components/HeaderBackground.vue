<script setup lang="ts">
import heroMobileImg from '../assets/images/mobile/image-hero.jpg'
import heroDesktopImg from '../assets/images/desktop/image-hero.jpg'

const { isSm, scrollY } = defineProps<{ isSm: boolean; scrollY: number }>()

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
    class="bg- absolute inset-0 z-1 h-[90dvh] w-full bg-cover bg-bottom bg-no-repeat"
    :style="{
      backgroundImage: `url(${isSm ? heroDesktopImg : heroMobileImg})`,
    }"
    aria-hidden="true"
  ></div>
</template>

<style scoped lang="scss"></style>
