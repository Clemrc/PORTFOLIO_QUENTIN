<template>
  <client-only>
    <header>
      <section class="hero">
        <div class="hero-body">
          <div class="container">
            <h2 class="title">{{ title }}</h2>
          </div>
        </div>
      </section>
      <div class="line"></div>
      <div id="_progress"></div>
    </header>
  </client-only>
</template>

<script>
import gsap from 'gsap'
export default {
  props: {
    title: String
  },
  updated() {
    gsap.from('.hero', {
      duration: 1.5,
      opacity: 0,
      y: 50,
      ease: 'expo'
    })
    gsap.from('.line', {
      duration: 1.5,
      opacity: 0,
      y: 100,
      ease: 'expo'
    })
  },
  mounted() {
    document.addEventListener('scroll', function() {
      const scrollTop =
        document.documentElement.scrollTop || document.body.scrollTop

      const scrollBottom =
        (document.documentElement.scrollHeight || document.body.scrollHeight) -
        document.documentElement.clientHeight

      const scrollPercent = (scrollTop / scrollBottom) * 100 + '%'
      const scrollPercentDecimal = Math.round((scrollTop / scrollBottom) * 100)

      document
        .getElementById('_progress')
        .style.setProperty('--scroll', scrollPercent)

      document.getElementById('_percent').innerHTML = scrollPercentDecimal
    })
  }
}
</script>

<style scoped lang="scss">
header {
  width: 85%;
  position: fixed;
  background-color: white;
  z-index: 10;
}

.line {
  height: 1px;
  width: 100%;
  background-color: black;
}

.container {
  margin: 0;
  display: flex;
}

#_progress {
  --scroll: 0%;
  background: linear-gradient(
    to right,
    rgb(0, 0, 0) var(--scroll),
    transparent 0
  );
  position: fixed;
  width: 100%;
  height: 5px;
  right: 0px;
  top: 0px;
  z-index: 100;
}
</style>
