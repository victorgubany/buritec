<template>





  <!-- Accordion existente -->
  <div class="container">
    <div id="accordion-collapse" data-accordion="collapse">
      <!-- Serviços -->
      <h2 id="accordion-collapse-heading-2">
        <button
          type="button"
          class="flex items-center justify-between w-full p-5 font-medium rtl:text-right text-gray-500 border border-b-0 border-gray-200 focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-800 dark:border-gray-700 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-800 gap-3"
          data-accordion-target="#accordion-collapse-body-2"
          aria-expanded="true"
          aria-controls="accordion-collapse-body-2"
        >
          <span>Serviços</span>
          <svg data-accordion-icon class="w-3 h-3 rotate-180 shrink-0" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5 5 1 1 5" />
          </svg>
        </button>
      </h2>
      <div id="accordion-collapse-body-2" class="hidden" aria-labelledby="accordion-collapse-heading-2">
        <div class="p-5 border border-b-0 border-gray-200 dark:border-gray-700 dark:bg-gray-900">
          <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
            <ul v-for="(chunk, index) in serviceChunks" :key="'s'+index" class="list-disc ps-5 text-gray-500 dark:text-gray-400">
              <li v-for="(item, i) in chunk" :key="i"><a href="{{ item }}">{{ item }}</a></li>
            </ul>
          </div>
        </div>
      </div>

      <!-- Reconstrução -->
      <h2 id="accordion-collapse-heading-3">
        <button
          type="button"
          class="flex items-center justify-between w-full p-5 font-medium rtl:text-right text-gray-500 border border-gray-200 focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-800 dark:border-gray-700 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-800 gap-3"
          data-accordion-target="#accordion-collapse-body-3"
          aria-expanded="false"
          aria-controls="accordion-collapse-body-3"
        >
          <span>Reconstrução</span>
          <svg data-accordion-icon class="w-3 h-3 rotate-180 shrink-0" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5 5 1 1 5" />
          </svg>
        </button>
      </h2>
      <div id="accordion-collapse-body-3" class="hidden" aria-labelledby="accordion-collapse-heading-3">
        <div class="p-5 border border-t-0 border-gray-200 dark:border-gray-700 dark:bg-gray-900">
          <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
            <ul v-for="(chunk, index) in recoveryChunks" :key="'r'+index" class="list-disc ps-5 text-gray-500 dark:text-gray-400">
              <li v-for="(item, i) in chunk" :key="i"><a href="/{{ item }}">{{ item }}</a></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, computed } from 'vue'

const services = [
  "Manutenção em Campo", "Balanceamento Dinâmico Industrial", "Manutenção em Geral", "Usinagem",
  "Fresadora", "Torno", "Plaina", "Soldas Especiais", "Adaptações", "Mandrilhamento",
  "Embuchamento", "Prensa", "Pintura"
]

const recovery = [
  "Ferramentas", "Pistões", "Eixos", "Rotores", "Engrenagens", "Rodas dentadas", "Mancais",
  "Rodas", "Cubos", "Polias", "Cremalheiras", "Flanges", "Rolos", "Pinos", "Buchas", "Porcas",
  "Prisioneiros", "Roscas", "Furos", "Chavetas", "Olhais", "Ganchos", "Prolongadores", "Separadores"
]

// Função para dividir arrays em blocos de até 5 itens
function chunkArray(arr, size = 5) {
  const result = []
  for (let i = 0; i < arr.length; i += size) {
    result.push(arr.slice(i, i + size))
  }
  return result
}

const serviceChunks = computed(() => chunkArray(services, 5))
const recoveryChunks = computed(() => chunkArray(recovery, 5))

const props = defineProps({
  name: String
})
</script>

<style lang="css" scoped>
.container{
    margin-top: 4vh ;
}
</style>
