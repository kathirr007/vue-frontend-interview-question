<template>
  <q-page class="questions-page">
    <p class="question-text">
      You are tasked with creating a layout where two images are displayed.
      <br />
      The first image can have any dimensions, while the second image must be exactly 40x40 pixels.
      <br />
      The second image should always be positioned at the bottom right corner of the first image.
      <br />
      Please implement the HTML and CSS code to achieve this layout.

      <br />
      <br />
      Image Links:
      <br />
      First Image: https://via.placeholder.com/300x200
      <br />
      Second Image: https://via.placeholder.com/40x40
    </p>
    <div class="relative">
      <img class="first-image" src="https://via.placeholder.com/300x200" alt="first-image">
      <img class="second-image" src="https://via.placeholder.com/40x40" alt="second-image">
    </div>
  </q-page>
</template>

<script>
// vue
import { defineComponent } from "vue";

export default defineComponent({
  name: 'QuestionNumberTwo',
})
</script>

<style lang="scss" scoped>
.questions-page {
  padding: 16px;

  .question-text {
    margin-bottom: 24px;
    font-weight: 500;

    font-size: 16px;
  }

  .relative {
    position: relative;

    img {
      display: block;
    }

    .first-image {
      width: 100%;
    }

    .second-image {
      position: absolute;
      display: inline-block;
      bottom: 0;
      right: 0;
      border: 2px solid orange;
    }
  }
}
</style>
