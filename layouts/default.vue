<template>
  <div class="app">
    <no-ssr>
      <Infobar :title="title" />
    </no-ssr>

    <nuxt class="nuxt" />

    <no-ssr>
      <Footer />
    </no-ssr>
  </div>
</template>

<script>
import Infobar from '@/components/infobar.vue'
import Footer from '@/components/footer.vue'
// import Nav from '@/components/navbar.vue'
export default {
  components: {
    // Nav,
    Infobar,
    Footer
  },
  data() {
    return {
      title: 'PORTFOLIO'
    }
  }
}
</script>

<style scoped>
*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

html {
  font-family: 'Montserrat', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

.app {
  min-height: 100vh;
  width: 85%;
  margin: 0 auto;
  border: 3px black;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: flex-start;
}

.nuxt {
  margin-top: 80px;
  width: 100%;
}

footer {
  display: none;
}

@media screen and (min-width: 1000px) {
  .nuxt {
    margin-top: 110px;
    margin-bottom: 110px;
  }

  footer {
    display: block;
  }
}
</style>
