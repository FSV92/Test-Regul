<template>
  <div class="feedback__photos feedback-photos">
    <input
      id="upload"
      type="file"
      class="feedback-photos__input"
      v-on:change="onPictureSelected"
    />
    <label for="upload" class="feedback-photos__label"></label>
    <div class="template feedback-photos__wrap-img">
      <img
        class="feedback-photos__img"
        src="../img/photo-1.jpg"
        alt="photo-1"
      />
      <img
        class="feedback-photos__delete"
        src="../img/delete.svg"
        alt="basket"
        v-on:click="removePictures"
      />
    </div>

    <div class="feedback-photos__wrap-img">
      <img
        class="feedback-photos__img"
        src="../img/photo-1.jpg"
        alt="photo-1"
      />
      <img
        class="feedback-photos__delete"
        src="../img/delete.svg"
        alt="basket"
        v-on:click="removePictures"
      />
    </div>
    <div class="feedback-photos__wrap-img">
      <img
        class="feedback-photos__img"
        src="../img/photo-2.jpg"
        alt="photo-2"
      />
      <img
        class="feedback-photos__delete"
        src="../img/delete.svg"
        alt="basket"
        v-on:click="removePictures"
      />
    </div>
    <div class="feedback-photos__wrap-img">
      <img
        class="feedback-photos__img"
        src="../img/photo-3.jpg"
        alt="photo-3"
        v-on:click="removePictures"
      />
      <img
        class="feedback-photos__delete"
        src="../img/delete.svg"
        alt="basket"
        v-on:click="removePictures"
      />
    </div>
    <div class="feedback-photos__wrap-img">
      <img
        class="feedback-photos__img"
        src="../img/photo-4.jpg"
        alt="photo-4"
        v-on:click="removePictures"
      />
      <img
        class="feedback-photos__delete"
        src="../img/delete.svg"
        alt="basket"
        v-on:click="removePictures"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "photos",
  data() {
    return {
      image: "",
    };
  },
  methods: {
    onPictureSelected() {
      let feedbackPhotos = document.querySelector(`.feedback-photos`);
      let wrapperImg = document.querySelector(`.feedback-photos__wrap-img`);
      let cloneWrapperImg = wrapperImg.cloneNode(true);
      let image = cloneWrapperImg.querySelector(`.feedback-photos__img`);
      let basket = cloneWrapperImg.querySelector(`.feedback-photos__delete`);
      let uploadFile = document.querySelector(`.feedback-photos__input`);
      let file = uploadFile.files[0];
      let reader = new FileReader();

      cloneWrapperImg.classList.remove(`template`);
      basket.addEventListener(`click`, (evt) => {
        evt.target.parentElement.remove();
      });

      reader.addEventListener(`load`, () => {
        image.src = reader.result;
      });
      reader.readAsDataURL(file);
      feedbackPhotos.appendChild(cloneWrapperImg);
    },
    removePictures(evt) {
      evt.target.parentElement.remove();
    },
  },
};
</script>

<style lang="scss" src="../scss/photos.scss">
</style>