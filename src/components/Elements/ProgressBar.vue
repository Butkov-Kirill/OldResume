<template lang="pug">
.progress-bar(id="progress-bar", ref="progress_bar", @mouseover="Rewind")
    .passed
    .slider
</template>

<script>
export default {
    data(){
        return {
            ProgressBar : null
        }
    },
    methods: {
        Rewind(){
            this.ProgressBar.onmouseup = (e) => {
                this.$refs.progress_bar.style.setProperty('--progress', e.offsetX-5+'px');
            }
        }
    },
    mounted(){
        this.$nextTick(function(){
            let bar = this.$refs.progress_bar;
            this.ProgressBar = bar;
        })
    }
}
</script>

<style lang="scss">
:root{
    --height: 4px;
    --width: 90%;
    --bg: #fff;
    --progress: 0%;
    --color: rgb(233, 15, 15);
    --size_slider: 10px;
    --slider_color: #ccc;
}

.progress-bar{
    display: flex;
    height: var(--height);
    width: var(--width);
    background: var(--bg);

    .passed {
        height: 100%;
        width: var(--progress);
        background: var(--color);
        &:hover::before{
            content: ' ';
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.651);
            z-index: 5;
        }
    }

    .slider {
        position: absolute;
        width: var(--size_slider);
        height: var(--size_slider);
        border-radius: 50%;
        background: var(--slider_color);
        top: 50%;
        left: var(--progress);
        transform: translate(0, -50%);
    }
}
</style>