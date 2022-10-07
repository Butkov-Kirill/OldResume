<script>
export default {
    props:{
        Procentages:{
            type: String,
            default: "50%"
        }
    }
}
</script>

<template lang="pug">
.chart
    .chart-line
        span.procentages {{Procentages}}
</template>

<style lang="scss">

.chart{
    width: 100px;
    height: 100px;
    background: rgb(255, 255, 255);
    border-radius: 50%;
    overflow: hidden;
    position: relative;
    margin: 0 auto;
    margin-top: auto;
    margin-bottom: 0em;
    box-shadow: 2px 2px 20px rgba(0, 0, 0, 0.13);
    aspect-ratio: 1;
    display: inline-grid;

    .chart-line{
        position: absolute;
        top: 3px;
        left: 3px;
        right: 3px;
        bottom: 3px;
        background: rgb(238, 238, 238);
        z-index: 5;
        border-radius: 50%;
        display: flex;
    }

    .procentages{
        font-size: 36px;
        font-family: 'Montserrat Light', sans-serif;
        font-weight: lighter;
        margin: auto auto;
    }
}

.chart:before{
    content: "";
    position: absolute;
    border-radius: 50%;
    inset: 0;
    background: conic-gradient(var(--c) calc(var(--p)*1%),#0000 0);
}
</style>