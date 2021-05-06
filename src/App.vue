<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div class="container">
    <SideBar/>
    <Main/>
    <Bottom/>
  </div>
</template>

<script>
import SideBar from './components/SideBar.vue'
import Bottom from './components/Bottom.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    SideBar,Bottom,Main
  }
}
</script>

<style lang="scss">
// @import '../../public/style/positions.scss';
@import '../public/style/color.scss';
*{
  font-family: 'Montserrat', sans-serif;
  box-sizing: border-box;
  margin: 0;
}

.container{
  background-color: $color-dark;
  width: 100vw;
  height: 100vh;
}
</style>
