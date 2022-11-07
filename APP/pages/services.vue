<template>
  <div>
    <navbars />
    <Carousel class="carouselContainer">
      <CarouselSlide v-for="post in posts" :key="post.key"
        ><img
          :src="require('~/assets/carouselPosts/post_' + post.key + '.JPG')"
          alt="img"
          class="carouselPost" />
        <p v-html="post.text" class="carouselText"></p
      ></CarouselSlide>
    </Carousel>
    <h1 class="titreServices">Services</h1>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      posts: [
        {
          key: 1,
          text: "FONACO vous propose différentes formes de communication et promotion pour répondre à vos besoins et vos objectifs tout en respectant votre budget.",
        },
        {
          key: 2,
          text: "Impression sur multiples supports : carte de visite, dépliant, brochure, magazine, bâche, panneau ...",
        },
        {
          key: 3,
          text: "Notre équipe se consacre entièrement pour vous fournir la conception graphique avec l'exigence et la méthodologie nécessaire qui vous convient.",
        },
      ],
    };
  },
};
</script>
<style></style>
