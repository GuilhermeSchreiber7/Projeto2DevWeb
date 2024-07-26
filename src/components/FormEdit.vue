<script setup>
import { ref, computed, reactive } from 'vue'
defineProps({
    dadosEdit: {
        type: Object,
        required: true
    }
})
const emit = defineEmits(['salvar'])

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
const botao = ref(false)

const nomeBotao = computed(() => {
    return botao.value ? 'Esconder' : 'Mostrar';
});

function enviar() {
    //  validacoes
    // else
    emit('salvar', {...perfil} )
}

</script>
<template>
    <body class="background">
        <div class="containerForm">
            <main>
                <form @submit.prevent="enviar">
                    <h1>SUAS INFORMAÇÕES</h1>
                    <div class="InputLabel">
                        <label for="inputName">Nome</label>
                        <input type="text" v-model.trim="perfil.nome" placeholder="Digite seu nome" id="inputName"
                            required />
                    </div>
                    <div class="InputLabel">
                        <label for="inputEmail">Email</label>
                        <input id="inputEmail" type="email" v-model.trim="perfil.email" placeholder="Digite seu email"
                            required>
                    </div>
                    <div class="InputLabel">
                        <label for="inputSenha">Senha (min.
                            8 caracteres)</label>
                        <input id="inputSenha" type="password" v-model.trim="perfil.senha" placeholder="Digite sua Senha"
                            required>
                    </div>
                    <div class="InputLabel">
                        <label for="inputConfSenha">Confirmação de Senha</label>
                        <input id="inputConfSenha" type="password" v-model.trim="perfil.confSenha"
                            placeholder="Confirme sua Senha" required>
                    </div>
                    <div class="InputLabel">
                        <label for="inputAge">Nascimento</label>
                        <input id="inputAge" type="date" v-model="perfil.nascimento" placeholder="Digite sua Nascimento "
                            required>
                    </div>
                    <div class="InputLabel">
                        <label for="inputCEP">CEP</label>
                        <input id="inputCEP" type="number" v-model="perfil.cep" placeholder="Digite seu CEP" required>
                    </div>
                    <div class="InputLabel">
                        <label for="inputCity">Cidade</label>
                        <input id="inputCity" type="text" v-model="perfil.cidade" placeholder="Digite sua Cidade"
                            required>
                    </div>
                    <div class="InputLabel">
                        <label for="inputEstado">Estado</label>

                        <select id="inputEstado" value="Estado" v-model="perfil.estado" required>
                            <option v-for="Estado of Estados" :key="Estado.uf" :value="Estado.uf">
                                {{ Estado.nome }}
                            </option>
                        </select>
                    </div>
                    <div>
                        <p class="titulo">Hobbies:</p>
                        <input type="checkbox" id="hobbies1" value="Esporte" v-model="perfil.hobbies">
                        <label for="hobbies1">Esportes</label>

                        <input type="checkbox" id="hobbies2" value="Viagens" v-model="perfil.hobbies">
                        <label for="hobbies2">Viagens</label>

                        <input type="checkbox" id="hobbies3" value="Música" v-model="perfil.hobbies">
                        <label for="hobbies3">Músicas</label>

                        <input type="checkbox" id="hobbies4" value="Leitura" v-model="perfil.hobbies">
                        <label for="hobbies4">Leitura</label>

                        <input type="checkbox" id="hobbies5" value="VIdeoGame" v-model="perfil.hobbies">
                        <label for="hobbies5">Video Game</label>
                    </div>
                    <div>
                        <p class="titulo">Linguagem preferida:</p>
                        <input type="radio" id="Js" value="JavaScript" v-model="perfil.linguagemProg">
                        <label for="Js">JavaScript</label>

                        <input type="radio" id="Java" value="Java" v-model="perfil.linguagemProg">
                        <label for="Java">Java</label>

                        <input type="radio" id="C" value="C" v-model="perfil.linguagemProg">
                        <label for="C">C</label>

                        <input type="radio" id="Py" value="Python" v-model="perfil.linguagemProg">
                        <label for="Py">Python</label>

                        <input type="radio" id="C#" value="C#" v-model="perfil.LinguagemProg">
                        <label for="C#">C#</label>
                    </div>
                    <div class="inputBio">
                        <label for="bio">Biografia</label>
                        <textarea type="text" id="bio" placeholder="Sua Biografia (opcional)"
                            v-model="perfil.biografia"></textarea>
                    </div>
                    <button @click="enviar"
                        type="submit">{{ nomeBotao }}</button>
                </form>
            </main>
        </div>
    </body>
</template>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

.containerForm {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 20px;
    border-radius: 10px;
    width: 40%;
    margin: 0 auto;
    padding: 10px 100px;
    max-width: 500px;
    background: rgba(255, 255, 255, 0.5);
    ;
    font-family: "Poppins", sans-serif;
    backdrop-filter: blur(10px);
    box-shadow: 0px 0px 1.5px rgba(0, 0, 0, 0.048),
        0px 0px 3.2px rgba(0, 0, 0, 0.071),
        0px 0px 5.3px rgba(0, 0, 0, 0.088),
        0px 0px 7.7px rgba(0, 0, 0, 0.102),
        0px 0px 10.9px rgba(0, 0, 0, 0.115),
        0px 0px 15.2px rgba(0, 0, 0, 0.128),
        0px 0px 21.3px rgba(0, 0, 0, 0.142),
        0px 0px 30.7px rgba(0, 0, 0, 0.159),
        0px 0px 47.4px rgba(0, 0, 0, 0.182),
        0px 0px 101px rgba(0, 0, 0, 0.23)
}

main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100%;
}

h1 {
    font-size: 20px;
    font-weight: bold;
}

.InputLabel {
    display: flex;
    flex-direction: column;
    margin: 10px 0;
}

.InputLabel label {
    font-weight: bold;
}

.InputLabel input {
    padding: 5px;
    border-radius: 5px;
    border: 1px solid #000;
}

.titulo {
    display: flex;
    font-weight: bold;
    justify-content: center;
}

.inputBio {
    display: flex;
    flex-direction: column;
    margin: 10px 0;
}

.inputBio label {
    font-weight: bold;
}

.inputBio textarea {
    max-width: 300px;
    max-height: 200px;
    padding: 5px;
    border-radius: 5px;
    border: 1px solid #000;
}

textarea {
    resize: none;
    padding: 5px;
    border-radius: 5px;
    border: 1px solid #ccc;
}</style>