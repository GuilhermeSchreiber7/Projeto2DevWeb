<script setup>
defineProps(['dados']);

</script>
<template>
    <div class="container">
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
    .container {
        display: flex;
        justify-content: center;
        align-items: center;
        max-width: 200px;
        margin: auto;
    }
    #infosEnviadas {
        background: rgba( 255, 255, 255, 0.5 );
        padding: 20px;
        border-radius: 10px;
        margin-top: 20px;
    }
    .Bio {
        margin-top: 20px;
    }
    p {
        margin: 10px 0;
    }
    h1 {
        margin-bottom: 20px;
    }

</style>