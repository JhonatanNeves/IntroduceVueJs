<template>
<div id="app">
  
  <div v-for="(cliente, index) in clientes" :key="cliente.id">
    <h1>{{ index }}</h1>
    <Cliente :cliente="cliente"/>
    <br>

  </div>
  
  

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
      },
      clientes:[
        {
          id: 2,
          nome: "Jhonatan Neves",
        email: "teste22@gmail.com",
        idade: 99
        },
        {
          id: 3,
          nome: "Jhonatan Pro",
        email: "teste4578@gmail.com",
        idade: 55
        },
        {
          id: 4,
          nome: "Jhonatan Val",
        email: "teste99@gmail.com",
        idade: 33
        },
      ]
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
