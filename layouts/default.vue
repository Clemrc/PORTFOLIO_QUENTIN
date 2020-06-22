<template>
  <div class="app">
    <Infobar :title="title" />
    <nuxt />
    <!-- <Nav /> -->
  </div>
</template>

<script>
import Infobar from '@/components/infobar.vue'
// import Nav from '@/components/navbar.vue'
export default {
  components: {
    // Nav,
    Infobar
  },
  data() {
    return {
      title: 'PORTFOLIO'
    }
  }
}
</script>

<style>
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
  padding: 0px 0px 20px 0px;
  width: 85%;
  margin: 0 auto;
  border: 3px black;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: flex-start;
}
</style>
