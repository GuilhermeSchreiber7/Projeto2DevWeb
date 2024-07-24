<script setup>
import { computed, reactive, ref } from 'vue';
import Infos from '@/components/FormInfo.vue';
import FormEdit from '@/components/FormEdit.vue';

const perfil = reactive({
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
const nomeBotao = computed(() => {
   return botao.value ? 'Esconder' : 'Mostrar';
});
const botao = ref(false)


</script>

<template>
   <div v-if="!botao">
    <form>
    <FormEdit  :dados-edit="perfil"/>
   <button v-if="perfil.senha ==perfil.confSenha && perfil.senha.length >= 8" @click="botao = !botao" type="submit">{{ nomeBotao }}</button>
    </form>
    </div>
  <div v-if="botao">
    <Infos :dados="perfil" />
    <button  @click="botao = !botao">{{ nomeBotao }}</button>
  </div>
</template>

<style scoped>

</style>
