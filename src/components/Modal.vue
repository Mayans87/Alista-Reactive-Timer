<script>
export default {
  props: ["time"],
  data() {
    return {
      content: false,
      score: 10,
    };
  },
  methods: {
    gameHandler() {
      this.content = true;
      console.log("content area clicked!");
      console.log("timer prop: " + this.time);
      console.log("time difference : ", Date.now().toFixed(5) - this.time);
      this.score=Date.now().toFixed(5) - this.time;
    },
  },
};
</script>
<template>
  <div
    class="backdrop"
    @click.self="
      () => {
        this.$emit('close');
      }
    "
  >
    <div class="modal" @click="gameHandler">
      <div v-if="!content">
        <span>Click Me!</span>
      </div>
      <div class ="ctx" v-if="content && this.score < 1000">
        <p>Woot Woot!!!</p><br>
        <p>Fantastic Score: {{ score }} ms</p>
    </div>
      <div class ="ctx" v-if="content && this.score > 1000">
        <p>Oops Awww!!!</p><br>
        <p>Average Score: {{ score }} ms</p>
    </div>
    </div>
  </div>
</template>
<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* Semi-transparent backdrop */
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9; /* Higher z-index to ensure it's on top */
}
.modal {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgb(7, 218, 172);
  border-radius: 25px;
  height: 30vh;
  width: 30vw;
  margin: auto auto;
  border: 5px solid rgb(4, 117, 93);
  cursor: pointer;
  position: absolute;
  z-index: 10;
}
.ctx{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: white;
    font-weight: bolder;
}
</style>
