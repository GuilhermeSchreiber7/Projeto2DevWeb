<script setup>
import { ref } from 'vue'

const emit = defineEmits(['mandarPerfil'])

const Estados = [
    { uf: 'AC', nome: 'Acre' },
    { uf: 'AL', nome: 'Alagoas' },
    { uf: 'AP', nome: 'Amapá' },
    { uf: 'AM', nome: 'Amazonas' },
    { uf: 'BA', nome: 'Bahia' },
    { uf: 'CE', nome: 'Ceará' },
    { uf: 'DF', nome: 'Distrito Federal' },
    { uf: 'ES', nome: 'Espírito Santo' },
    { uf: 'GO', nome: 'Goiás' },
    { uf: 'MA', nome: 'Maranhão' },
    { uf: 'MT', nome: 'Mato Grosso' },
    { uf: 'MS', nome: 'Mato Grosso do Sul' },
    { uf: 'MG', nome: 'Minas Gerais' },
    { uf: 'PA', nome: 'Pará' },
    { uf: 'PB', nome: 'Paraíba' },
    { uf: 'PR', nome: 'Paraná' },
    { uf: 'PE', nome: 'Pernambuco' },
    { uf: 'PI', nome: 'Piauí' },
    { uf: 'RJ', nome: 'Rio de Janeiro' },
    { uf: 'RN', nome: 'Rio Grande do Norte' },
    { uf: 'RS', nome: 'Rio Grande do Sul' },
    { uf: 'RO', nome: 'Rondônia' },
    { uf: 'RR', nome: 'Roraima' },
    { uf: 'SC', nome: 'Santa Catarina' },
    { uf: 'SP', nome: 'São Paulo' },
    { uf: 'SE', nome: 'Sergipe' },
    { uf: 'TO', nome: 'Tocantins' }
]
 defineProps({
    dados: {
        type: Object,
        required: true
    }
})


const showprofile = ref(false)
const form = ref(true)

function mandarPerfil() {
    showprofile.value = true
    form.value = false
    emit('mandarPerfil', dados);
}

</script>
<template>
    <div>
        <div class="containerForm" v-show="form">
                    <h1>SUAS INFORMAÇÕES</h1>
                    <form @submit.prevent="mandarPerfil()">
                        <div class="InputLabel">
                            <label for="inputName">Nome</label>
                            <input type="text" v-model.trim="dados.nome" placeholder="Digite seu nome" id="inputName"
                                required />
                        </div>
                        <div class="InputLabel">
                            <label for="inputEmail">Email</label>
                            <input id="inputEmail" type="email" v-model.trim="dados.email"
                                placeholder="Digite seu email" required>
                        </div>
                        <div class="InputLabel">
                            <label for="inputSenha">Senha (min. 
                                8 caracteres)</label>
                            <input id="inputSenha" type="password" v-model.trim="dados.senha"
                                placeholder="Digite sua Senha" required>
                        </div>
                        <div class="InputLabel">
                            <label for="inputConfSenha">Confirmação de Senha</label>
                            <input id="inputConfSenha" type="password" v-model.trim="dados.confSenha"
                                placeholder="Confirme sua Senha" required>
                        </div>
                        <div class="InputLabel">
                            <label for="inputAge">Nascimento</label>
                            <input id="inputAge" type="date" v-model.date="dados.nascimento"
                                placeholder="Digite sua Nascimento " required>
                        </div>
                        <div class="InputLabel">
                            <label for="inputCEP">CEP</label>
                            <input id="inputCEP" type="number" v-model="dados.cep" placeholder="Digite seu CEP"
                                required>
                        </div>
                        <div class="InputLabel">
                            <label for="inputCEP">Cidade</label>
                            <input id="inputCEP" type="text" v-model="dados.cidade" placeholder="Digite sua Cidade"
                                required>
                        </div>
                        <div class="InputLabel">
                            <label for="inputEstado">Estado</label>

                            <select id="inputEstado" value="Estado" v-model="dados.estado" required>
                                <option v-for="Estado of Estados" :key="Estado.uf" :value="Estado.uf">
                                    {{ Estado.nome }}
                                </option>
                            </select>
                        </div>
                        <div>
                            <p class="titulo">Hobbies:</p>
                            <input type="checkbox" id="hobbies1" value="Esporte" v-model="dados.hobbies">
                            <label for="hobbies1">Esportes</label>

                            <input type="checkbox" id="hobbies2" value="Viagens" v-model="dados.hobbies">
                            <label for="hobbies2">Viagens</label>

                            <input type="checkbox" id="hobbies3" value="Música" v-model="dados.hobbies">
                            <label for="hobbies3">Músicas</label>

                            <input type="checkbox" id="hobbies4" value="Leitura" v-model="dados.hobbies">
                            <label for="hobbies4">Leitura</label>

                            <input type="checkbox" id="hobbies5" value="VIdeoGame" v-model="dados.hobbies">
                            <label for="hobbies5">Video Game</label>
                        </div>
                        <div>
                            <p class="titulo">Linguagem preferida:</p>
                            <input type="radio" id="Js" value="JavaScript" v-model="dados.linguagemProg">
                            <label for="Js">JavaScript</label>

                            <input type="radio" id="Java" value="Java" v-model="dados.linguagemProg">
                            <label for="Java">Java</label>

                            <input type="radio" id="C" value="C" v-model="dados.linguagemProg">
                            <label for="C">C</label>

                            <input type="radio" id="Py" value="Python" v-model="dados.linguagemProg">
                            <label for="Py">Python</label>

                            <input type="radio" id="C#" value="C#" v-model="dados.LinguagemProg">
                            <label for="C#">C#</label>
                        </div>
                        <div class="inputBio">
                            <label for="bio">Biografia</label>
                            <textarea type="text" id="bio" placeholder="Sua Biografia (opcional)"
                                v-model="dados.Biografia"></textarea>
                        </div>

                        <div class="botaoEnviar">
                            <button v-if="dados.senha == dados.confSenha && dados.senha.length >= 8"
                                type="submit">Enviar</button>
                        </div>
                    </form>
                </div>
    </div>
</template>
<style scoped>
</style>