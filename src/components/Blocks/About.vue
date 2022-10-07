<template lang="pug">
.About
    .nameBlock
        h1.name о себе
        .liner
    .sides
        .left
            .note
                p
                    |Меня зовут Кирилл, мне 16 лет. Впервые открыл для себя программирование в 2016 году,
                    | желая стать разработчиком игр. Эта идея изменила все последующие 6 лет. Я успел 
                    |попробовать себя во многих сферах IT: Разработка игр, ПО, мобильных приложений,
                    | создание сайтов, информационная безопасность.
                p
                    | На данный момент, основным родом 
                    |деятельности для меня является программирование, а именно разработка сайтов и разработка
                    | игр на Unity. В свободное время занимаюсь музыкой и дизайном.
        .right
            .characteristics
                h1.name положительные качества
                .liner
                ul
                    li • адаптивный / гибкий
                    li • целеустремленный
                    li • коммуникабельный
                    li • восприимчив к критике
                    li • креативный
                    li • многогранный
                    li • энтузиаст
</template>

<script>

</script>

<style lang="scss">
.About {
    z-index:10;
    position: static;
    display: flex;
    flex-direction: column;
    background: rgba(43, 47, 48, 1);
    padding-top: 30px;
    box-shadow: inset 0 0 30px 10px rgba(0, 0, 0, 0.295);

    .nameBlock{
        display: flex;
        flex-direction: column;
        margin: 0 auto;
        .name{
            color: rgb(255, 255, 255);
            font-family: 'Montserrat', sans-serif;
            font-weight: bold;
            font-size: 36px;
            letter-spacing: 0.15em;
            text-transform: uppercase;
        }

        .liner{
            height: 2px;
            background: #F0BF10;
            width: 80px;
            margin: 0 auto;
            margin-top: 10px;
            margin-bottom: 50px;
        }
    }

    .sides{
        display: flex;

        .left{
            width: 70%;
            display: flex;
            .note{
                background-image: url(../../assets/images/src/note.png);
                background-repeat: no-repeat;
                width: 80%;
                height: auto;
                display: flex;
                flex-direction: column;
                margin: 0 auto;
                filter: drop-shadow(5px 0px 15px rgba(0, 0, 0, 0.555));
                overflow-y: auto;
                background-size: 100%;
                
                p {
                    font-family: 'JakobCTT', sans-serif;
                    color: rgba(3, 4, 30, 0.829);
                    font-style: normal;
                    font-weight: bold;
                    font-size: 15px;
                    line-height: 29px;
                    letter-spacing: 0.2em;
                    padding: 0px 20% 0px 20%;
                    text-indent: 50px;
                    margin-bottom: 0;
                }

                p:first-child{
                    padding-top: 20px;
                }

                p:last-child{
                   margin-bottom: 20px;
                }

            }
        }

        .right{
            .characteristics{
                display: flex;
                flex-direction: column;

                .name{
                    font-family: 'Montserrat', sans-serif;
                    font-style: normal;
                    font-weight: bold;
                    font-size: 36px;
                    line-height: 42px;
                    letter-spacing: 0.2em;
                    color: #fff;
                    text-transform: uppercase;
                }

                .liner {
                    width: 80%;
                    background: #fff;
                    height: 1px;
                    margin-top: 20px;
                    margin-bottom: 50px;
                }

                li{
                    font-family: 'Montserrat Light', sans-serif;
                    font-style: normal;
                    font-weight: lighter;
                    font-size: 24px;
                    line-height: 28px;
                    letter-spacing: 0.2em;
                    color: #fff;
                }
            }
        }
    }
}

@media (max-width: 800px) {
.About {
    padding-left: 20px;
    padding-right: 20px;

    .nameBlock{
        .name{
            font-size: 20px;
        }

        .liner{
            margin-bottom: 40px;
        }
    }

    .sides{
        flex-direction: column-reverse;

        .left{
            width: 100%;
            padding-top: 50px;
            
            .note{
                width: 100%;
                height: 400px;
                background-size: 100%;
                z-index:100;
                overflow-y: scroll;

                p {
                    font-size: 14px;
                    padding: 0px 25% 0px 20%;
                    text-indent: 25px;
                }

                p:first-child{
                    padding-top: 0px;
                }

            }
        }

        .right{
            .characteristics{
                display: flex;
                flex-direction: column;

                .name{
                    font-size: 25px;
                    line-height: 30px;
                }

                .liner {
                    margin-bottom: 20px;
                }

                li{
                    font-size: 18px;
                    line-height: 30px;
                }
            }
        }
    }
}
}
</style>