<template>
  <div id="app">
      <img src="./assets/pc-monitor.png">
    <loginPage msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import loginPage from './components/loginPage.vue'

export default {
  name: 'app',
  components: {
    loginPage
  }
}
</script>

<style lang="scss">
body{
background: linear-gradient(0deg, rgba(51,78,145,1) 0%, rgba(143,224,230,1) 100%);
background-repeat: no-repeat;
height:100vh;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color:white;
  padding-top: 20%;
  font-weight: bolder;
  img{
    opacity:0.7;
  }
}
</style>
