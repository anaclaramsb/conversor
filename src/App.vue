<template>
  <div id="app">
    <h1> Conversor de Moedas </h1>
    <div class = "linha">
    <Conversor moedaA="USD" moedaB="BRL"/>
    <Conversor moedaA="BRL" moedaB="USD"/>
    </div>
    <div class = "linha">
    <Conversor moedaA="CAD" moedaB="BRL"/>
    <Conversor moedaA="BRL" moedaB="CAD"/>
    </div>
    <div class = "linha">
    <Conversor moedaA="EUR" moedaB="BRL"/>
    <Conversor moedaA="BRL" moedaB="EUR"/>
    </div>
  </div>
</template>

<script>
import Conversor from "./components/Conversor.vue"

export default {
  name: 'App',
  components: {
    Conversor,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  margin-bottom: 40px;
}

.linha{
  display: flex;
  justify-content: space-evenly;
  margin-bottom: 30px;
}
</style>
