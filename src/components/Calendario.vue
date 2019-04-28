<template>
    <div id="calendario">
        <div  id="grid-hora">
            <p class="hora-titulo" v-for="(hora, i) in horas" :key="i"> {{hora}}</p>
        </div>
        <Dia v-for="(dia, i) in dias" :key="i" :dia="dia"/>
    </div>
</template>

<script>
import Dia from "./Dia.vue"
import axios from 'axios'
export default {
  components: { Dia },
  data: function() {
            let aulas_seg, aulas_ter, aulas_qua, aulas_qui, aulas_sex = [];
            return { 
                dias: [
                  {nome: "Segunda", aulas: []},
                  {nome: "Terça", aulas: []},
                  {nome: "Quarta", aulas: []},
                  {nome: "Quinta", aulas: []},
                  {nome: "Sexta", aulas: []}
                ],
                horas: [
                    "8:00","10:00","12:00","14:00","16:00","18:00",
                ]
            }
  },
  mounted() {
    axios
      .get('http://localhost:3000/horarios/segunda')
      .then(response => (
        this.dias[0].aulas =  response.data
      ))
    axios
      .get('http://localhost:3000/horarios/terca')
      .then(response => (
        this.dias[1].aulas =  response.data
      ))
    axios
      .get('http://localhost:3000/horarios/quarta')
      .then(response => (
        this.dias[2].aulas =  response.data
      ))
    axios
      .get('http://localhost:3000/horarios/quinta')
      .then(response => (
        this.dias[3].aulas =  response.data
      ))
    axios
      .get('http://localhost:3000/horarios/sexta')
      .then(response => (
        this.dias[4].aulas =  response.data
      ))
  }
}
</script>

<style>
#calendario {
    height: 80vh;
    display: grid;
    grid-template-columns: 70px repeat(5,1fr);
    padding: 10px;
    border-radius: 1%;
    
}
#grid-hora{
    display: grid;
    grid-template-rows: 40px 1fr 1fr 5% 1fr 1fr ; 
    height: 100%;
}

.hora-titulo{
    align-self: end;
    position: relative;
    bottom: -23px;
    justify-self: center;
    color: rgba(21, 67, 128, 0.582);
    font-weight: bold;
    font-size: 15px;
}

</style>
