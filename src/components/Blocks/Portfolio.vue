<script>

import file_cyberpank from '../../assets/Video/CYBERPUNK.mp4';
import file_timetrapstory from '../../assets/Video/Time-TrapStory.mp4';
import file_steampunk from '../../assets/Video/STEAMPUNK.mp4';
import file_industrysimulation from '../../assets/Video/IndustrySimulation.mp4';

import VideoPlayer from '../Elements/VideoPlayer.vue'
export default {
    components:{
        VideoPlayer
    },
    data(){
        return{
            Video : null,
            Name : "CYBERPUNK",
            Description : "Игра которую я делал в свободное время в 2021 году на Unity. Все механики игры писались на языке C#. Основная идея игры - решение головоломок и скрытное прохождение уровней.",
            CYBERPUNK : {
                video : file_cyberpank,
                description : "Игра которую я делал в свободное время в 2021 году на Unity. Все механики игры писались на языке C#. Основная идея игры - решение головоломок и скрытное прохождение уровней.",
                name_product : "CYBERPUNK",
            },
            TimeTrapStory : {
                video : file_timetrapstory,
                description : "Эта игра разрабатывалась в 2020 году на Unity, в свободное время и была заброшена по некоторым причинам. Игровые механики были написаны на C#. Основной идеей было создать игру с большим миром, обитателями которого являются члены разных фракций, сформированных после схлопывания всех вселенных и временных периодов в один. Данная игра своего рода RPG Survivor. Где игрок мог бы выбрать любую фракцию и продвигать ее к победе.",
                name_product : "Time-Trap Stroy",
            },
            STEAMPUNK : {
                video : file_steampunk,
                description : "Эту игру я разрабатывал в 2021 году на Unity, для школьного проекта. Все механики были написаны на C#. Основной идеей было создать игру в которой можно выполнять квесты, ходить по локациям и изучать их. Игра не была доведена до конца, так как школьный проект закончился раньше и пришлось сдать игру не доделанной. За несколько дней до сдачи проекта была улучшена внешне, были добавлены объекты которые реагируют на игрока, чтобы игры казалась динамичней. В дальнейшем я решил не доделывать ее.",
                name_product : "STEAMPUNK 1888",
            },
            IndustrySimulation : {
                video : file_industrysimulation,
                description : "Эту игру я разрабатывал в 2020 году, на игровом движке GameMaker Studio 2, дабы занять себя в свободное время. Игра представляет из себя простой симулятор развития своего поселения. В ней вы можете: строить дома, заселять их людьми, строить промышленные здания и т.д.",
                name_product : "Industry Simulation",
            }         
        }
    },
    mounted(){
        this.$nextTick(function(){
            var Video = this.$refs.video_player;
            this.Video = Video;
        });
    },
    methods:{
        ProductButton(product){
            this.Name = product.name_product;
            this.Description = product.description;
            this.Video.src = product.video;
        }
    }
}
</script>

<template lang="pug">
.portfolio
    video.video-background(src="../../assets/Video/background.mp4", loop="loop", autoplay="", muted="")
    .name-page
        h1.name ПОРТФОЛИО
        .liner 
    .sides
        .left
            .portfolio-block
                .name-portfolio-block GameDev
                .liner
                button.button(v-on:click = "ProductButton(this.CYBERPUNK)") CYBERPUNK
                button.button(v-on:click = "ProductButton(this.TimeTrapStory)") Time-Trap Stroy
                button.button(v-on:click = "ProductButton(this.STEAMPUNK)") STEAMPUNK 1888
                button.button(v-on:click = "ProductButton(this.IndustrySimulation)") Industry simulation
            .portfolio-block
                .name-portfolio-block WebDev
                .liner
                button.button SOON
                button.button SOON
                button.button SOON
                button.button SOON
        .right
            .info-block
                .name-product {{Name}}
                //VideoPlayer.player
                video.video-media(src="../../assets/Video/CYBERPUNK.mp4", ref="video_player", controls)
                .info-product
                    span Описание:
                    |{{Description}}
