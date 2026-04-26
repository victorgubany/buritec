<template>
    <div v-if="!service">
    <ServiceNotFound/>
    </div>

    <div v-else>
        <ServiceFound :name="service.name" :description="service.description" :image="service.image"/>
    </div>
</template>

<script setup>
import ServiceNotFound from '@/components/ServiceNotFound.vue';
import ServiceFound from '@/components/ServiceFound.vue';
import { services } from '@/mocks/list';
import { useRoute } from 'vue-router';



const route = useRoute()
let slug = route.params.slug

let service = services.find(item => item.slug == slug)

</script>

<style scoped>
</style>