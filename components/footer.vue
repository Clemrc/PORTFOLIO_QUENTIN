<template>
  <footer>
    <div class="footer">
      <div id="_percent">0</div>
    </div>
  </footer>
</template>

<script>
import gsap from 'gsap'
export default {
  mounted() {
    gsap.from('.footer', {
      delay: 3,
      duration: 1.5,
      opacity: 0,
      y: 50,
      ease: 'expo'
    })
  }
}
</script>

<style>
.footer {
  border-top: 1px solid black;
  padding: 0;
  height: 80px;
  position: fixed;
  z-index: 10;
  bottom: 0%;
  width: 85%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: white;
}

.dark .footer {
  border-top: 1px solid white;
  background-color: #000000;
  color: white;
  transition: 0.5s;
}
</style>
