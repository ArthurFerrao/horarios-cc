<template>
    <div class="hora" >
        <Aula v-for="(aula, i) in aulas" :key="i" :aula="aula" v-show='aula.horario.hora == hora'/>
    </div>
</template>

<script>
import Aula from "./Aula.vue"
export default {
    components: { Aula },
    props: [ 'hora','aulas' ]
}
</script>

<style>
.hora{
    background-color: rgba(36, 33, 33, 0.082);
    border-bottom: 2px dashed rgba(34, 82, 145, 0.377);
    padding: 7px;
    overflow-y: auto;
}
.border-right-left{
    margin-right: 3px;
    margin-left: 3px;
}
.black{
    background-color: rgba(0, 0, 0, 0.199);
    border-radius: 0%;
}
.border-top{
    border-top: 2px dashed rgba(34, 82, 145, 0.377);
}
</style>