</template>

<style lang="scss">
.portfolio{
    position: relative;
    display: flex;
    flex-direction: column;
    overflow:hidden;
    box-shadow: 0 0 30px 10px rgba(0, 0, 0, 0.295);

    &::before{
        content: ' ';
        z-index: -1;
        background-color: rgba(43, 47, 48, 0.95);
        width: 100%;
        height: 100%;
        position: absolute;
    }

    .video-background{
        z-index:-2;
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        width: 100%;
        -webkit-filter: blur(5px);
        overflow:hidden;
    }
    
    .name-page{
        display: flex;
        flex-direction: column;
        margin: 0 auto;
        margin-top:50px;

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
        padding: 0 100px 50px 100px;
        .left{
            width: 50%;
            display: flex;
            .portfolio-block{
                display: flex;
                flex-direction: column;
                width: 45%;
                &:first-child{
                    margin-left: 0;
                }
                &:last-child{
                    margin: 0 auto;
                }
                .name-portfolio-block{
                    color: #fff;
                    font-family: 'Montserrat', sans-serif;
                    font-style: normal;
                    font-weight: 500;
                    font-size: 24px;
                    line-height: 28px;
                    letter-spacing: 0.15em;
                    margin-bottom: 15px;
                }

                .liner{
                    height: 1px;
                    background: #F0BF10;
                    width: 100%;
                    margin-bottom: 25px;
                }

                button{
                    padding: 16px 0 16px 0;
                    background: rgba(0, 0, 0, 0.5);
                    border:none;
                    border-radius: 25px;
                    margin-bottom: 25px;
                    color: #fff;
                    font-family: 'Montserrat Light', sans-serif;
                    font-style: normal;
                    font-weight: lighter;
                    font-size: 14px;
                    letter-spacing: 0.15em;
                }

                button:hover{
                    background: rgba(0, 0, 0, 0.699);
                    box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.349);
                    transition: 0.2s;
                }
            }
            
        }
        .right{
            width: 50%;

            .video-media{
                width: 100%;
                margin-bottom: 15px;
            }

            .info-block{
                background: rgba(14, 14, 14, 0.5);
                box-shadow: 4px 4px 20px rgba(0, 0, 0, 0.15);
                border-radius: 44px;
                padding: 30px 40px 30px 40px;
                
                .name-product{
                    color: #fff;
                    font-family: 'Montserrat Light', sans-serif;
                    font-weight: lighter;
                    font-size: 24px;
                    line-height: 28px;
                    letter-spacing: 0.15em;
                    margin-bottom: 25px;
                }
                .player{
                    margin-bottom: 15px;
                }
                .info-product{
                    font-family: 'Montserrat Light', sans-serif;
                    color: #fff;
                    font-weight: lighter;
                    font-size: 14px;
                    line-height: 21px;
                    letter-spacing: 0.05em;
                    span {
                        font-weight: bold;
                        padding-right: 5px;
                    }
                }
            }
        }
    }
}

@media (max-width: 800px) {
.portfolio{
    .video-background{
        width: auto;
        height: 100%;
    }
    
    .name-page{
        margin-top: 30px;

        .name{
            font-size: 20px;
        }
        .liner{
            margin-bottom: 40px;
        }
    }

    .sides{
        flex-direction: column;
        padding: 0 10px 25px 10px;
        .left{
            width: 100%;
            .portfolio-block{
                width: 45%;
                &:first-child{
                    margin: 0 auto;
                }
                &:last-child{
                    margin: 0 auto;
                }
                .name-portfolio-block{
                    font-size: 20px;
                    line-height: 20px;
                }
            }
            
        }
        .right{
            width: 100%;
            .info-block{
                border-radius: 30px;
                padding: 20px 20px 20px 20px;
                .name-product{
                    line-height: 20px;
                    margin-bottom: 20px;
                }
            }
        }
    }
}
}
</style>