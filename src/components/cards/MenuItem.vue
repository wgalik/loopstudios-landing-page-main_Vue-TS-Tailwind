<script setup lang="ts">
interface MenuItem {
  name: string
  href: string
}
const { handleMenu, item } = defineProps<{
  handleMenu: () => void
  item: MenuItem
}>()
</script>

<template>
  <li>
    <a
      :href="item.href"
      class="relative mx-4 mb-4 block text-xl normal-case sm:mx-0 sm:mb-0 sm:text-sm md:text-base"
      @click="handleMenu"
      >{{ item.name }}</a
    >
  </li>
</template>

<style scoped lang="scss">
header a {
  text-transform: uppercase;
  @media (min-width: 40rem) {
    font-family: 'Alata', sans-serif;
    font-weight: 400;
  }
  &:hover::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 50%;
    width: 50%;
    height: 1px;
    background-color: currentColor;
    transform: translateX(-50%);
    @media (min-width: 40rem) {
      bottom: -10px;
      height: 2px;
    }
  }
}
footer a {
  font-family: 'Alata', sans-serif;
  font-weight: 400;
  font-size: 1rem;
  padding: 1rem 0;

  &:hover::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 50%;
    width: 50%;
    height: 1px;
    background-color: currentColor;
    transform: translateX(-50%);
    @media (min-width: 40rem) {
      bottom: -10px;
      height: 2px;
    }
  }
}
</style>
