<script setup>
import { computed, reactive, ref } from 'vue';
import FormEdit from '@/components/FormEdit.vue';
import FormInfo from '@/components/FormInfo.vue';

const dados = ref('')

function salvar(item) {
  console.log(item)
  dados.value = item
}

const mostrarDados = computed(() => {
  return dados.value !== ''
})

</script>

<template>
  <div>
    <div class="container2">
      <FormEdit @salvar="salvar" />
    </div>
    <div class="containerApp">
      <FormInfo v-if="mostrarDados" :dadosEdit="dados" />

    </div>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');

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
</style>
