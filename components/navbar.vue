<template>
  <client-only>
    <nav>
      <ul>
        <li>
          <nuxt-link to="/">Acceuil</nuxt-link>
        </li>
      </ul>
    </nav>
  </client-only>
</template>

<script>
import gsap from 'gsap'
export default {
  updated() {
    gsap.from('nav', {
      duration: 1,
      opacity: 0,
      x: 100,
      ease: 'expo'
    })
  }
}
</script>

<style scoped></style>
