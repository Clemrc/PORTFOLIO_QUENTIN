<template>
  <div>
    <div class="container">
      <div class="content">
        <!-- Entrance -->
        <div class="entrance">
          <img src="/DMQ.png" />
        </div>

        <!-- Acceuil -->
        <transition name="slide-fade">
          <div v-if="show" class="content-list">
            <div class="acceuil">
              <div class="title-content">
                <h1 class="title">QUENTIN DEMARIA</h1>
                <div class="square"></div>
              </div>
              <div class="title-content">
                <h1 class="job">Designer graphique</h1>
              </div>
              <div class="title-content">
                <h1 class="place">ORLEANS</h1>
              </div>
              <!-- <div class="projects-content"></div> -->
            </div>
            <div class="acceuil">
              <div class="title-content">
                <h1 class="title">QUENTIN DEMARIA</h1>
                <div class="square"></div>
              </div>
              <div class="title-content">
                <h1 class="job">Designer graphique</h1>
              </div>
              <div class="title-content">
                <h1 class="place">ORLEANS</h1>
              </div>
              <!-- <div class="projects-content"></div> -->
            </div>
            <div class="acceuil">
              <div class="title-content">
                <h1 class="title">QUENTIN DEMARIA</h1>
                <div class="square"></div>
              </div>
              <div class="title-content">
                <h1 class="job">Designer graphique</h1>
              </div>
              <div class="title-content">
                <h1 class="place">ORLEANS</h1>
              </div>
              <!-- <div class="projects-content"></div> -->
            </div>
            <div class="acceuil">
              <div class="title-content">
                <h1 class="title">QUENTIN DEMARIA</h1>
                <div class="square"></div>
              </div>
              <div class="title-content">
                <h1 class="job">Designer graphique</h1>
              </div>
              <div class="title-content">
                <h1 class="place">ORLEANS</h1>
              </div>
              <!-- <div class="projects-content"></div> -->
            </div>
            <div class="acceuil">
              <div class="title-content">
                <h1 class="title">QUENTIN DEMARIA</h1>
                <div class="square"></div>
              </div>
              <div class="title-content">
                <h1 class="job">Designer graphique</h1>
              </div>
              <div class="title-content">
                <h1 class="place">ORLEANS</h1>
              </div>
              <!-- <div class="projects-content"></div> -->
            </div>
            <div class="acceuil">
              <div class="title-content">
                <h1 class="title">QUENTIN DEMARIA</h1>
                <div class="square"></div>
              </div>
              <div class="title-content">
                <h1 class="job">Designer graphique</h1>
              </div>
              <div class="title-content">
                <h1 class="place">ORLEANS</h1>
              </div>
              <!-- <div class="projects-content"></div> -->
            </div>
            <div class="acceuil">
              <div class="title-content">
                <h1 class="title">QUENTIN DEMARIA</h1>
                <div class="square"></div>
              </div>
              <div class="title-content">
                <h1 class="job">Designer graphique</h1>
              </div>
              <div class="title-content">
                <h1 class="place">ORLEANS</h1>
              </div>
              <!-- <div class="projects-content"></div> -->
            </div>
          </div>
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
import { TimelineMax } from 'gsap'
export default {
  transition: 'slide-fade',
  data() {
    return {
      show: false
    }
  },
  mounted() {
    const tl = new TimelineMax()

    tl.to('.entrance', {
      delay: 1,
      duration: 1.5,
      opacity: 1,
      y: 120,
      ease: 'expo'
    })
      .to('.entrance', {
        delay: 0.5,
        duration: 1,
        opacity: 0,
        y: 80,
        ease: 'expo'
      })
      .call(this.removeElement('.entrance'))
      .call(this.showContent(this))
  },
  methods: {
    removeElement: (element) => {
      if (typeof element === 'string') {
        element = document.querySelector(element)
      }
      return function() {
        element.parentNode.removeChild(element)
      }
    },
    showContent: (c) => {
      return function() {
        c.show = true
      }
    }
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
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  flex-direction: column;
  width: 100%;
}

.entrance {
  opacity: 0;
  width: 100%;
  display: flex;
  justify-content: center;
}

.entrance img {
  width: 50%;
}

.name {
  font-weight: 400;
  font-size: 200px;
  color: black;
  margin-bottom: 0;
}

.title-content {
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
  margin-bottom: 10px;
}

.projects-content {
  margin: 0 auto;
  width: 80%;
  height: 1000px;
  border: 1px solid black;
}

.title {
  font-weight: 400;
  font-size: 110px;
  color: black;
  margin-bottom: 0;
}

.job {
  font-weight: 100;
  font-size: 60px;
  color: black;
  margin-bottom: 0;
}

.place {
  font-weight: 100;
  font-size: 16px;
  color: black;
  margin-top: 10px;
}

.square {
  display: none;
}

/* DARK MODE */

.dark .title {
  color: white;
  transition: 0.5s;
}

.dark .place {
  color: white;
  transition: 0.5s;
}

.dark .job {
  color: white;
  transition: 0.5s;
}

.dark .square {
  background-color: white;
  transition: 0.5s;
}

/* MEDIAQUERIES */

@media screen and (min-width: 1000px) {
  .square {
    width: 13px;
    height: 13px;
    background-color: black;
    margin-left: 14px;
    margin-bottom: 20px;
  }
}
</style>
