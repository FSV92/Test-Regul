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

    <div class="feedback__content">
      <div class="feedback__author feedback-author">
        <img
          class="feedback-author__img"
          src="../img/author.jpg"
          alt="author"
        />
        <h2 class="feedback-author__title">Фоточки в свадебном платьице</h2>
        <span class="feedback-author__name">Алена Смирнова</span>
      </div>
      <Rating />
      <Comment />
    </div>
    <button class="feedback__button">Отправить</button>
  </div>
</template>

<script>
import Rating from "@/components/rating";
import Comment from "@/components/comment";
export default {
  name: "feedback",
  components: { Rating, Comment },
  methods: {
    closeForm() {
      this.$emit("close-form");
    },
  },
};
</script>

<style lang="scss" src="./scss/feedback.scss">
</style>
