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
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    max-width: 300px;
    margin: auto;
}

#infosEnviadas {
    background: rgba(255, 255, 255, 0.5);
    padding: 20px;
    border-radius: 10px;
}

.Bio {
    margin-top: 20px;
    max-width: 100px;
    
}

p {
    margin: 10px 0;
    font-size: 22px;
}

h1 {
    margin-bottom: 20px;
}</style>