<template>
    <div class="watch">
        <div class="day"><Day v-bind:data="valueDay" /></div>
        <div class="date"><Dates v-bind:data="valueDates" /></div>
        <div class="hours"><Hour v-bind:data="valueHour" /></div>
        <div class="minutes"><Minute v-bind:data="valueMinute" /></div>
        <div class="ampm"><AmPm v-bind:data="valueHour" /></div>
        <div class="seconds"><Seconds v-bind:data="valueSeconds" /></div>        
    </div>
</template>

<script>
import AmPm from './AmPm.vue';
import Dates from './Dates.vue';
import Day from './Day.vue';
import Hour from './Hour.vue';
import Minute from './Minute.vue';
import Seconds from './Seconds.vue';

export default {
    name: 'Watch',
    components: {
        AmPm,
        Dates,
        Day,
        Hour,
        Minute,
        Seconds
    },
    data () {
        return {
            timer: null,
            time: "00:00:00",
            valueDates: [0, 0],
            valueDay: 0,
            valueHour: 0,
            valueMinute: 0,
            valueSeconds: 0
        }
    },
    methods: {
        procTime: (date) => {
            const hours = date.getHours();
            const minutes = date.getMinutes();
            const seconds = date.getSeconds();
            return [hours, minutes, seconds].join(':');
        }
    },
    beforeMount() {
        this.timer = setInterval(() => {
            //this.time = new Date()
            this.time = this.procTime(new Date())

            const date = new Date();
            this.valueHour = date.getHours();
            this.valueMinute = date.getMinutes();
            this.valueSeconds = date.getSeconds();
            
            const day = date.getDate();
            const month = date.getMonth();
            const year = date.getFullYear();
            this.valueDates = [year, month, day];
            
            this.valueDay = date.getDay();
            
        }, 1000)
    },
    beforeDestroy() {
        clearInterval(this.timer)
    }
}
</script>

<style scoped>
.watch {
    background-color: white; /*#cecece;*/
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 1px 1px;
    grid-auto-rows: 1fr 2fr 2fr 1fr;
    height: 100%;
    border-radius: 50%;
    border: 1px solid white;
    overflow: hidden;
}
.day {
    background-color: black;
    grid-column: 1 / 3;
    grid-row: 1;
}
.date {
    background-color: white;
    grid-column: 1 / 3;
    grid-row: 4;
}
.hours {
    background-color: maroon;
    grid-column: 1 / 2;
    grid-row: 2;
}
.minutes {
    background-color: cornflowerblue;
    grid-column: 1 / 2;
    grid-row: 3;
}
.ampm {
    background-color: yellow;
    grid-column: 2 / 3;
    grid-row: 2;
}
.seconds {
    background-color: aquamarine;
    grid-column: 2 / 3;
    grid-row: 3;
}
</style>