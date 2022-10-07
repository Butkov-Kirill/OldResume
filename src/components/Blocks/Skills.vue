<script>
import RoundChart from '../Elements/RoundChart.vue';

export default {
    components: {
    RoundChart,
}
}
</script>

<template lang="pug">
.skills
    .cards
        .card
            h1.name Опыт в GameDev
            .liner
            p Unity, Unreal Engine 4, Game Maker Studio 2.
            RoundChart(Procentages="25%", style="--p:25; --b:3px; --c:#6950c6;")
        .card
            h1.name Опыт в WebDev
            .liner
            p HTML, CSS, JavaScript, Pug, Vue, SCSS, WebPack.
            RoundChart(Procentages="60%", style="--p:60; --b:3px; --c:#6bc650;")
        .card
            h1.name Опыт в дизайне
            .liner
            p Figma, Photoshop.
            RoundChart(Procentages="15%", style="--p:15; --b:3px; --c:#c65050;")
    .info
        .info-block
            h1 Опыт работы:
            .text
                span • Call Center
                | - В 2021 году работал в колл-центре Infotell в качестве оператора горячей линии и менеджера
                | по работе с клиентами.
        .info-block
            h1 Дополнительная информация:
            .text
                span • Еще ЯП'ы
                | - Имел опыт с такими языками программирования как: C#, C++, PHP, Python, Assembler, Pascal, Java.
</template>

<style lang="scss">
.skills{
    width: 100%;
    display: flex;
    flex-direction: column;
    .cards{
        display: flex;
        width: 100%;
        margin-top: 30px;

        .card{
            background: rgb(0,0,0,0.05);
            border-radius: 30px;
            padding: 25px 40px 25px 40px;
            display: flex;
            flex-direction: column;
            margin: 0 auto;
            width: 20%;
            box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.089);

            .name{
                font-family: 'Montserrat Light', sans-serif;
                font-size: 20px;
                font-weight: medium;
                display: flex;
                margin: 0 auto;
            }

            .liner{
                height:1px;
                width: 100%;
                background: #000;
                margin-top: 10px;
            }

            p{
                font-family: 'Montserrat Light', sans-serif;
                font-size: 18px;
                font-weight: lighter;
                text-align: center;
            }
        }
    }

    .info {
        padding-left: 40px;
        padding-top: 40px;
        width: 100%;
        line-height: 30px;
        display: flex;

        .info-block{
            width: 45%;
            margin: 0 auto;
        }

        h1{
            font-family: 'Montserrat', sans-serif;
            font-size: 18px;
            font-weight: 800;
        }
        span{
            font-family: 'Montserrat', sans-serif;
            font-weight: 600;
            padding-right: 5px;
        }
        .text {
            font-family: 'Montserrat Light', sans-serif;
            font-size: 18px;
            font-weight: lighter;
        }
    }
}

@media (max-width: 800px) {
    .skills{
        .cards{
            width: 100%;
            flex-direction: column;
    
            .card{
                width: 60%;
                margin-bottom: 20px;
            }
        }
    
        .info {
            padding-top: 10px;
            width: 90%;
            flex-direction: column;
            padding-left: 15px;
            .info-block{
                width: 80%;

                &:first-child{
                    margin-bottom: 15px;
                }
            }
        }
    }
}
</style>