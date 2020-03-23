<template>
    <div class="dates-container">
        <div class="dates-content">{{ showValue }}</div>
    </div>
</template>

<script>
export default {
    name: 'Dates',
    props: {
        data: Array,
    },
    computed: {
        showValue: function() {
            
            const monthName = [
                "January",
                "February",
                "March",
                "April",
                "May",
                "June",
                "July",
                "August",
                "September",
                "October",
                "November",
                "December"
            ]
            const month = monthName[this.data[1]];
            
            return [month, this.data[2]].join(' ')
        }
    }
}
</script>

<style scoped>
.dates-container {
    background-color: #fff;
}
.dates-content {
    text-align: center;
    padding-top: 6px;
    font-size: 0.8em;
    font-weight: 600;
    font-family: "Arial Black";
    text-transform: uppercase;
    color: #000;
}
</style>