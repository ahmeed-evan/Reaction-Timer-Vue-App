<template>
  <h1>Reaction Timer</h1>
  <button id="playButton" @click="start" :disabled="isPlaying">Play</button>

  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Result v-if="showReactionTime" :reactionScore="score" />
</template>

<script>
import Block from "./components/Block";
import Result from "./components/Result";

export default {
  name: "App",
  components: { Block, Result },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showReactionTime: false,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      this.showReactionTime = false;
    },
    endGame(reactionTime) {
      this.isPlaying = false;
      this.score = reactionTime;
      this.showReactionTime = true;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
#playButton {
  color: aliceblue;
  background: orange;
  border-radius: 4px;
  padding-block-start: 8px;
  padding-block-end: 8px;
  padding-left: 16px;
  padding-right: 16px;
  border: none;
  cursor: pointer;
}
#playButton[disabled] {
  cursor: not-allowed;
  opacity: 0.4;
}
</style>
