<script setup>
import { RouterLink, RouterView } from 'vue-router'
import TheHeader from './components/shared/TheHeader.vue';
import TheFooter from './components/shared/TheFooter.vue';


const name = "Buritec"
const instagram = "https://www.instagram.com/buritec_tornearia/"
const linkedIn = "https://www.linkedin.com/in/buritec-balanceamento-e-tornearia-7812222b1/"
const facebook = "https://www.facebook.com/buritec2006?locale=pt_BR"
</script>

<template>
    <TheHeader/>
    <RouterView />
    <TheFooter :facebook="facebook" :linkedIn="linkedIn" :instagram=instagram :name=name />
</template>


