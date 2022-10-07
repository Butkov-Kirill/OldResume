<script>
import ProgressBar from '../Elements/ProgressBar.vue'

export default {
    components: {
        ProgressBar,
    },
    data(){
        return{
            play : false,
            isControll : true,
            video_player : null,
            Time : {
                minutes : 0,
                seconds : 0
            }
        }
    },
    methods: {
        MouseAction: function(isPlay){
            this.isControll = isPlay;
            if (!this.play){
                this.isControll = true;
            }
        },
        PlayAction: function() {
            this.play = !this.play;
            if (this.play){
                this.video_player.play();
            } else {
                this.video_player.pause();
            }
            console.log(this.Time.minutes + " : "+this.Time.seconds);

        },
        ShowTime(){
            console.log("play");
        },
        Rewind(){
            
        }
    },
    mounted(){
        this.$nextTick(function(){
            let video_player = this.$refs.video_player;
            this.video_player = video_player;
            var duration = video_player.duration.toFixed(1);
            var m = duration % 60;
            this.Time.minutes = Math.floor(duration /60);
            this.Time.seconds = Math.floor((m < 10 ? '0' : '')+ m);
            console.log(this.Time.minutes + " : "+this.Time.seconds);
        })
    }
}
</script>

<template lang="pug">
.video-player(@mouseenter="MouseAction(true)", @mouseleave="MouseAction(false)")
    video.video-media(src="../../assets/Video/CYBERPUNK.mp4", ref="video_player", controls)
    //.video-controll(v-show="isControll")
        .play(v-if="play==false", @mousedown="PlayAction")
        .pause(v-if="play", @mousedown="PlayAction")
        ProgressBar.progress()
</template>

<style lang="scss">
    .video-player{
        position: relative;
        display: flex;
        flex-direction: column;
        .video-media{
            width: 100%;
            box-shadow: 4px 4px 15px rgba(0, 0, 0, 0.25);
        }
        .video-controll{
            position: absolute;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.329);
            .play{
                position: absolute;
                padding: 10% 10% 10% 10%;
                border-radius: 50%;
                background: rgba(196, 196, 196, 0.28);
                margin: 0 auto;
                left: 50%;
                top: 50%;
                transform: translate(-50%, -50%);

                &::before{
                    position: absolute;
                    left: 50%;
                    top: 50%;
                    transform: translate(-20%, -50%);
                    display: flex;
                    background: rgba(255, 255, 255, 0);
                    content: ' ';
                    margin: 0 auto;
                    border: 20px solid transparent;
                    border-left: 30px solid rgb(255, 255, 255);
                }
            }
            .pause{
                position: absolute;
                padding: 10% 10% 10% 10%;
                border-radius: 50%;
                background: rgba(196, 196, 196, 0.28);
                margin: 0 auto;
                left: 50%;
                top: 50%;
                transform: translate(-50%, -50%);

                &::before{
                    content: ' ';
                    background: #fff;
                    width: 8px;
                    height: 40px;
                    position: absolute;
                    left: 35%;
                    top: 50%;
                    transform: translate(0, -50%);
                }

                &::after{
                    content: ' ';
                    background: #fff;
                    width: 8px;
                    height: 40px;
                    position: absolute;
                    right: 35%;
                    top: 50%;
                    transform: translate(0, -50%);
                }
            }
            .progress{
                position: absolute;
                left: 50%;
                top: auto;
                bottom: 5%;
                transform: translate(-50%, -50%);
            }
        }
    }
</style>