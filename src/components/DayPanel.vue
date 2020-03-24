<template>
    <div class="day-container">
        <div class="day-content">
            {{ $_Day_showDay }}
        </div>
    </div>
</template>

<script>
export default {
    name: 'Day',
    computed: {
        $_Day_showDay: function() {
            const nameDay = [
                "Sunday",
                "Monday",
                "Tuesday",
                "Wednesday",
                "Thursday",
                "Friday"
            ]
            return nameDay[this.data]
        }
    },
    props: {
        data: Number,
    }
}
</script>

<style scoped>
.day-container {
    background-color: transparent;
}
.day-content {
    text-align: center;
    padding-top: 10px;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 0.9em;
    font-weight: 600;
    color: #fff;
}
</style>
