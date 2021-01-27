<template>
  <div id="app">
    <h1>Conversor de moedas</h1>
    <div class="linha">
      <Conversor currency-from="USD" currency-to="BRL"/>
      <Conversor currency-from="BRL" currency-to="USD"/>
    </div>
    <div class="linha">
      <Conversor currency-from="CAD" currency-to="BRL"/>
      <Conversor currency-from="BRL" currency-to="CAD"/>
    </div>
    <div class="linha">
      <Conversor currency-from="EUR" currency-to="BRL"/>
      <Conversor currency-from="BRL" currency-to="EUR"/>
    </div>
  </div>
</template>

<script>
import Conversor from './components/Conversor.vue'; 

export default {
  name: 'App',
  components: {
    Conversor
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
  max-width: 900px;
  margin: auto;
}

.linha {
  display: flex;
  justify-content: space-around;
  margin-top: 30px;
}
</style>
