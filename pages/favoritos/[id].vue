<script setup>
    const route = useRoute();
    const {data:favoritos} = await useFetch(`http://localhost:8000/favoritos?usuario=${route.params.id}`)
</script>

<template>
    <div>
        <div v-for="favorito in favoritos" :key="favorito.id">
            <span> <strong>Id: </strong>{{ favorito.id }} </span> <br>
            <span> <strong>Filme: </strong>{{ favorito.idFilmeFK.nome }}, <strong>Descrição: </strong>{{ favorito.idFilmeFK.descricao }}</span> <br> <br>
            <img :src="`http://localhost:8000${favorito.idFilmeFK.banner}`" width="300" height="300" > <br>
            <span> <strong>Usuario: </strong>{{ favorito.idUsuarioFK.nome }}, <strong>Cpf: </strong>{{ favorito.idUsuarioFK.cpf }}</span> <br> <br>

        </div>
    </div>
</template>