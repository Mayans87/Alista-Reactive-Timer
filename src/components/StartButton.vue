<script>
export default {
  data() {
    return {
      disableButton: false,
    };
  },
  methods: {
    showModalEmitter() {
      this.$emit("showModal", true);
      this.disableButton = true;
      setTimeout(() => {
        this.disableButton = false;
      }, 5000);
    },
  },
};
</script>
<template>
  <div class="btn">
    <button :disabled="disableButton" @click="showModalEmitter" :class="{'disable': disableButton }">Start!</button>
  </div>
</template>
<style scoped>
.btn {
  display: flex;
  justify-content: center;
  margin-top: 40vh;
}
button {
  border-radius: 20px;
  padding: 25px;
  font-size: larger;
  font-weight: bolder;
  color: white;
  background-color: rgb(7, 218, 172);
  border: 5px solid rgb(4, 117, 93);
  cursor: pointer;
}
button:hover {
  color: rgb(4, 117, 93);
}
.disable{
    background-color: gray;
    border: 5px solid gray;
}
</style>
