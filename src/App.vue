<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
<template>
  <div id="app">
    <!--<img src="./assets/logo.png">
    <router-view></router-view>-->
    <top></top>
    <div class="container">
        <router-view></router-view>


    </div>
    <bottom></bottom>
  </div>
</template>

<script>
import Top from './components/Top'
import Bottom from './components/Bottom'
export default {
  name: 'app',
  components:{
      Top,
      Bottom
  }
 }
</script>

<style>

</style>