<script>
import Header from "./components/Header.vue";
import NavBar from "./components/NavBar.vue";
import Button from "./components/StartButton.vue";
import Modal from "./components/Modal.vue";
export default {
  data() {
    return {
      showModal: false,
      time: 5,
    };
  },
  components: {
    Header,
    NavBar,
    Button,
    Modal,
  },
  methods: {
    ModalToggler(data) {
      this.time = Math.floor(Math.random() * 10) + 1;
      console.log(
        "data received on click of button back to parent successfully: " +
          data +
          " , with timer: " +
          this.time +
          "seconds"
      );
      setTimeout(() => {
        this.showModal = data;
        this.time = Date.now().toFixed(5);
      }, this.time * 1000);
    },
  },
};
</script>
<template>
  <NavBar />
  <Header />
  <Teleport to=".modals">
    <div v-if="showModal">
      <Modal @close="this.showModal = false" :time="time" />
    </div>
  </Teleport>
  <Button @showModal="ModalToggler" />
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
