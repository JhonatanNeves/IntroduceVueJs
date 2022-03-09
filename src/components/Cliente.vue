
<template>
  <div :class="{ cliente: !isPremium, 'cliente-premium': isPremium }">
    <h4>Nome: {{ cliente.nome }}</h4>
    <hr />
    <p>Email: {{ cliente.email }}</p>
    <p v-if="showIdade === true">Idade: {{ cliente.idade }}</p>
    <p v-else>O usuário escondeu a idade!</p>
    <br />
    <button @click="mudarCor">Mudar cor!</button>
    <button @click="emitirEventoDelete">Deletar</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPremium: false,
    };
  },
  props: {
    cliente: Object,
    showIdade: Boolean,
  },
  methods: {
    mudarCor: function ($event) {
      console.log($event);
      this.isPremium = !this.isPremium;
    },
    emitirEventoDelete: function () {
      this.$emit("mDeletar", { idDoCliente: this.cliente.id, component: this });
    },
    testar: function () {
      console.log("Testando");
      alert("Alerta!");
    },
  },
};
</script>

<style scoped>
.cliente {
  background-color: #1f351a;
  width: 900px;
  height: 130px;
  padding: 3%;
  margin-top: 2%;
  margin-left: 23.5%;
  color: white;
}

.cliente-premium {
  background-color: #ed5d10;
  width: 900px;
  height: 130px;
  padding: 3%;
  margin-top: 2%;
  margin-left: 23.5%;
  color: white;
}
</style>