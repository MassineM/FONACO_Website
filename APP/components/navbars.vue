<template>
  <div>
    <nav :class="{ 'onScroll': !view.topOfPage}">
      <ul class="menu">
        <li><a
          :class="{active: currentRouteName == 'index' }" href="/">Accueil</a></li>
        <li><a
          :class="{active: currentRouteName == 'services' }" href="services">Services</a></li>
        <li><a
          :class="{active: currentRouteName == 'equipe' }" href="equipe">Equipe</a></li>
        <li><a
          :class="{active: currentRouteName == 'contact' }" href="contact">Contact</a></li>
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
