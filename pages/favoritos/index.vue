<script setup>
    const {data:favoritos} = await useFetch('http://localhost:8000/favoritos')
</script>

<template>
    <div>
        <h1>Favoritos</h1>
        <div v-for="favorito in favoritos" :key="favorito.id">
            <span> <strong>Id: </strong> {{ favorito.id }} | </span>
            <span> <strong>Filme: </strong>id: {{ favorito.idFilmeFK.id }}, nome: {{ favorito.idFilmeFK.nome }} | </span>
            <span> <strong>Usuario: </strong>id: {{ favorito.idUsuarioFK.id }}, nome: {{ favorito.idUsuarioFK.nome }} | </span>
            <br>
        </div>
    </div>
</template>