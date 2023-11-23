<script setup>
    const {data:assinaturas} = await useFetch('http://localhost:8000/assinatura')
</script>


<template>
    <div>
        <h1>Assinaturas disponiveis</h1>
        <div v-for="assinatura in assinaturas" :key="assinatura.id">
            <span> <strong>Id: </strong> {{ assinatura.id }} | </span>
            <span> <strong>Nome: </strong>{{ assinatura.nome }} | </span>
            <span> <strong>Valor: </strong>{{ assinatura.valor }} </span>
            <br>
        </div>
    </div>
</template>