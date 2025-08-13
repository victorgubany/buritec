<template>
    <solicite/>
    <contact-us/>


    <footer class="bg-gray-900 text-white py-8">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">

      <div>
        <h4 class="text-lg font-semibold mb-4">Empresa</h4>
        <ul class="space-y-2">
          <li><a href="#" class="hover:underline">Sobre nós</a></li>
          <li><a href="#" class="hover:underline">Carreiras</a></li>
          <li><a href="#" class="hover:underline">Blog</a></li>
        </ul>
      </div>

      <div>
        <h4 class="text-lg font-semibold mb-4">Suporte</h4>
        <ul class="space-y-2">
          <li><a href="#" class="hover:underline">Ajuda</a></li>
          <li><a href="#" class="hover:underline">Contato</a></li>
          <li><a href="#" class="hover:underline">Política de Privacidade</a></li>
        </ul>
      </div>

      <div>
        <h4 class="text-lg font-semibold mb-4">Serviços</h4>
        <ul class="space-y-2">
          <li><a href="#" class="hover:underline">Consultoria</a></li>
          <li><a href="#" class="hover:underline">Design</a></li>
          <li><a href="#" class="hover:underline">Desenvolvimento</a></li>
        </ul>
      </div>

      <div>
        <h4 class="text-lg font-semibold mb-4">Redes Sociais</h4>
        <div class="flex space-x-4">
          <a target="_blank" :href="linkedIn" class="hover:text-gray-400">🌐</a>
          <!-- <a href="#" class="hover:text-gray-400">🐦</a> -->
          <a target="_blank" :href="facebook" class="hover:text-gray-400">📘</a>
          <a target="_blank" :href="instagram" class="hover:text-gray-400">📸</a>
        </div>
      </div>
    </div>

    <div class="mt-8 border-t border-gray-700 pt-6 text-center text-sm text-gray-400">
      © {{ new Date().getFullYear() }} {{ props.name }}
    </div>
  </div>
</footer>

</template>

<script setup>
    import { defineProps } from 'vue';
    const props = defineProps({
        "name" : String,
        "instagram" : String,
        "linkedIn" :String,
        "facebook" :String
    })

    import ContactUs from '@/components/ContactUs.vue'
    import Solicite from '../Solicite.vue';
</script>
