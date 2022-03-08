
<template>
<div id="cliente">
    <h4>Nome: {{cliente.nome}}</h4>
    <hr>
    <p>Email: {{cliente.email}}</p>
    <p v-if="showIdade">Idade: {{cliente.idade}}</p>
    
</div>
</template>

<script>
export default {
    data(){
        return{
            

        }
    },
    props:{
        cliente: Object,
        showIdade: Boolean
    }

}
</script>

<style scoped>
#cliente{
    background-color: #1F351A  ;
    width: 900px;
    height: 130px;
    padding: 1%;
    margin-top: 2%;
    margin-left: 26.6%;
    color: white;
    
}

</style>