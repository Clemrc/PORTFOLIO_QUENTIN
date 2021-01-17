<template>
  <div class="app" :class="mode">
    <div class="app-content">
      <Infobar :title="title" :mode="mode" @toggle="darkmode" />

      <nuxt class="nuxt" />

      <Footer />
    </div>
  </div>
</template>

<script>
import Infobar from '@/components/infobar.vue'
import Footer from '@/components/footer.vue'

export default {
  components: {
    Infobar,
    Footer
  },
  data() {
    return {
      title: 'DMQ',
      mode: 'light'
    }
  },
  methods: {
    darkmode() {
      if (this.mode === 'dark') {
        this.mode = 'light'
      } else {
        this.mode = 'dark'
      }
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
  font-family: 'Helvetica';
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

.app {
  height: 100%;
}

.app-content {
  min-height: 100vh;
  width: 85%;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: flex-start;
}

.nuxt {
  margin-top: 80px;
  width: 100%;
  height: calc(100vh - 80px);
}

footer {
  display: none;
}

/* DARK MODE */

.dark {
  background-color: #000000;
  transition: 0.5s;
}

/* MEDIAQUERIES */

@media screen and (min-width: 1000px) {
  .nuxt {
    margin-top: 100px;
    width: 100%;
    height: calc(100vh - 100px);
  }

  footer {
    display: block;
  }
}
</style>
