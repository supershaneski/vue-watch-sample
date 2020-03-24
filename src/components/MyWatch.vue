<template>
    <div class="watch">
        <div class="day"><DayPanel v-bind:data="valueDay" /></div>
        <div class="date"><DatesPanel v-bind:data="valueDates" /></div>
        <div class="hours"><HourPanel v-bind:data="valueHour" /></div>
        <div class="minutes"><MinutePanel v-bind:data="valueMinute" /></div>
        <div class="ampm"><AmPmPanel v-bind:data="valueHour" /></div>
        <div class="seconds"><SecondsPanel v-bind:data="valueSeconds" /></div>        
    </div>
</template>

<script>
import AmPmPanel from './AmPmPanel.vue';
import DatesPanel from './DatesPanel.vue';
import DayPanel from './DayPanel.vue';
import HourPanel from './HourPanel.vue';
import MinutePanel from './MinutePanel.vue';
import SecondsPanel from './SecondsPanel.vue';

export default {
    name: 'MyWatch',
    components: {
        AmPmPanel,
        DatesPanel,
        DayPanel,
        HourPanel,
        MinutePanel,
        SecondsPanel
    },
    data () {
        return {
            timer: null,
            valueDates: [0, 0],
            valueDay: 0,
            valueHour: 0,
            valueMinute: 0,
            valueSeconds: 0
        }
    },
    beforeMount() {
        this.timer = setInterval(() => {
            
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