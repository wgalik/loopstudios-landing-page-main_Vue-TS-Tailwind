<script setup lang="ts">
const { content, img } = defineProps<{
  content: string
  img: string
}>()
</script>

<template>
  <article
    class="group relative grid h-full w-full cursor-pointer overflow-hidden bg-linear-to-t from-black/70 to-transparent text-(--white) transition duration-300 ease-in-out hover:text-(--black)"
  >
    <div
      id="gradient"
      class="absolute inset-0 z-1 bg-linear-to-t from-black/70 to-transparent transition duration-300 ease-in-out group-hover:from-white/70 group-hover:to-white/70"
    ></div>
    <img
      :src="img"
      :alt="content"
      class="z-0 col-start-1 col-end-2 row-start-1 row-end-2 h-full w-full object-cover object-center"
    />
    <h3
      class="z-1 col-start-1 col-end-2 row-start-1 row-end-2 w-[50%] self-end p-6 text-2xl leading-none sm:w-[70%] sm:text-xl md:text-2xl"
    >
      {{ content }}
    </h3>
  </article>
</template>

<style scoped lang="scss"></style>
