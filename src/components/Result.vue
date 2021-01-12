<template>
  <div class="result">
    <p>Your Reaction Time is : {{ reactionScore }} ms</p>
    <p id="rank">{{ rank }}</p>
  </div>
</template>

<script>
export default {
  props: ["reactionScore"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.reactionScore <= 250) {
      this.rank = "Ninja Reflex";
    } else if (this.reactionScore <= 500) {
      this.rank = "Okay Reflex";
    } else {
      this.rank = "Snail Reflex";
    }
  },
};
</script>

<style>
.result {
  width: 10%;
  border-radius: 20px;
  background: rgb(189, 187, 187);
  color: white;
  text-align: center;
  padding: 10px 42px;
  margin: 10px auto;
}
#rank{
    color:rgba(182, 31, 31, 0.658);
    text-align: center;
}
</style>