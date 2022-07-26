<template>
  <div>
    <slot></slot>
    <div class="carouselNav">
      <button @click.prevent="prev" class="prevnext">Prev</button>
      <div class="slideMenu">
        <button
          v-for="i in nbSlides()" :key="i"
          @click="selectSlide(i - 1)"
          class="slideSelector"
          :class="{active: i - 1 == index }"
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
      direction: 'right',
      slides: [],
    };
  },
  mounted() {

    document.addEventListener("keydown", this.keySlide);
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
      this.direction='right';
      if (this.index >= this.nbSlides() - 1) {
        this.index = 0;
      } else {
        this.index++;
      }
    },
    prev() {
      this.direction='left';
      if (this.index <= 0) {
        this.index = this.nbSlides() - 1;
      } else {
        this.index--;
      }
    },
    selectSlide(n) {
      this.direction='right';
      this.index = n;
    },
    keySlide(e){
      if(e.keyCode==37)
        this.prev()
      if(e.keyCode==39 || e.keyCode==32 || e.keyCode==13) this.next()
    }
  },
};
</script>

<style></style>
