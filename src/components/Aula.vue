<template>
    <div class="aula">
        {{aula.disciplina}}-{{aula.turma}}
    </div>
</template>

<script>
export default {
    props: [ 'aula' ]
}
</script>

<style>
.aula{
    border-radius: 50px;
    padding-left: 5px;
    padding-right: 5px;
    display: inline-block;
    background-color: rgba(47, 2, 77, 0.664);
    border: 1px solid rgba(88, 0, 189, 0.692);
    color: rgb(255, 255, 255);
    font-weight: bold;
    font-size: 15px;
    margin: 2px;
}
</style>
