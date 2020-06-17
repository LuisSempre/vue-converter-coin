<template>
  <div id="app">
    <div class="title">Converter Coin</div>
    <div class="line">
      <Converter coinA="USD" coinB="BRL" />
      <Converter coinA="BRL" coinB="USD" />
    </div>
    <div class="line">
      <Converter coinA="CAD" coinB="BRL" />
      <Converter coinA="BRL" coinB="CAD" />
    </div>
    <div class="line">
      <Converter coinA="EUR" coinB="BRL" />
      <Converter coinA="BRL" coinB="EUR" />
    </div>
  </div>
</template>

<script>
import Converter from "./components/coin.vue";

export default {
  name: "App",
  components: {
    Converter
  }
};
</script>

<style>
* {
  background-color: black;
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
#app {
  margin: auto;
  max-width: 900px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: white;
  margin-top: 60px;
}
.line {
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}
.title{
  text-align: center;
  font-size: 40px;
  color: green;
  font-weight: bold;
}
</style>
