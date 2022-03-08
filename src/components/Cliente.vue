
<template>
<div :class="{'cliente': !isPremium, 'cliente-premium': isPremium}">
    <h4>Nome: {{cliente.nome}}</h4>
    <hr>
    <p>Email: {{cliente.email}}</p>
    <p v-if="showIdade === true">Idade: {{cliente.idade}}</p>
    <p v-else>O usuário escondeu a idade!</p>
    
</div>
</template>

<script>
export default {
    data(){
        return{
            isPremium: false

        }
    },
    props:{
        cliente: Object,
        showIdade: Boolean
    }

}
</script>

<style scoped>
.cliente{
    background-color: #1F351A  ;
    width: 900px;
    height: 130px;
    padding: 1%;
    margin-top: 2%;
    margin-left: 26.6%;
    color: white;
    
}

.cliente-premium{
    
    background-color: #ED5D10   ;
    width: 900px;
    height: 130px;
    padding: 1%;
    margin-top: 2%;
    margin-left: 26.6%;
    color: white;
    

}
</style>