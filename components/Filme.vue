<script setup>
    const props = useAttrs();
</script>

<template>
    <div v-bind:class="{conteudo: true, conteudoAlugado: props.alugado}">
        <strong>{{ props.nome }}</strong>
        <p v-if="props.alugado"><u>Alugado</u></p>
        <img src="https://placeholder.co/150"/>
        <p>R$ {{ props.preco }}</p>
        <button v-on:click="props.alteraAlugado(props.id)" v-bind:class="{botao: true, botaoAlugado: props.alugado}">Alugar</button>
    </div>
</template>

<style scoped>
    .conteudo{
        display: flex;
        flex-direction: column;
        width: 200px;
        gap: 10px;
        text-align: center;
        background-color: blueviolet;
        color: white;
        padding: 20px;
        border-radius: 5px;
    }
    .conteudoAlugado{
        background-color: orangered;
    }
    .botao{
        background-color: orange;
        color: white;
        border: none;
        padding: 15px;
    }
    .botaoAlugado{
        background-color: yellowgreen;
    }
</style>