<template>
<div id="app">
  <h1>Clientes Bank</h1>
  <Cliente :cliente="clienteJhonatan" :showIdade="true"/>
  <Cliente :cliente="clienteJhonatan" :showIdade="false"/>
  <Cliente :cliente="clienteJhonatan" :showIdade="true"/>
  <Cliente :cliente="clienteJhonatan" :showIdade="false"/>
  
  

</div>
</template>

<script>
import Cliente from './components/Cliente.vue'

export default {
  name: 'App',
  data(){
    return {
      nomeDoJhonatan: "J. Neves ",
      clienteJhonatan:{
        nome: "Jhonatan Neves",
        email: "teste2e@gmail.com",
        idade: 99
      }
    }
  },
  components:{
    Cliente
  }
  }

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2E4C28 ;
  margin-top: 60px;
  background-color:white;
  ;
}
</style>
