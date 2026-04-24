<template>
  <div
    class="container min-w-full flex justify-center items-center gap-4"
    :style="{ backgroundImage: `url(${perfil})` }"
  >
    <button class="cursor-pointer px-6 py-2 bg-gray-600/50 text-white border border-transparent rounded-lg transition-all duration-300 hover:bg-gray-600 hover:border-white">
      Solicite um orçamento
    </button>
    <button class="cursor-pointer px-6 py-2 bg-gray-600/50 text-white border border-transparent rounded-lg transition-all duration-300 hover:bg-gray-600 hover:border-white">
      Solicite um orçamento por e-mail
    </button>
  </div>
</template>

<script setup>
import perfil from '@/assets/imgs/perfil.png'
</script>

<style scoped>
.container {
  width: 100%;
  height: 50vh; 
  background-size: cover; 
  background-position: center;
  background-repeat: no-repeat;
}
</style>
