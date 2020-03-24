<template>
    <div class="ampm-container">
        <div class="ampm-content">{{ $_AmPm_showValue }}</div>
    </div>
</template>

<script>
export default {
    name: 'AmPmPanel',
    props: {
        data: Number,
    },
    computed: {
        $_AmPm_showValue: function() {
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