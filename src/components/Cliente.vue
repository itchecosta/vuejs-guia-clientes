<template>
    <div :class="{'cliente': !isPremium, 'cliente-premium': isPremium}">
        <h4>Nome: {{cliente.nome}}</h4>
        <hr>
        <p>E-mail: {{cliente.email | processarEmail}}</p>
        <p v-if="showIdade">Idade: {{cliente.idade}}</p>
        <p v-else>O usuário escondeu a idade!</p>
        <button @click="mudarCor()">Mudar cor!</button>
        <button @click="emitirEventoDelete()">deletar</button>
        <h4>id especial: {{idEspecial}}</h4>
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
    },
    methods: {
        mudarCor: function() {
            this.isPremium = !this.isPremium;
        },
        emitirEventoDelete: function() {
            console.log("emitindo do filho");
            this.$emit("meDelete", {idDoCliente: this.cliente.id, curso: "formação node.js", emPromocao:true, component: this});
        }
    },
    filters: {
        processarEmail: function(value) {
            return value.toUpperCase();
        }
    },
    computed: {
        idEspecial: function() {
            return (this.cliente.email + this.cliente.nome + this.cliente.id).toUpperCase();
        }
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