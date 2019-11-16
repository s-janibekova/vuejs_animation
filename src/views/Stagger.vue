<template>
  <div>
    <div id="container">
      <div v-for="card in cards" :key="card" class="card"></div>
    </div>
  </div>
</template>

<script>
import { TweenMax } from 'gsap/TweenMax'
export default {
  data() {
    return {
      cards: [{ id: 1 }, { id: 2 }, { id: 3 }, { id: 4 }, { id: 5 }]
    }
  },

  mounted() {
    TweenMax.staggerFrom('.card', 0.5, { opacity: 0, y: 200 }, 0.1)
  }
}
</script>

<style scoped>
#container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-evenly;
}

.card {
  height: 6.5em;
  width: 6.5em;
  border-radius: 1%;
  background-color: #f880b8;
  box-shadow: 0.08em 0.03em 0.4em #ababab;
  padding-top: 1em;
  margin-top: 0.5em;
  margin-right: 0.5em;
}
</style>
