<template lang="pug">
.header
    .icon
        img(src='../../assets/images/src/icon_svg.svg')
    .name-page Бутков К.А.
    .buttons
        button(v-on:click = "Scroll('main')") Главная
        button(v-on:click = "Scroll('about')") О себе
        button(v-on:click = "Scroll('scills')") Навыки
        button(v-on:click = "Scroll('portfolio')") Портфолио
        button(v-on:click = "Scroll('contacts')") Контакты
</template>

<script>
export default {
    methods: {
        Scroll(component){
            this.$emit('scroll', component);
        },
        log(){
            console.log('test');
        }
    }
}
</script>

<style lang="scss">
    .header {
        display: flex;
        flex-direction: row;
        width: 100%;
        z-index: 10;
        margin-bottom: 5%;
        
        .icon{
            img {
                width:30px;
                height:30px;
                image-rendering: optimizeQuality;
            }
        }
        .name-page{
            font-family: 'Montserrat Light', sans-serif;
            font-weight: bold;
            font-size: 18px;
            margin: auto 0;
        }
        
        .buttons{
            margin: auto 0;
            margin-left: auto;
            margin-right: 0em;
            button{
                background: none;
                border: none;
                font-family: 'Montserrat Light', sans-serif;
                font-size: 18px;
                font-weight: bold;
                margin-left: 44px;
                border-bottom: 2px solid transparent;
            }
            button:hover{
                border-color: #000;
                transition: 0.5s;
            }
        }
    }

    @media (max-width: 800px) {
        .header {
            padding: 10px 10px 10px 10px;
            width: auto;
            .buttons{
                display: none;
                /*margin: auto 0;
                margin-left: auto;
                margin-right: 0em;
                button{
                    background: none;
                    border: none;
                    font-family: 'Roboto', sans-serif;
                    font-size: 18px;
                    font-weight: bold;
                    margin-left: 44px;
                    border-bottom: 2px solid transparent;
                }
                button:hover{
                    border-color: #000;
                    transition: 0.5s;
                }*/
            }
        }
    }
</style>