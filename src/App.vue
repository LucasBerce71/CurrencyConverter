<template>
  <div id="app">
    <h1>Conversor Monetário</h1>
    <div class="grid-line">
      <Convert coinA="USD" coinB="BRL" />
      <Convert coinA="BRL" coinB="USD" />
    </div>

    <div class="grid-line">
      <Convert coinA="CAD" coinB="BRL" />
      <Convert coinA="BRL" coinB="CAD" />
    </div>

    <div class="grid-line">
      <Convert coinA="EUR" coinB="BRL" />
      <Convert coinA="BRL" coinB="EUR" />
    </div>
  </div>
</template>

<script>
import Convert from "./components/Convert.vue";

export default {
  name: "App",
  components: {
    Convert,
  },
};
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.grid-line {
  display: flex;
  justify-content: space-between;
  margin-top: 40px;
  margin-bottom: 40px;
}
</style>
