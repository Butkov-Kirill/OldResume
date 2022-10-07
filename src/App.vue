<script setup>
import './index.scss';
import './assets/Fonts/awesome/css/all.css';

import Header from './components/Main/Header.vue'
import WhiteBackground from './components/Main/WhiteBackground.vue'
import Main from './components/Blocks/Main.vue'
import About from './components/Blocks/About.vue'
import Skills from './components/Blocks/Skills.vue'
import Portfolio from './components/Blocks/Portfolio.vue'
import Contacts from './components/Blocks/Contacts.vue'
import Copyright from './components/Blocks/Copyright.vue'

function scroll(component){
    var element = document.getElementsByClassName(component);
    element[0].scrollIntoView();
}

</script>

<template lang="pug">
.border.main
    Header(@scroll="scroll")
    .block  
        WhiteBackground
            Main(@scroll = "scroll")
About.about
.border.scills
    .block
        WhiteBackground(namePage="навыки")
            Skills
Portfolio.portfolio
.border.contacts
    .block
        WhiteBackground(namePage="контакты")
            Contacts
Copyright
</template>

<style lang="scss">
    .border {
        padding: 25px 100px 0 100px;
        box-shadow: 0px 10px 50px rgba(0, 0, 0, 0.3);
    }
    
    .block{
        display: flex;
        flex-direction: column;
    }

    @media (max-width: 800px) {
        .border {
            padding: 0;
        }
    }
</style>
