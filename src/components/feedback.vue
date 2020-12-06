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
        <div class="feedback-author__text">
          <h2 class="feedback-author__title">Фоточки в свадебном платьице</h2>
          <span class="feedback-author__name">Алена Смирнова</span>
        </div>
      </div>
      <Rating />
      <Comment />
      <Photos />
    </div>

    <div class="feedback__footer">
      <button class="feedback__send">Отправить</button>
    </div>
  </div>
</template>

<script>
import Rating from "@/components/rating";
import Comment from "@/components/comment";
import Photos from "@/components/photos";
export default {
  name: "feedback",
  components: { Rating, Comment, Photos },
  methods: {
    closeForm() {
      this.$emit("close-form");
    },
  },
};
</script>

<style lang="scss" src="./scss/feedback.scss">
</style>
