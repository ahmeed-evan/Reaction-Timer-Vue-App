<template>
  <h1>Reaction Timer</h1>
  <button id="playButton" @click="start" :disabled="isPlaying">Play</button>

  <Block v-if="isPlaying" :delay="delay"/>

</template>

<script>
import Block from "./components/Block";

export default {
  name: "App",
  components: { Block },
  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      console.log(this.delay)
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
}
</style>
