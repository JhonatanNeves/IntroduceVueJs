<template>
  <div id="app">
    <h3>Cadastro:</h3>
    <small id="nomeErro" v-show="deuErro"
      >O nome é inválido, tente novamente!</small
    >
    <br />
    <input type="text" placeholder="nome" v-model="nomeField" />
    <input type="email" placeholder="email" v-model="emailField" />
    <input type="number" placeholder="idade" v-model="idadeField" />
    <button @click="cadastrarUsuario">Cadastrar!</button>
    <div v-for="(cliente, index) in clientes" :key="cliente.id">
      <h1>{{ index + 1 }}</h1>
      <Cliente :cliente="cliente" @mDeletar="deletarUsuario($event)" />
      <br />
    </div>
  </div>
</template>

<script>
import Cliente from "./components/Cliente.vue";

export default {
  name: "App",
  data() {
    return {
      deuErro: false,
      nomeField: "",
      emailField: "",
      idadeField: 0,

      clientes: [
        {
          id: 2,
          nome: "Jhonatan Neves",
          email: "teste22@gmail.com",
          idade: 99,
        },
        {
          id: 3,
          nome: "Jhonatan Pro",
          email: "teste4578@gmail.com",
          idade: 55,
        },
        {
          id: 4,
          nome: "Jhonatan Val",
          email: "teste99@gmail.com",
          idade: 33,
        },
      ],
    };
  },
  components: {
    Cliente,
  },
  methods: {
    cadastrarUsuario: function () {
      if (
        this.nomeField == "" ||
        this.nomeField == " " ||
        this.nomeField.length < 3
      ) {
        this.deuErro = true;
      } else {
        this.clientes.push({
          nome: this.nomeField,
          email: this.emailField,
          idade: this.idadeField,
          id: Date.now(),
        });
        this.nomeField = "";
        this.emailField = "";
        this.idadeField = "";
        this.deuErro = false;
      }
    },
    deletarUsuario: function ($event) {
      console.log("Recebendo Evento!");
      var id = $event.idDoCliente;
      var novoArray = this.clientes.filter((cliente) => cliente.id != id);
      this.clientes = novoArray;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2e4c28;
  margin-top: 60px;
  background-color: white;
}
#nomeErro {
  color: red;
}
</style>
