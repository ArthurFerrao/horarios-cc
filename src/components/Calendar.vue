<template>
    <div id="calendar">
        <Day v-for="(day, i) in days" :key="i" :day="day" :class="{'border': i!=0}"/>
    </div>
</template>

<script>
import Day from "./Day.vue"
export default {
  components: { Day },
  data: function() {
            return { 
                days: [
                  {name: "Segunda-feira", hours: [{},{},{},{},{}]},
                  {name: "Terça-feira", hours: [{},{},{},{},{}]},
                  {name: "Quarta-feira", hours: [{},{},{},{},{}]},
                  {name: "Quinta-feira", hours: [{},{},{},{},{}]},
                  {name: "Sexta-feira", hours: [{},{},{},{},{}]}
                ]
            }
        }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
#calendar {
    height: 80vh;
    display: grid;
    grid-template-columns: repeat(5,20%);
    background-color: rgba(56, 90, 161, 0.253);
    padding: 10px;
    border-radius: 1%;
}


</style>
