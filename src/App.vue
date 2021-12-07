<template>
<div class="background">
  <div id="app" style="padding-bottom: 225px; margin-top : 0;">
    <img class="img" src="./assets/pokemon.png">
    <router-view/>
  </div>
</div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    }

.img {
  width : 30%;
  padding-bottom: 140px;
}

.background{
  background-image: url("./assets/background.jpg");
  background-repeat: no-repeat;
  background-size: 1500px;
    }
</style>
