<script setup>
import { reactive } from 'vue';
import Form from '@/components/Form.vue';
import Infos from '@/components/Infos.vue';

const dados = reactive({
    nome: '',
    senha: '',
    confSenha: '',
    nascimento: '',
    email: '',
    cep: '',
    cidade: '',
    estado: '',
    hobbies: [],
    linguagemProg: '',
    biografia: ''
});

function getPerfil(dados) {
  console.log(dados);
}

</script>

<template>
   <div>
    <Form :dados="dados" @mandar-perfil="getPerfil"/>
    <Infos :dados="dados" />
   </div>
</template>

<style scoped>

</style>
