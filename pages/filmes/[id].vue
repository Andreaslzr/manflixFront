<script setup>
    const route = useRoute();
    const {data:filmes} = await useFetch(`http://localhost:8000/filmes/${route.params.id}`)
</script>

<template>
    <div>
            <p> <strong>Id: </strong> {{ filmes.id }}, </p>
            <p> <strong>Categoria: </strong>id: {{ filmes.idCategoriaFK.id}}, nome: {{ filmes.idCategoriaFK.nome }}</p>
            <p> <strong>Titulo: </strong>{{ filmes.nome }},</p>
            <p> <strong>Descrição: </strong>{{ filmes.descricao }},</p>
            <h3>Foto:</h3>
            <img :src="`http://localhost:8000${filmes.foto}`" width="1200" height="500" >
            <h3>Banner:</h3>
            <img :src="`http://localhost:8000${filmes.banner}`" width="1200" height="500" >
            <h3>Logo:</h3>
            <img :src="`http://localhost:8000${filmes.logo}`" width="1200" height="500" >
            
    </div>
</template>