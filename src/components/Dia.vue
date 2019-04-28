<template>
    <div class="dia">
        <p id="title">{{dia.nome}}</p>
        <Hora :aulas="dia.aulas" hora="08" :class="{'border-right-left border-top': true}"/>
        <Hora :aulas="dia.aulas" hora="10" :class="{'border-right-left': true}"/>
        <Hora hora="12" :class="{' black': true,}"/>
        <Hora :aulas="dia.aulas" hora="14" :class="{'border-right-left': true}"/>
        <Hora :aulas="dia.aulas" hora="16" :class="{'border-right-left': true}"/>
    </div>
</template>

<script>
import Hora from "./Hora.vue"
export default {
    components: { Hora },
    props: [ 'dia' ]
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
