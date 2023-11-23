<script setup>
    const {data:categorias} = await useFetch('http://localhost:8000/categoria')
</script>

<template>
    <div>
        <h1>Categorias</h1>
        <div v-for="categoria in categorias" :key="categoria.id">
            <span> <strong>Id: </strong> {{ categoria.id }} | </span>
            <span> <strong>Nome: </strong>{{ categoria.nome }} </span>
            <br>
        </div>
    </div>
</template>