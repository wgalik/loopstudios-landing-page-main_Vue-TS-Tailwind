<script setup lang="ts">
import HamburgerButton from './cards/HamburgerButton.vue'
import LogoContainer from './cards/LogoContainer.vue'
import MenuLink from './cards/MenuLink.vue'

interface MenuItem {
  id: number
  name: string
  href: string
}
const { isMenuOpen, handleMenu, menuItems } = defineProps<{
  handleMenu: () => void
  isMenuOpen: boolean
  menuItems: MenuItem[]
  scrollY: number
}>()
</script>

<template>
  <nav
    id="main-menu"
    class="fixed top-0 z-20 flex h-25 w-full max-w-276 items-center justify-between px-4 text-(--white) transition-all duration-500 ease-linear"
    aria-label="Main menu"
  >
    <LogoContainer :isMenuOpen :handleMenu />
    <ul
      class="absolute top-0 flex h-dvh w-dvw shrink-2 flex-col items-start justify-start gap-1 bg-(--black) transition-all duration-500 ease-linear sm:static sm:h-full sm:w-auto sm:flex-row sm:items-center sm:justify-end sm:gap-5 sm:bg-transparent md:gap-7"
      :class="isMenuOpen ? 'left-0' : '-left-160'"
      :aria-hidden="!isMenuOpen"
    >
      <MenuLink
        v-for="item in menuItems"
        :key="item.id"
        :handleMenu
        :item
        class="first-of-type:mt-[25vh] sm:first-of-type:mt-0"
      />
    </ul>
    <HamburgerButton :isMenuOpen :handleMenu />
  </nav>
</template>

<style scoped lang="scss"></style>
