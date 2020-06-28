<template>
  <header>
    <section class="hero">
      <div class="hero-body">
        <div class="container">
          <nuxt-link to="/">
            <h2 class="title">{{ title }}</h2>
          </nuxt-link>
          <nav>
            <ul>
              <li>
                <nuxt-link to="/projets" class="link">Projets</nuxt-link>
              </li>
              <li>
                <nuxt-link to="/contact" class="link">Contact</nuxt-link>
              </li>
              <li>
                <toggle :mode="mode" @toggle="$emit('toggle')" />
              </li>
            </ul>
          </nav>
        </div>
      </div>
    </section>
    <div class="line"></div>
    <div id="_progress"></div>
  </header>
</template>

<script>
import gsap from 'gsap'
import toggle from '@/components/toggle.vue'
export default {
  components: {
    toggle
  },
  props: {
    title: String,
    mode: String
  },
  mounted() {
    gsap.from('.hero', {
      delay: 3,
      duration: 1.5,
      opacity: 0,
      y: -50,
      ease: 'expo'
    })
    gsap.from('.line', {
      delay: 3,
      duration: 1,
      opacity: 0,
      y: -100,
      ease: 'expo'
    })
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

.hero-body {
  padding: 1rem 0rem;
}

.line {
  height: 1px;
  width: 100%;
  background-color: black;
}

.container {
  max-width: 100%;
  margin: 0;
  display: flex;
  justify-content: space-between;
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

// DARK MODE

.dark header {
  background-color: #000000;
  transition: 0.5s;
}

.dark .title {
  color: white;
  transition: 0.5s;
}

.dark .line {
  background-color: white;
  transition: 0.5s;
}

.dark #_progress {
  background: linear-gradient(
    to right,
    rgb(255, 255, 255) var(--scroll),
    transparent 0
  );
}

// MEDIAQUERIES

@media screen and (min-width: 1000px) {
  .hero-body {
    padding: 1.5rem 0rem;
  }

  nav {
    display: flex;
    align-items: center;
  }

  nav ul {
    display: flex;
  }

  nav ul li {
    margin-left: 10px;
  }

  nav ul li:not(:last-child) {
    margin-right: 10px;
  }

  nav ul li a {
    color: #192734;
  }

  .dark nav ul li a {
    color: white;
  }
}
</style>
