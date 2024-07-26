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
  <div >
   <div class="containerApp" v-if="!botao">
    <FormEdit  :dados-edit="perfil"/>
   <button v-if="perfil.senha ==perfil.confSenha && perfil.senha.length >= 8" @click="botao = !botao" type="submit">{{ nomeBotao }}</button>
    </div>
  <div class="container2" v-if="botao">
    <Infos :dados="perfil" />
    <button  @click="botao = !botao">{{ nomeBotao }}</button>
  </div>
</div>
</template>

<style scoped>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
 .containerApp{
  background-image: linear-gradient(to right, #273cc1, #ffffff, rgb(14, 14, 159));
  height: 100%;
  width: 100%;
  display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 2%;
}
.container2{
  display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  background-image: linear-gradient(to right, #273cc1, #ffffff, rgb(14, 14, 159));
  height: 100vh;
  width: 100vw;
}
 button{
      margin-top: 20px;
      padding: 10px;
      color: white;
      background-color: #0e52ff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
 }
</style>
