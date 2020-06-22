<template>
  <div class="container">
    <client-only>
      <div class="content">
        <div class="title-content">
          <h1 class="title">Book</h1>
          <div class="square"></div>
        </div>
        <div class="projects-content"></div>
      </div>
    </client-only>
  </div>
</template>

<script>
import gsap from 'gsap'
export default {
  transition: 'slide-fade',
  updated() {
    gsap.from('.content', {
      duration: 1.5,
      opacity: 0,
      y: 50,
      ease: 'expo'
    })
  },
  head() {
    return {
      title: 'Quentin Demaria',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'portfolio de Quentin Demaria'
        },
        {
          name: 'keyword',
          content: 'Quentin Demaria, Quentin Demaria portfolio'
        }
      ]
    }
  }
}
</script>

<style scoped>
.content {
  position: absolute;
  bottom: 0;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
}

.title-content {
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
}

.title {
  font-weight: 400;
  font-size: 110px;
  color: black;
  margin-bottom: 0;
}

.square {
  width: 13px;
  height: 13px;
  background-color: black;
  margin-left: 14px;
  margin-bottom: 20px;
}

.container {
  height: 2000px;
  width: 100%;
  position: relative;
}
</style>
