<script setup lang="ts">
const { isSm } = defineProps<{ isSm: boolean }>()

import aboutMoblieImg from '../assets/images/mobile/image-interactive.jpg'
import aboutDesktopImg from '../assets/images/desktop/image-interactive.jpg'

const imageMobile: string = aboutMoblieImg
const imageDesktop: string = aboutDesktopImg
</script>

<template>
  <section
    id="about"
    class="grid w-full max-w-276 px-4 pt-20 sm:grid-cols-4 sm:grid-rows-3 sm:pt-25"
  >
    <img v-if="!isSm" :src="imageMobile" alt="Image interactive" />
    <img
      v-else
      :src="imageDesktop"
      alt="Image interactive"
      class="z-0 h-full w-full object-cover"
    />

    <article
      class="z-1 grid bg-(--white) sm:row-start-2 sm:row-end-3 sm:grid-rows-subgrid sm:ps-20"
    >
      <h2
        class="mt-12 text-center text-4xl uppercase sm:row-start-1 sm:row-end-2 sm:mt-0 sm:self-end sm:text-start sm:text-[clamp(2rem,4vw,3rem)]"
      >
        The leader in interactive VR
      </h2>
      <p
        class="py-5 text-center text-base leading-8 text-(--grey200) sm:row-start-2 sm:row-end-3 sm:self-end sm:py-0 sm:text-start"
      >
        Founded in 2011, Loopstudios has been producing world-class virtual
        reality projects for some of the best companies around the globe. Our
        award-winning creations have transformed businesses through digital
        experiences that bind to their brand.
      </p>
    </article>
  </section>
</template>

<style scoped lang="scss">
@media (min-width: 40rem) {
  img {
    grid-area: 1 /1 /4 /4;
  }
  article {
    grid-area: 2 /3 /5 /5;
  }
}
</style>
