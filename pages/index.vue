<script setup>
    
    const filmes = reactive([
        {
            id: 0,
            nome: "Esqueceram de mim",
            preco: 29.90,
            alugado: true,
        },
        {
            id: 1,
            nome: "Todo mundo em pânico",
            preco: 35.00,
            alugado: false,
        },
    ])

    function alteraAlugado( id ){
        filmes[id].alugado = !filmes[id].alugado;
    }

/*
    ---- SCRIPT DE PLANEJAMENTO DA AULA ----

    PARTE 1: passar dados para o componente

    - Criar cabeçalho e filme em HTML puro
    - Passar cabeçalho e filme para componente
    - Ensinar a usar props para nome do filme
    - Atividade para adicionar preço

    PARTE 2: objetos e v-bind
    - Criar um objeto para guardar dados do filme, como em um banco
    - Usar v-bindo para passar os dados
    - Atividade para adicionar um filme novo
    - Adicionar alugado e v-bind para mostrar no componente
    - Mostrar v-bind para classes

    PARTE 3: enviar dados entre componentes
    - Criar função que altera o alugado
    - Mostrar o reactive e vincular a algum elemento aletório do html
    - Passar a função para ser chamada dentro do componente
    - Refazer o componente com o objeto invés das variáveis

*/

</script>

<template>
    
    <CabecalhoFilme/>

    <hr/>

    <p v-on:click="alteraAlugado(1)" >Confira o catálogo de filmes:</p>

    <div class="catalogo">
        <Filme v-bind:alteraAlugado="alteraAlugado" v-bind:id="filmes[0].id" v-bind:nome="filmes[0].nome" v-bind:preco="filmes[0].preco" v-bind:alugado="filmes[0].alugado" />
        <Filme v-bind:alteraAlugado="alteraAlugado" v-bind:id="filmes[1].id" v-bind:nome="filmes[1].nome" v-bind:preco="filmes[1].preco" v-bind:alugado="filmes[1].alugado"/>
    </div>

</template>

<style>
    .catalogo{
        display: flex;
        gap: 10px;
    }
</style>