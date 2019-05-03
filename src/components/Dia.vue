<template>
    <div class="dia">
        <p id="title">{{dia.nome}}</p>
        <Hora :aulas="aulas_08" hora="08" :class="{'border-right-left border-top': true}"/>
        <Hora :aulas="aulas_10" hora="10" :class="{'border-right-left': true}"/>
        <Hora hora="12" :class="{' black': true,}"/>
        <Hora :aulas="aulas_14" hora="14" :class="{'border-right-left': true}"/>
        <Hora :aulas="aulas_16" hora="16" :class="{'border-right-left': true}"/>
    </div>
</template>

<script>
import Hora from "./Hora.vue"
export default {
    components: { Hora },
    props: [ 'dia' ],
    computed: {
        aulas_08:function () {return this.dia.aulas.filter(aula => aula.horario.hora === "08")},
        aulas_10:function () {return this.dia.aulas.filter(aula => aula.horario.hora === "10")},
        aulas_14:function () {return this.dia.aulas.filter(aula => aula.horario.hora === "14")},
        aulas_16:function () {return this.dia.aulas.filter(aula => aula.horario.hora === "16")},
    }
}


</script>

<style>
.dia{
    height: 100%;
    display: grid;
    grid-template-rows: 40px 1fr 1fr 5% 1fr 1fr;
}
#title{
    align-self: center;
    justify-self: center;
    color: rgba(42, 55, 77, 0.747);
    font-weight: bold;
    font-size: 20px;
}
</style>
