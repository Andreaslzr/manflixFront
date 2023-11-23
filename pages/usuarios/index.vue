<script setup>
    const {data:usuarios} = await useFetch('http://localhost:8000/usuarios')
</script>

<template>
    <div>
        <h1>Usuarios</h1>
        <div v-for="usuario in usuarios" :key="usuario.id">
            <span> <strong>Id: </strong> {{ usuario.id }} | </span>
            <span> <strong>Assinatura: </strong>{{ usuario.idAssinaturaFK.nome }}, Valor: {{ usuario.idAssinaturaFK.valor }} | </span>
            <span> <strong>Usuario: </strong>{{ usuario.nome}} | </span>
            <span> <strong>cpf: </strong>{{ usuario.cpf}} </span> <br> <br>
            <NuxtLink :to="`/favoritos/${usuario.id}`">
                <img :src="`http://localhost:8000${usuario.foto}`" width="500" height="500" >
            </NuxtLink>
            <h2>___________________________________________________________________________________________________________________________________________________________________</h2>
            <br>
        </div>
    </div>
</template>