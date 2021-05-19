<template>
    <div :class="{'cliente': !isPremium, 'cliente-premium': isPremium}">
        <h4>Nome: {{cliente.nome}}</h4>
        <hr>
        <p>E-mail: {{cliente.email}}</p>
        <p v-if="showIdade">Idade: {{cliente.idade}}</p>
        <p v-else>O usuário escondeu a idade!</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
           isPremium: false
        }
    },
    props: {
        cliente: Object,
        showIdade: Boolean
    }
}
</script>

<style scoped>
    .cliente {
        background-color:#ECE5E3;
        width: 600px;
        height: 250px;
        padding: 1%;
        margin-top: 2%;
    }
    .cliente-premium {
        background-color:#000;
        color: gold;
        width: 600px;
        height: 250px;
        padding: 1%;
        margin-top: 2%;
    }
</style>