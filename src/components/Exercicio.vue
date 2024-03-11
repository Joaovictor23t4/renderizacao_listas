
<template>
    <div v-show="exercicioShow !== 0" class="exit">
        <button @click="exercicioShow = 0" class="buttonExit">X</button>
    </div>
  
    <div v-if="exercicioShow === 0" class="container-show-opcoes">
        <div class="container-opcoes">
            <button @click="exercicioShow = 1" class="buttonExibir" style="background-color: red;">Exercicio 1</button>
        </div>
        <div class="container-opcoes">
            <button @click="exercicioShow = 2" class="buttonExibir" style="background-color: blue;">Exercicio 2</button>
        </div>
    </div>
  
    <div v-else-if="exercicioShow === 1" class="exercicio">
        <div class="container">
          <h1>Cidades</h1>
          <ul>
            <li v-for="(cidades, cidadesIndex) in cidades" :key="cidadesIndex">{{ cidades }}</li>
          </ul>    
        </div>
    </div>
  
    <div v-else-if="exercicioShow === 2" class="exercicio">
  
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue'
  
  const exercicioShow = ref(0);
  const cidades = ref([
  'São Paulo',
  'Rio de Janeiro',
  'Belo Horizonte',
  'Salvador',
  'Fortaleza',
  'Curitiba',
  'Manaus',
  'Recife',
  'Porto Alegre',
  'Brasília',
  ]);
  </script>
  
  <style scoped>
  button {
    width: 50px;
    border: none;
    font-size: 2rem;
  }
  
  .exit {
    position: absolute;
    top: 0;
    right: 0;
    margin: 10px 10px 0 0;
  }
  
  .buttonExit {
    cursor: pointer;
  }
  
  .container-show-opcoes {
    display: flex;
    justify-content: flex-start;
    gap: 10px;
  }
  
  .exercicio {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 20px;
  }
  
  .container {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
  }
  
  .container-input > label {
    position: relative;
    right: 5px;
  }
  
  .reload-icon {
    position: relative;
    bottom: 1px;
    cursor: pointer;
  }
  
  .liberar-evento {
    color: blue;
    cursor: pointer;
  }
  
  .bloquear-evento {
    color: black;
    opacity: .5;
    cursor: not-allowed;
  }
  
  .somaMaior {
    background-color: green;
    color: #fdfdfd;
    padding: 10px;
  }
  
  .somaIgual {
    background-color: blue;
    color: #fdfdfd;
    padding: 10px;
  }
  
  .somaMenor {
    background-color: red;
    color: #fdfdfd;
    padding: 10px;
  }
  
  .somaMaior, .somaIgual, .somaMenor {
    margin-left: 10px;
  }
  
  .buttonExibir {
    color: #fdfdfd;
    font-size: 1.8rem;
    width: 200px;
    cursor: pointer;
  }
  </style>