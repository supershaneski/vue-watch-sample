<template>
    <div class="ampm-container">
        <div class="ampm-content">{{ showValue }}</div>
    </div>
</template>

<script>
export default {
    name: 'AmPm',
    props: {
        data: Number,
    },
    computed: {
        showValue: function() {
            return (this.data >= 12)?'pm':'am';
        }
    }
}
</script>

<style scoped>
.ampm-container {
    background-color: transparent;
}
.ampm-content {
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