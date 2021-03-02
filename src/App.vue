<template>
  <div id="app">

<!-- on introduit le header dans le template -->
    <Header/>

<!-- on introduit la Nav dans le template -->
    <Nav/>

<!-- on introduit le test focus -->
    <focus/>

<!-- on introduit le main dans le template -->
    <Main/>

<!-- on introduit le footer dans le template -->
  <!-- <Footer/> -->

  </div>
</template>

<script>

// on import l'ensemble des composants utilisés par app.vue
import Header from './components/header.vue'
import Footer from './components/footer.vue'
import Main from './components/main.vue'
import Nav from './components/nav.vue'
import state from './state.js'
import focus from './components/focus.vue'


export default {
  name: 'app',
  components: {
    Header,
    Main,
    Footer,
    Nav,
    focus
  },

// ce sont les datas du state qui sont utilisés dans app.vue
  data() {
    return {
      state        
      
    };
  },
  created() {
    this.state.profil = 'adult'
    
  },
  watch: {
    'state.profil': function(profile) {
      document.body.style.backgroundImage = `url("background/fond-${profile}.jpg")`;
    }
  },
}
</script>

<style lang="less">
// import des deux feuilles de style
  @import "./assets/style/normalize.css";
  @import "./assets/style/style.css";
</style>
