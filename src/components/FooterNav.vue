<script setup lang="ts">
import LogoContainer from './cards/LogoContainer.vue'
import MenuLink from './cards/MenuLink.vue'
import FooterSocials from './cards/FooterSocials.vue'

interface MenuItem {
  id: number
  name: string
  href: string
}
const { handleMenu, isMenuOpen, menuItems } = defineProps<{
  handleMenu: () => void
  isMenuOpen: boolean
  menuItems: MenuItem[]
}>()
</script>

<template>
  <nav
    class="sm:grid-col-2 mt-10 grid w-full max-w-276 px-4 text-(--white) transition-all duration-500 ease-linear sm:mt-0"
    aria-label="Footer menu"
  >
    <LogoContainer :isMenuOpen :handleMenu />
    <ul
      class="flex w-full flex-col items-center justify-center gap-1 transition-all duration-500 ease-linear sm:col-start-1 sm:h-full sm:w-auto sm:flex-row sm:justify-start sm:gap-3 md:gap-5"
      aria-label="Menu links"
    >
      <MenuLink v-for="item in menuItems" :key="item.id" :handleMenu :item />
    </ul>
    <FooterSocials />
    <p
      class="self-baseline py-4 text-center text-(--grey200) sm:col-start-2 sm:row-start-2 sm:row-end-3 sm:text-right"
    >
      © 2021 Loopstudios. All rights reserved.
    </p>
  </nav>
</template>

<style scoped lang="scss"></style>
