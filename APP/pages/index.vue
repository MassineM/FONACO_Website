<template>
  <div class="mainPage">
    <navbars />
    <Carousel>
      <CarouselSlide v-for="i in [1, 2, 3]"
        ><img
          :src="require('~/assets/carouselPosts/post_' + i + '.JPG')"
          alt="img"
          class="carouselPost"
      /></CarouselSlide>
    </Carousel>
    <flech />
    <div id="next" class="next">
      <Aboutus />
      <Services />
    </div>
    
  </div>
</template>

<script>



</script>
