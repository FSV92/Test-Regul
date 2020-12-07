<template>
  <div id="app">
    <button class="main-button" v-on:click="showForm" v-if="!isFeedbackVisible">
      Оставить отзыв
    </button>
    <Feedback
      v-if="isFeedbackVisible"
      v-on:close-form="closeFormHadler"
      v-on:submit-form="submitFormhadler"
    />

    <div class="alert" v-if="isAlertVisible">
      <span class="alert__text">Спасибо, отзыв опубликован!</span>
      <img
        class="alert__close"
        src="./img/close-alert.svg"
        alt="close-alert"
        v-on:click="closeAlert"
      />
    </div>
  </div>
</template>

<script>
import Feedback from "./components/feedback";
export default {
  name: "App",
  components: {
    Feedback,
  },
  data() {
    return {
      isFeedbackVisible: false,
      isAlertVisible: false,
    };
  },
  methods: {
    showForm() {
      this.isFeedbackVisible = true;
    },
    closeFormHadler() {
      this.isFeedbackVisible = false;
    },
    submitFormhadler() {
      this.isFeedbackVisible = false;
      this.isAlertVisible = true;
    },
    closeAlert() {
      this.isAlertVisible = false;
    },
  },
};
</script>

<style lang="scss" src="./scss/setting.scss">
</style>
