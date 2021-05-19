<template>
  <div id="app">
    <h1>Guia Clientes</h1>
    <input type="text" v-model="nomeDoItalo">
    <Cliente :cliente="clienteItalo" :showIdade="true" />
    <Cliente :cliente="clienteItalo" :showIdade="false" />
    <Cliente :cliente="clienteItalo" :showIdade="false" />
    <Cliente :cliente="clienteItalo" :showIdade="true" />
  </div>
</template>

<script>
import Cliente from './components/Cliente'
// import Produto from './components/Produto'

export default {
  name: 'App',
  data() {
    return {
      nomeDoItalo: "Italo Costa",
      clienteItalo: {
        nome: "Italo Costa",
        email: "italo@gmail.com",
        idade: 30
      }
    }
  },
  components: {
    Cliente,
    // Produto
  }
}
</script>

<style>
</style>
