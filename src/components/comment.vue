<template>
  <div class="feedback__comment feedback-comment">
    <textarea
      class="feedback-comment__field"
      name="comment"
      placeholder="Комментарий"
      maxlength="500"
      required
      v-model="text"
    ></textarea>
    <div class="feedback-comment__count">
      <span>{{ text.length }}</span
      >/<span>500</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "comment",
  data() {
    return {
      text: "",
    };
  },
};
</script>

<style lang="scss" src="../scss/comment.scss"></style>
