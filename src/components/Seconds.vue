<template>
    <div class="seconds-container">
        <div class="seconds-content">{{ showValue }}</div>
    </div>
</template>

<script>
export default {
    name: 'Seconds',
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
.seconds-container {
    background-color: transparent;
}
.seconds-content {
    text-align: center;
    padding-top: 14px;
    font-family: 'Arial Black';
    font-size: 2.2em;
    font-weight: 600;
    text-transform: uppercase;
    line-height: 100%;
    letter-spacing: 0px;
    /*
    font-family: arial;
    font-size: 2.1em;
    */
}
</style>