<template>
  <div>
    <button @click="calcularMedia()" >Calcular</button>
    <p>{{media}}</p>
    <table>
        <tr>
            <th>Nome do Aluno</th>
            <th>Informação</th>
        </tr>
        <tr v-for="t in tabelaMedia" :key="t.aluno">
            <td>{{t.aluno}}</td>
            <td>{{t.infomacao}}</td>
        </tr>
    </table>
  </div>
</template>

<script>
export default {
    props:{
        nomeAluno: String,
        valor1: Number,
        valor2: Number,
        valor3: Number
    },
    data() {
        return {
            aprovado: ' ',
            media: 0,
            tabelaMedia:[
                {
                    aluno: this.nomeAluno,
                    infomacao: ''
                }
            ]
        }
    },
    methods: {
        calcularMedia() {
            this.media = (this.valor1 + this.valor2 * 2 + this.valor3 * 3)/6
            if(this.nomeAluno != ' '){
                if (this.media >= 7)  {
                    this.aprovado = 'Aprovado'  
                }else{
                    this.aprovado = 'Reprovado'
                }
                this.tabelaMedia.push({
                aluno: this.nomeAluno,
                infomacao: this.aprovado
                })
            }
        }
        
    }
}
</script>

<style>
.aprovado {
  background-color: blue;
}
.reprovado {
  background-color: red;
}
</style>