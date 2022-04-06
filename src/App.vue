<template>
  <div class="headerBox">
    <h1>How fast Can U Catch Me?</h1>
    <button class="controller" ref="button" :disabled="start" @click="show">
      Play▶
    </button>
  </div>
  <div v-if="start">
    <Box @hideBox="hideBox_emit" :delay="delay" />
  </div>
  <div v-if="gameEnd"><Result :score="this.score / 1000" /></div>
</template>
<script>
import Box from "./components/Box.vue";
import Result from "./components/Result.vue";
export default {
  name: "App",
  components: {
    Box,
    Result,
  },
  data() {
    return {
      start: false,
      delay: null,
      score: 0,
      gameEnd: false,
    };
  },
  methods: {
    // local
    show() {
      this.gameEnd = false;
      this.start = true;
      this.delay = 2000 + (Math.random() * 5000 + 1);
      this.$refs.button.textContent = "Pause⏹";
      this.score = 0;
    },
    // emit
    hideBox_emit(reactionScore) {
      this.start = false;
      this.$refs.button.textContent = "Play Again▶";
      this.score = reactionScore;
      this.gameEnd = true;
    },
  },
};
</script>

<style scoped>
.headerBox {
  text-align: center;
}
h1 {
  color: white;
  font-family: sans-serif;
  font-size: 4rem;
  word-spacing: 2.1px;
}
button.controller {
  padding: 10px 15px;
  margin-top: 30px;
  font-size: 2rem;
  font-weight: bold;
  border-radius: 8px;
  transition: 0.4s, color 0.5s;
  border: none;
  cursor: pointer;
}
button.controller:hover {
  transform: translateY(-6px);
  background-color: rgb(48, 44, 44);
  color: rgb(4, 255, 4);
}
button.controller:active {
  color: rgb(48, 44, 44);
  background-color: white;
}
</style>
