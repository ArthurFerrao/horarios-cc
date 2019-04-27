<template>
    <div class="day">
        <p id="title">{{day.name}}</p>
        <Hour v-for="(hour, i) in day.hours" :key="i"/>
    </div>
</template>

<script>
import Hour from "./Hour.vue"
export default {
    components: { Hour },
    props: {
        day: {type: Object}
    }
}
</script>

<style>
.day{
    height: 100%;
    display: grid;
    grid-template-rows: 10% repeat(5,1fr);
    grid-row-gap: 3px;
    padding: 3px;
}
#title{
    align-self: center;
    justify-self: center;
    color: rgba(42, 55, 77, 0.747);
}
.border{
    border-left: 2px solid rgba(0, 0, 255, 0.1);
}
</style>
