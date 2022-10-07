<script>
export default {
        name: 'Skils',
        props: {
            namePage:{
                type: String,
            },
        },
};
</script>

<template lang="pug">
.namePage(v-if="namePage")
        h1.text {{namePage}}
        .liner
.BackgroundWhite
    .background
    .Slot
        slot
</template>

<style lang="scss">
.namePage{
    display: flex;
    flex-direction: column;

    .text{
        padding-top: 28px;
        color: #000;
        font-family: 'Montserrat', sans-serif;
        font-size: 36px;
        letter-spacing: 0.15em;
        text-transform: uppercase;
        font-weight: bold;
        margin: 0 auto;
    }

    .liner{
        height: 2px;
        background: #656565;
        width: 100px;
        margin: 0 auto;
        margin-top: 11px;
        margin-bottom: 50px;
    }
}
.BackgroundWhite{
    position: relative;
    width: 100%;
    height: 100%;
    display: flex;
    margin-top: auto;
    margin-bottom: 0em;
    overflow:hidden;
    border-radius: 25px 25px 0 0;
    box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.1);
    z-index:0;
    padding-bottom: 30px;

    .namePage{
        display: flex;
        flex-direction: column;
        position: relative;
        .name{
            color: #000;
            font-family: 'Montserrat Light', sans-serif;
            font-size: 36px;
            letter-spacing: 0.15em;
            text-transform: uppercase;
        }
    }
    .background{
        position: absolute;
        width: 100%;
        height: 100%;
        border-radius: 25px 25px 0 0;
        background-image: url(../../assets/images/src/background.png);
        opacity: 30%;
        background-repeat: no-repeat;
        background-position: center center;
        -webkit-background-size: cover;
        -moz-background-size: cover;
        -o-background-size: cover;
        background-size: cover;
        -webkit-filter: blur(10px);
        background-color: rgb(214, 214, 214);
        box-shadow: 4px 4px 50px rgba(0, 0, 0, 0.048);
    }
    .Slot{
        z-index: 2;
        //position: absolute;
        height: 100%;
    }
}

@media (max-width: 800px) {
    .BackgroundWhite{
        height: 100%;

        .background {
            
        }
    }

    .namePage{
        .text{
            font-size: 20px;
        }
    
        .liner{
            width: 80px;
            margin-bottom: 25px;
        }
    }
}
</style>