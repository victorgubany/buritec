<template>
    <div v-if="!service">
    <RecoveryNotFound/>
    </div>

    <div v-else>
        <RecoveryFound :name="service.name" :description="service.description" :image="service.image"/>
    </div>
</template>

<script setup>
import { recovery } from '@/mocks/list';
import { useRoute } from 'vue-router';
import RecoveryFound from '@/components/RecoveryFound.vue';
import RecoveryNotFound from '@/components/RecoveryNotFound.vue';



const route = useRoute()
let slug = route.params.slug

let service = recovery.find(item => item.slug == slug)

</script>

<style scoped>
</style>