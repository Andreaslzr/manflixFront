<script setup>
    const {data:filmes} = await useFetch('http://localhost:8000/filmes')
</script>

<template>
    <div>
        <h1>Filmes</h1>
        <div v-for="filme in filmes" :key="filme.id">
            <h2> <strong>Titulo: </strong>{{ filme.nome }} </h2>
            <NuxtLink :to="`/filmes/${filme.id}`">
                <img :src="`http://localhost:8000${filme.banner}`" width="1200" height="500" >
            </NuxtLink>
            <br> <br>
            <h2>___________________________________________________________________________________________________________________________________________________________________</h2>
            <br>
        </div>
    </div>
</template>