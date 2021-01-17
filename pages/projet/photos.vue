<template>
  <div>
    <div class="container">
      <div class="content">
        <div class="title-content">
          <h1 class="title">Photos</h1>
        </div>
        <div class="photos-content">
          <div class="img">
            <img src="/IMG_2427.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_2500.jpg" alt="" />
          </div>
          <!-- <div class="img">
            <img src="/IMG_2548.jpg" alt="" />
          </div> -->
          <div class="img">
            <img src="/IMG_2642.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_2771.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_3042.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_3056.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_3131.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_3147.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_3157.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_3184.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_3531.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_4008.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_4032.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_5295.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_5312.jpg" alt="" />
          </div>
          <div class="img">
            <img src="/IMG_5637.jpg" alt="" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { TimelineLite } from 'gsap'
export default {
  transition: 'slide-fade',
  mounted() {
    const tl = new TimelineLite()
    tl.from('.img', {
      duration: 1,
      delay: 0.2,
      opacity: 0,
      y: 200,
      ease: 'expo',
      stagger: {
        each: 0.1,
        from: 'start'
      }
    })
  },
  beforeRouteLeave(to, from, next) {
    const tl = new TimelineLite()
    tl.to('.img', {
      duration: 0.5,
      opacity: 0,
      y: 50,
      ease: 'expo',
      onComplete: () => {
        next()
      }
    })
  },
  head() {
    return {
      title: 'Quentin Demaria - contact',
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
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  flex-direction: column;
  width: 100%;
}

.title-content {
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
}

.projects-content {
  margin: 10px;
  width: 20px;
  height: 20px;
  background-color: black;
}

.title {
  font-weight: 400;
  font-size: 80px;
  color: black;
  margin-bottom: 0;
}

.dark .title {
  color: white;
  transition: 0.5s;
}

.square {
  width: 13px;
  height: 13px;
  background-color: black;
  margin-left: 14px;
  margin-bottom: 20px;
}

.photos-content {
  margin-top: 30px;
  margin-bottom: 100px;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

.img {
  width: 300px;
  padding: 20px;
}
</style>
