<template>
  <div
    class="container flex justify-center items-center gap-4"
    :style="{ backgroundImage: `url(${perfil})` }"
  >
    <button class="px-6 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700">
      Solicite um orçamento
    </button>
    <button class="px-6 py-2 bg-green-600 text-white rounded-lg hover:bg-green-700">
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
  height: 50vh; /* tela inteira na vertical */
  background-size: cover; /* preenche horizontalmente, pode cortar vertical */
  background-position: center;
  background-repeat: no-repeat;
}
</style>
