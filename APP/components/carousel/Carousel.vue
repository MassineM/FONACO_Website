<template>
  <div>
    <slot></slot>
    <div class="carouselNav">
      <button @click.prevent="prev" class="prevnext">Prev</button>
      <div class="slideMenu">
        <button
          v-for="i in nbSlides()"
          @click="selectSlide(i - 1)"
          class="slideSelector"
          :class="{ active: i - 1 == index }"
        ></button>
      </div>
      <button @click.prevent="next" class="prevnext">Next</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      index: 0,
      slides: [],
    };
  },
  mounted() {
    this.slides = this.$children;
    this.slides.forEach((slide, i) => {
      slide.index = i;
    });
  },
  methods: {
    nbSlides() {
      return this.slides.length;
    },
    next() {
      if (this.index >= this.nbSlides() - 1) {
        this.index = 0;
      } else {
        this.index++;
      }
    },
    prev() {
      if (this.index <= 0) {
        this.index = this.nbSlides() - 1;
      } else {
        this.index--;
      }
    },
    selectSlide(n) {
      this.index = n;
    },
  },
};
</script>

<style></style>
