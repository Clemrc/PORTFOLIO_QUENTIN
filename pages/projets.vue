<template>
  <div>
    <div class="container">
      <div class="projets projet1">
        <nuxt-link to="/projet/photos">
          <div class="projet-content">
            <div class="img">
              <img src="/IMG_4032.jpg" alt="" />
            </div>
          </div>
        </nuxt-link>
      </div>

      <div class="projets projet2">
        <nuxt-link to="/projet/monolithe">
          <div class="projet-content">
            <div class="img">
              <img src="/0001.jpg" alt="" />
            </div>
          </div>
        </nuxt-link>
      </div>

      <div class="projets projet5">
        <nuxt-link to="/projet/ice-land">
          <div class="projet-content">
            <div class="img">
              <img src="/AFFICHE_ICE_LAND.jpg" alt="" />
            </div>
          </div>
        </nuxt-link>
      </div>

      <div class="projets projet3">
        <nuxt-link to="/canvas">
          <div class="projet-content">
            <div class="img">
              <img src="/album_monolithere.jpg" alt="" />
            </div>
          </div>
        </nuxt-link>
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
    tl.from('.projets', {
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
    if (to.name === 'portfolioquentin') {
      tl.to('.projet1', {
        duration: 0.3,
        opacity: 0,
        y: -50,
        ease: 'expo'
      }).to(
        '.projets',
        {
          duration: 0.5,
          opacity: 0,
          y: 100,
          ease: 'expo',
          stagger: {
            each: 0.1,
            from: 'end'
          },
          onComplete: () => {
            next()
          }
        },
        '<.2'
      )
    } else if (to.name === 'canvas') {
      tl.to('.projet3', {
        duration: 0.3,
        opacity: 0,
        y: 50,
        ease: 'expo'
      }).to(
        '.projets',
        {
          duration: 0.5,
          opacity: 0,
          y: 100,
          ease: 'expo',
          stagger: {
            each: 0.1,
            from: 'end'
          },
          onComplete: () => {
            next()
          }
        },
        '<.2'
      )
    } else {
      tl.to('.projets', {
        duration: 0.3,
        opacity: 0,
        y: 100,
        ease: 'expo',
        stagger: {
          each: 0.1,
          from: 'end'
        },
        onComplete: () => {
          next()
        }
      })
    }
  },
  head() {
    return {
      title: 'Quentin Demaria - projets',
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
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.projets {
  width: 70%;
  margin: 10px 0px;
}

.projet-content {
  height: 100%;
  width: 100%;
  transition: 0.2s;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.projet-content img:hover {
  box-shadow: 0 0 10px 0px grey;
  transition: 0.2s;
  transition-delay: 0s;
  cursor: pointer;
}

.focus {
  grid-column-start: 1;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 7;
  z-index: 10;
  background-color: brown;
  opacity: 0.5;
  transition: 0.2s;
}

/* @media screen and (min-width: 800px) {
  .container {
    display: grid;
    grid-column-start: 3;
    grid-column-end: 4;
    grid-row-start: 1;
    grid-row-end: 6;
    grid-template-columns: auto;
    grid-template-rows: 15% 15% 15% 15%;
  }

  .projet1 {
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 5;
  }
  .projet2 {
    grid-column-start: 3;
    grid-column-end: 4;
    grid-row-start: 1;
    grid-row-end: 7;
  }
  .projet3 {
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 5;
    grid-row-end: 7;
  }

  .projet5 {
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 3;
    grid-row-end: 7;
  }
} */

@media screen and (min-width: 1000px) {
  .container {
    display: grid;
    grid-column-start: 3;
    grid-column-end: 4;
    grid-row-start: 1;
    grid-row-end: 6;
    grid-template-columns: auto;
    grid-template-rows: 15% 15% 15% 15%;
  }

  .projets {
    width: 100%;
    margin: 0;
  }

  .description .projet_title {
    color: black;
  }

  .projet1 {
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 5;
  }
  .projet2 {
    grid-column-start: 3;
    grid-column-end: 4;
    grid-row-start: 1;
    grid-row-end: 7;
  }
  .projet3 {
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 5;
    grid-row-end: 7;
  }

  .projet5 {
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 1;
    grid-row-end: 7;
  }

  .projet1 img {
    width: 80%;
  }

  .projet2 img {
    width: 70%;
  }

  .projet3 img {
    width: 70%;
  }

  .projet5 img {
    width: 90%;
  }

  .img {
    display: flex;
    justify-content: center;
  }

  img {
    width: 30%;
  }
}
</style>
