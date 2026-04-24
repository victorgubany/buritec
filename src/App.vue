<script setup>
import { RouterLink, RouterView } from 'vue-router'
import TheHeader from './components/shared/TheHeader.vue';
import TheFooter from './components/shared/TheFooter.vue';


const name = "DEKSA industrial"
const instagram = "https://www.instagram.com/deksa_industrial/"
const linkedIn = ""
const facebook = ""
</script>

<template>
    <TheHeader/>
    <RouterView />
    <TheFooter :facebook="facebook" :linkedIn="linkedIn" :instagram=instagram :name=name />
</template>


