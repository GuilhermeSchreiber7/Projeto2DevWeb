<script setup>
import { reactive } from 'vue'
 const props = defineProps({
    dadosEdit: {
        type: Object,
        required: true
    }
})

console.log(props.dadosEdit)

</script>
<template>
    <div class="container">
        <div id="infosEnviadas">
            <h1>SEUS DADOS</h1>
            <p>Nome: {{ props.dadosEdit.nome }}</p>
            <p>Nascimento: {{ props.dadosEdit.nascimento }}</p>
            <p>Email: {{ props.dadosEdit.email }}</p>
            <p>Cidade: {{ props.dadosEdit.cidade }}</p>
            <p>Estado: {{ props.dadosEdit.estado }}</p>
            <p>Hobbies: {{ props.dadosEdit.hobbies }}</p>
            <p>Linguagem Preferida: {{ props.dadosEdit.linguagemProg }}</p>
            <div class="Bio">
                <p> Biografia: {{ props.dadosEdit.biografia }}</p>
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
    background: rgba(255, 255, 255, 0.5);
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
}</style>