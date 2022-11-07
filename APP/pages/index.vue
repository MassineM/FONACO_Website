<template>
  <div class="mainPage">
    <video autoplay muted loop class="bgVid">
      <source src="../assets/background.mp4" type="video/mp4" />
    </video>
    <navbars />
    <div class="index">
      <h1 class="gtitre">FONACO WEB AGENCY</h1>
      <p class="desc">
        FONACO est une agence de communication pour l'innovation dans le
        rayonnement des marques et dans l'introduction des entreprises à un
        monde digitalisé. Du conseil au développement, de la création à
        l'acquisition de trafic en passant par la gestion complète de la
        communication et l'affichage, FONACO vous propose des offres sur mesure
        et vous accompagne tout au long de vos projets.
      </p>
      <p class="desc animate-text">PLUS HAUT ET PLUS LOIN AVEC FONACO</p>
    </div>
    <flech />
    <div id="next" class="next">
      <Aboutus />
      <h1 class="titre2">Nos services</h1>

      <indexservice />
      <div class="btncon">
        <button class="custom-btn btn-15" @click="$router.push('services')">
          Voir Plus
        </button>
      </div>
      <h1 class="titre2">Notre équipe</h1>
      <Person />
      <div class="btncon">
        <button class="custom-btn btn-15" @click="$router.push('equipe')">
          Voir Plus
        </button>
      </div>
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
      elem.style.visibility = "visible";
      letters.forEach(function (letter, index_1) {
        setTimeout(function () {
          elem.textContent += letter;
        }, delay_start + delay * index_1);
      });
      delay_start += delay * letters.length;
    });
  },
  methods: {},
};
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
