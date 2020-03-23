<template>
    <div class="hour-container">
        <div class="hour-content">{{ showValue }}</div>
    </div>
</template>

<script>
export default {
    name: 'Hour',
    props: {
        data: Number,
    },
    computed: {
        showValue: function() {
            const date = (this.data + 1) % 13;
            return (date < 10)?'0'+date:date;
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