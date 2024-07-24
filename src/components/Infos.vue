<script setup>
function EsconderPerfil() {
    showprofile.value = false
    form.value = true
}
</script>
<template>
    <div>
        <div id="infosEnviadas" v-show="showprofile">
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
                    <button @click="EsconderPerfil()">Voltar</button>
                </div>
    </div>
</template>
<style scoped>
</style>