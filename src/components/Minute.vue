<template>
    <div class="minute-container">
        <div class="minute-content">{{ showValue }}</div>
    </div>
</template>

<script>
export default {
    name: 'Minute',
    props: {
        data: Number,
    },
    computed: {
        showValue: function() {
            return (this.data < 10)?'0'+this.data:this.data;
        }
    }
}
</script>

<style scoped>
.minute-container {
    background-color: transparent;
}
.minute-content {
    background-color: transparent;
    text-align: center;
    padding-top: 14px;
    font-family: 'Arial Black';
    font-size: 2.2em;
    font-weight: 600;
    text-transform: uppercase;
    line-height: 100%;
    letter-spacing: 0px;
    color: #000;
}
</style>