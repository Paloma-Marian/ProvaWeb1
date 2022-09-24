<template>
  <div>
    <h1>Calculo de Média de Aproveitamento</h1>

    <label>Nome do Aluno:</label> <br>
    <input type="text" v-model="nome" required> <br>
    <label>1ª Nota:</label> <br>
    <input type="number" v-model="nota1" required> <br>
    <label>2ª Nota:</label> <br>
    <input type="number" v-model="nota2" required> <br>
    <label>3ª Nota:</label> <br>
    <input type="number" v-model="nota3" required> <br>
    <p>nota: {{nota1}} nota: {{nota2}} nota: {{nota3}} nome: {{nome}}</p>

    <media-prova
      :nomeAluno="nome"
      :valor1="nota1"
      :valor2="nota2"
      :valor3="nota3">
    </media-prova>
  </div>
</template>

<script>
import MediaProva from './components/MediaProva.vue'

export default {
  name: 'App',
  components: {
    MediaProva
  },
  data(){
    return{
      nota1: 0,
      nota2: 0,
      nota3: 0,
      nome: ' '
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
