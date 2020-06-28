<template>
  <div>
    <div class="container">
      <div class="content">
        <div class="title-content">
          <h1 class="title">Projets</h1>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  transition: 'slide-fade',
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
</style>
