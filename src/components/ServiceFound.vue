<template>
  <section id="services" class="services bg-gray-50 py-16">
    <div class="max-w-6xl mx-auto px-6 flex flex-col md:flex-row items-center gap-12">
      
      <div class="w-full md:w-1/2 flex justify-center">
        <div class="relative group">
          <div class="absolute -inset-2 bg-blue-600 rounded-2xl blur opacity-20 group-hover:opacity-40 transition duration-1000"></div>
          
          <img 
            :src="props.image" 
            :alt="props.name"
            class="relative rounded-2xl shadow-2xl object-cover w-full h-[400px] transform transition duration-500 hover:scale-[1.02]"
          />
        </div>
      </div>

      <div class="w-full md:w-1/2 text-left">
        <h1 class="text-4xl sm:text-5xl font-extrabold text-gray-900 mb-6 leading-tight">
          {{ props.name }}
        </h1>
        
        <div class="w-full h-0.5 bg-gray-600 mb-8 rounded-full"></div>

        <p class="text-lg text-gray-700 leading-relaxed">
          {{ props.description }}
        </p>

          
        <a target="_blank" href="whatsapp://send?phone=5515997744747&text=Gostaria%20de%20informações%20sobre%20os%20serviços">
            <button class="mt-8 cursor-pointer px-8 py-3 bg-gray-600/30 text-black border border-transparent rounded-lg transition-all duration-300 hover:bg-gray-600 hover:border-white">
            Solicite um orçamento
            </button>
        </a>

      </div>

    </div>
  </section>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    name: String,
    image: String,
    description: String
})

</script>

<style scoped>
</style>