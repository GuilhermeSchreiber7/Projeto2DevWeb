<script setup>
defineProps(['dados']);

</script>
<template>
    <div>
        <div id="infosEnviadas">
                    <h1>SEUS DADOS</h1>
                    <p>Nome: {{ dados.nome }}</p>
                    <p>Nascimento: {{ dados.nascimento }}</p>
                    <p>Email: {{ dados.email }}</p>
                    <p>Cidade: {{ dados.cidade }}</p>
                    <p>Estado: {{ dados.estado }}</p>
                    <p>Hobbies: {{ dados.hobbies.join(', ') }}</p>
                    <p>Linguagem Preferida: {{ dados.linguagemProg }}</p>
                    <div class="Bio">
                        <p> Biografia: {{ dados.biografia }}</p>
                    </div>
                </div>
    </div>
</template>
<style scoped>
</style>