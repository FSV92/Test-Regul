<template>
  <div id="app">
    <button class="main-button" v-on:click="showForm">Оставить отзыв</button>
    <Feedback v-if="isFeebackVisible" v-on:close-form="closeForm" />
  </div>
</template>

<script>
import Feedback from "@/components/feedback";
export default {
  name: "App",
  components: {
    Feedback,
  },
  data() {
    return {
      isFeebackVisible: true,
    };
  },
  methods: {
    showForm() {
      this.isFeebackVisible = true;
    },
    closeForm() {
      this.isFeebackVisible = false;
    },
  },
};
</script>

<style>
#app {
  font-family: "Montserrat", Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
  background-color: #ebedf0;
}
.main-button {
  position: relative;
  background-color: #5ac2c9;
  padding: 20px 20px;
  border: none;
  border-radius: 20px;
  font-family: Roboto;
  font-style: normal;
  font-weight: bold;
  font-size: 40px;
  line-height: 50px;
  color: #ffffff;
  cursor: pointer;
  top: 50%;
  transform: translateY(-50%);
  z-index: -1;
}
</style>
