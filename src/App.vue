<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue'

import HeaderNav from './components/HeaderNav.vue'
import HeaderHero from './components/HeaderHero.vue'
import HeaderBackground from './components/HeaderBackground.vue'
import AboutSection from './components/AboutSection.vue'
import ProductsSection from './components/ProductsSection.vue'

import FooterNav from './components/FooterNav.vue'

const isSm = ref<boolean>(false)
const isMenuOpen = ref<boolean>(false)
const scrollY = ref<number>(0)

interface MenuItem {
  id: number
  name: string
  href: string
}
const menuItems: MenuItem[] = [
  { id: 1, name: 'About', href: '#about' },
  { id: 2, name: 'Careers', href: '#' },
  { id: 3, name: 'Events', href: '#' },
  { id: 4, name: 'Products', href: '#products' },
  { id: 5, name: 'Support', href: '#' },
]

const mediaQuery = window.matchMedia('(min-width: 40rem)')

const handleBreakpoint = () => (isSm.value = mediaQuery.matches)
const handleResize = () => {
  if (!isMenuOpen.value) return
  handleMenu()
}
const handleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
const handleScroll = () => (scrollY.value = window.scrollY)

onMounted(() => {
  handleBreakpoint()
  mediaQuery.addEventListener('change', handleBreakpoint)
  window.addEventListener('scroll', handleScroll)
  window.addEventListener('resize', handleResize)
})

onUnmounted(() => {
  mediaQuery.removeEventListener('change', handleBreakpoint)
  window.removeEventListener('scroll', handleScroll)
  window.removeEventListener('resize', handleResize)
})
</script>

<template>
  <header class="relative z-10 flex w-full items-center justify-center">
    <HeaderNav :handleMenu :isMenuOpen :menuItems :scrollY />
    <HeaderHero />
    <HeaderBackground :isSm :scrollY />
  </header>
  <main class="grid w-full justify-center gap-20">
    <AboutSection :isSm />
    <ProductsSection :isSm />
  </main>
  <footer
    class="mt-20 flex min-h-50 w-full flex-col items-center justify-center bg-(--black)"
  >
    <FooterNav :handleMenu :isMenuOpen :menuItems class="" />
  </footer>
</template>

<style scoped lang="scss"></style>
