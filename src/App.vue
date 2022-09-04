<template>
  <Nav @themeChange="changeTheme" :lightTheme="lightTheme"/>
  <Header :lightTheme="lightTheme"/>
  <Main :lightTheme="lightTheme"/>
  <Footer/>
  <Preload/>
</template>

<script>
import NavVue from './components/Nav.vue'
import HeaderVue from './components/Header.vue'
import MainVue from './components/Main.vue'
import FooterVue from './components/Footer.vue'
import PreloadVue from './components/Preload.vue'

export default {
  name: 'App',
  components: {
    Nav: NavVue,
    Header: HeaderVue,
    Main: MainVue,
    Footer: FooterVue,
    Preload: PreloadVue
  },
  data() {
    return {
      lightTheme: false 
    }
  },
  methods: {
    changeTheme() {
      this.lightTheme = !this.lightTheme
      let body = document.querySelector('body')

      if (this.lightTheme) {
        body.classList.add('light-theme')  
      } else {
        body.classList.remove('light-theme')  
      }
    }
  }
}
</script>

<style lang="scss">

</style>
