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

<style lang="scss" src="./components/scss/setting.scss">
</style>
