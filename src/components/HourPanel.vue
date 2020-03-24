<template>
    <div class="hour-container">
        <div class="hour-content">{{ $_Hour_showValue }}</div>
    </div>
</template>

<script>
export default {
    name: 'HourPanel',
    props: {
        data: Number,
    },
    computed: {
        $_Hour_showValue: function() {
            let hour = this.data % 12;
            hour = (hour === 0)?12:hour; 
            return (hour < 10)?'0'+hour:hour;
        }
    }
}
</script>

<style scoped>
.hour-container {
    background-color: transparent;
}
.hour-content {
    text-align: center;
    padding-top: 14px;
    font-family: 'Arial Black';
    font-size: 2.2em;
    font-weight: 600;
    text-transform: uppercase;
    line-height: 100%;
    letter-spacing: 0px;
    color: #fff;
}
</style>