<script setup>
import { computed, reactive, ref } from 'vue';
import FormEdit from '@/components/FormEdit.vue';
import FormInfo from '@/components/FormInfo.vue';


const botao = ref(false);
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

</script>

<template>
  <div>
    <div class="container2" v-if="botao">
      <FormInfo :dados="dados-edit" />
      <button @click="botao = !botao">{{ nomeBotao }}</button>
    </div>
    <div class="containerApp" v-else>
      <FormEdit  @salvar="botao= true" :dados-edit="perfil" />
      
    </div>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.containerApp {
  background-image: linear-gradient(to right, #273cc1, #ffffff, rgb(14, 14, 159));
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 2%;
}

.container2 {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-image: linear-gradient(to right, #273cc1, #ffffff, rgb(14, 14, 159));
  height: 100vh;
  width: 100vw;
}

button {
  margin-top: 20px;
  padding: 10px;
  color: white;
  background-color: #0e52ff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}</style>
