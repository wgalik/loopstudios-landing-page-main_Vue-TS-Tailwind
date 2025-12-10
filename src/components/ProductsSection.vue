<script setup lang="ts">
import GalleryCard from './cards/GalleryCard.vue'

import imgMobile_1 from '../assets/images/mobile/image-deep-earth.jpg'
import imgMobile_2 from '../assets/images/mobile/image-night-arcade.jpg'
import imgMobile_3 from '../assets/images/mobile/image-soccer-team.jpg'
import imgMobile_4 from '../assets/images/mobile/image-grid.jpg'
import imgMobile_5 from '../assets/images/mobile/image-from-above.jpg'
import imgMobile_6 from '../assets/images/mobile/image-pocket-borealis.jpg'
import imgMobile_7 from '../assets/images/mobile/image-curiosity.jpg'
import imgMobile_8 from '../assets/images/mobile/image-fisheye.jpg'

import imgDesktop_1 from '../assets/images/desktop/image-deep-earth.jpg'
import imgDesktop_2 from '../assets/images/desktop/image-night-arcade.jpg'
import imgDesktop_3 from '../assets/images/desktop/image-soccer-team.jpg'
import imgDesktop_4 from '../assets/images/desktop/image-grid.jpg'
import imgDesktop_5 from '../assets/images/desktop/image-from-above.jpg'
import imgDesktop_6 from '../assets/images/desktop/image-pocket-borealis.jpg'
import imgDesktop_7 from '../assets/images/desktop/image-curiosity.jpg'
import imgDesktop_8 from '../assets/images/desktop/image-fisheye.jpg'

const { isSm } = defineProps<{ isSm: boolean }>()

interface Articule {
  id: number
  content: string
  imgMobile: string
  imgDesktop: string
}

const articules: Articule[] = [
  {
    id: 1,
    content: 'Deep earth',
    imgMobile: imgMobile_1,
    imgDesktop: imgDesktop_1,
  },
  {
    id: 2,
    content: 'Night arcade',
    imgMobile: imgMobile_2,
    imgDesktop: imgDesktop_2,
  },
  {
    id: 3,
    content: 'Soccer team VR',
    imgMobile: imgMobile_3,
    imgDesktop: imgDesktop_3,
  },
  {
    id: 4,
    content: 'The grid',
    imgMobile: imgMobile_4,
    imgDesktop: imgDesktop_4,
  },
  {
    id: 5,
    content: 'From up above VR',
    imgMobile: imgMobile_5,
    imgDesktop: imgDesktop_5,
  },
  {
    id: 6,
    content: 'Pocket borealis',
    imgMobile: imgMobile_6,
    imgDesktop: imgDesktop_6,
  },
  {
    id: 7,
    content: 'The curiosity',
    imgMobile: imgMobile_7,
    imgDesktop: imgDesktop_7,
  },
  {
    id: 8,
    content: 'Make it fisheye',
    imgMobile: imgMobile_8,
    imgDesktop: imgDesktop_8,
  },
]
</script>

<template>
  <section
    id="products"
    class="flex w-full max-w-276 flex-col items-center justify-center px-4 sm:flex-row sm:flex-wrap sm:justify-start"
  >
    <h2
      class="text-4xl uppercase sm:order-1 sm:basis-1/2 sm:text-[clamp(2rem,4vw,3rem)]"
    >
      Our creations
    </h2>

    <div class="grid gap-4 py-8 sm:order-3 sm:grid-cols-4 sm:grid-rows-2">
      <GalleryCard
        v-for="articule in articules"
        :key="articule.id"
        :content="articule.content"
        :img="isSm ? articule.imgDesktop : articule.imgMobile"
      />
    </div>
    <button
      type="button"
      class="cursor-pointer self-center border-2 border-(--black) p-2 px-8 transition duration-300 ease-in-out hover:bg-(--black) hover:text-(--white) sm:order-2 sm:ms-auto"
    >
      See all
    </button>
  </section>
</template>

<style scoped lang="scss"></style>
