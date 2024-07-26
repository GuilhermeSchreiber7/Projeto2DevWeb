<script setup>
import { reactive } from 'vue'
defineProps(['dados']);

</script>
<template>
    <div class="container">
        <div id="infosEnviadas">
                    <h1>SEUS DADOS</h1>
                    <p>Nome: {{ perfil.nome }}</p>
                    <p>Nascimento: {{ perfil.nascimento }}</p>
                    <p>Email: {{ perfil.email }}</p>
                    <p>Cidade: {{ perfil.cidade }}</p>
                    <p>Estado: {{ perfil.estado }}</p>
                    <p>Hobbies: {{ perfil.hobbies.join(', ') }}</p>
                    <p>Linguagem Preferida: {{ perfil.linguagemProg }}</p>
                    <div class="Bio">
                        <p> Biografia: {{ perfil.biografia }}</p>
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