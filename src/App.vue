<template>
  <div id="app">
    <button class="main-button" v-on:click="showForm">Оставить отзыв</button>
    <feedback v-if="isFeebackVisible" />
  </div>
</template>

<script>
import feedback from "@/components/feedback";
export default {
  name: "App",
  components: {
    feedback,
  },
  data() {
    return {
      isFeebackVisible: false,
    };
  },
  methods: {
    showForm() {
      this.isFeebackVisible = true;
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
  color: #2c3e50;
  height: 100vh;
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
}
</style>
