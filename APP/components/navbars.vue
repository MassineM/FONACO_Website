<template>
  <div>
    <nav :class="{ 'onScroll': !view.topOfPage}">
      <ul class="menu">
        <li><a href="/" class="myA"
          :class="{active: currentRouteName == 'index' }">Accueil</a></li>
        <li><a href="services"
          :class="{active: currentRouteName == 'services' }">Services</a></li>
        <li><a href="equipe"
          :class="{active: currentRouteName == 'equipe' }">Equipe</a></li>
        <li><a href="contact"
          :class="{active: currentRouteName == 'contact' }">Contact</a></li>
      </ul>
    </nav>
  </div>
</template>
<script>
export default{computed: {
    currentRouteName() {
        return this.$route.name;
    }
},data () {
    return {
      view: {
        topOfPage: true
      }
    }
  },
  beforeMount() {
    window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll(){
      if(window.pageYOffset>0){
        if(this.view.topOfPage) this.view.topOfPage = false
      } else {
        if(!this.view.topOfPage) this.view.topOfPage = true
      }
    }
  },
}
</script>
<style></style>
