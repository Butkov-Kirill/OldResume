<template lang="pug">
.Main
    .Left
        img(src="../../assets/images/src/man.png")
    .Right
        .Human
            img.avatar(src="../../assets/images/src/ava.png")
            h1.MyName Бутков Кирилл
        p 
            | Кирилл, 16 лет. С 2016 года занимаюсь изучением сферы IT,
            | с 2020 года занимаюсь музыкой, созданием 2Д графики для игр и дизайном.
        button(v-on:click = "CheckMore('about')") УЗНАТЬ БОЛЬШЕ
</template>

<script>
export default {
    methods: {
        CheckMore(component){
            this.$emit('scroll', component);
        }
    }
}
</script>

<style lang="scss">
.Main{
    display: flex;
    min-height: 200px;
    height: 100%;
        .Left{
            display: flex;
            margin-top: auto;
            height: 100%;
            width: 50%;
            img{
                width: 60%;
                display: flex;
                margin: 0 auto;
                margin-top: auto;
                margin-bottom: -2em;
                image-rendering: crisp-edges;
                filter: drop-shadow(5px 5px 10px rgba(0, 0, 0, 0.377));
            }
        }

        .Right{
            padding-right: 5%;
            width: 50%;
            margin: auto auto;
            .avatar{
                display: none;
            }
            .MyName {
                font-family: 'Montserrat', sans-serif;
                font-weight: bold;
                font-size: 64px;
                padding-bottom: 50px;
            }

            p{
                font-family: 'Montserrat Light', sans-serif;
                font-weight: 100;
                font-size: 24px;
                line-height: 40px;
            }

            button {
                margin-top: 50px;
                background: rgba(62, 62, 62, 1);
                border: none;
                padding: 20px 85px 20px 85px;
                color: white;
                font-family: 'Montserrat Light', sans-serif;
                font-size: 18px;
                font-weight: lighter;
                border-radius: 50px;
                box-shadow: 4px 4px 25px rgba(0, 0, 0, 0.25);

                &:hover{
                    background: rgb(41, 41, 41);
                    box-shadow: 4px 4px 25px rgba(0, 0, 0, 0.356);
                    transition: 0.5s;
                }
            }
        }
}

@media (max-width: 800px) {
.Main{
        .Left{
            display: none;
        }

        .Right{
            width: 100%;
            padding-right: 20px;
            padding-left: 20px;
            margin: 0;
            .Human{
                display: flex;
                padding-top: 20px;
            }

            .avatar{
                display: block;
                width: 100px;
                height: 100px;
                border-radius: 100%;
                box-shadow: 0 0 20px rgb(0,0,0,0.1);
            }

            .MyName {
                font-size: 30px;
                padding-bottom: 0px;
                margin: auto 0;
                padding-left: 20px;
            }

            p{
                font-size: 18px;
                line-height: 30px;
                text-align: justify;
            }

            button {
                margin-top: 15px;
                padding: 20px 60px 20px 60px;
                font-size: 14px;
                display: flex;
                margin: 0 auto;
            }
        }
    }
}
</style>