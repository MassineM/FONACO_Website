<template>
  <div class="mainPage">
    <video autoplay muted loop class="bgVid">
      <source src="../assets/background.mp4" type="video/mp4">
    </video>
    <navbars />
    <!-- <Carousel>
      <CarouselSlide v-for="i in [1, 2, 3]"
        ><img
          :src="require('~/assets/carouselPosts/post_' + i + '.JPG')"
          alt="img"
          class="carouselPost"
      /></CarouselSlide>
    </Carousel> -->
    <div class="index">
      <h1 class="gtitre">FONACO WEB AGENCY</h1>
      <p class="desc">FONACO est une agence de communication digitale pour des convictions innovantes et contribue au
        rayonnement des marques et à la transformation des entreprises dans un monde digitalisé.

        Du conseil au développement, de la création à l'acquisition de trafic en passant par le print, FONACO vous
        propose une offre globale et vous accompagne tout au long de vos projets.

        Nous mobilisons des expertises créatives et techniques en nous appuyant sur une démarche projet novatrice.</p>
      <p class="desc animate-text">PLUS HAUT ET PLUS LOIN AVEC FONACO</p>
    </div>
    <flech />
    <div id="next" class="next">
      <Aboutus />
      <h1 class="titre2">Nos services</h1>

      <indexservice />
    </div>

  </div>
</template>

<script>
export default {

  mounted: function () {
      let delay = 100,
        delay_start = 0,
        contents,
        letters;

      document.querySelectorAll(".animate-text").forEach(function (elem) {
        contents = elem.textContent.trim();
        elem.textContent = "";
        letters = contents.split("");
        elem.style.visibility = 'visible';

        letters.forEach(function (letter, index_1) {
          setTimeout(function () {

            elem.textContent += letter;

          }, delay_start + delay * index_1);
        });
        delay_start += delay * letters.length;
      });
  },

  methods: {
    }


}



</script>
<style>
.bgVid {
  position: absolute;
  width: 100vw;
  height: 100vh;
  object-fit: cover;
  opacity: 0.3;
  right: 0;
  bottom: 0;
}

.animate-text {
  visibility: hidden;
}
</style>