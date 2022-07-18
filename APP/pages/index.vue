<template>
  <div class="mainPage">
    <Navbar />
    <Carousel>
      <CarouselSlide v-for="i in [1, 2, 3, 4, 5]"
        ><img
          :src="require('~/assets/carouselPosts/post_' + i + '.png')"
          alt="img"
          class="carouselPost"
      /></CarouselSlide>
    </Carousel>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>
