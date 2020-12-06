<template>
  <div class="feedback">
    <div class="feedback__header">
      <h1 class="feedback__title">Мой отзыв</h1>
      <img
        class="feedback__close"
        src="../img/close.svg"
        alt="close"
        v-on:click="closeForm"
      />
    </div>
    <div class="feedback__content">Контент</div>
    <button class="feedback__button">Отправить</button>
  </div>
</template>

<script>
export default {
  name: "feedback",
  components: {},
  methods: {
    closeForm() {
      this.$emit("close-form");
    },
  },
};
</script>

<style>
</style>
