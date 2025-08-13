<template>
       <section class="quem-somos bg-gray-50 py-10">
    <div class="max-w-4xl mx-auto px-4 text-center">
      <h1 class="text-3xl sm:text-4xl font-bold text-gray-800 mb-6">
        Quem Somos
      </h1>

      <p class="text-lg text-gray-700 leading-relaxed">
        A <span class="font-semibold text-blue-600">{{ name }}</span> foi fundada com o objetivo de oferecer
        <span class="font-semibold">qualidade</span>,
        <span class="font-semibold">agilidade</span> e
        <span class="font-semibold">comprometimento</span> nos segmentos de
        balanceamento dinâmico, usinagem, fabricação de máquinas, peças, ferramentas,
        manutenção industrial e agroindustrial.
      </p>

      <p class="text-lg text-gray-700 leading-relaxed mt-6">
        Desde <span class="font-semibold">2006</span>, somos especializados em balanceamento e usinagem de peças técnicas de alta precisão.
        Desenvolvemos projetos de máquinas, ferramentas, dispositivos, protótipos e acessórios, oferecendo
        <span class="font-semibold">serviço profissional de excelência</span> para que nossos clientes
        alcancem maior produtividade e eficiência em suas linhas produtivas.
      </p>
    </div>
  </section>
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
    /* margin-bottom: 4vh ; */
}
.title{
    /* font-family:  ; */
    font-weight: bold;
    font-size: 2rem;
}
.quem-somos {
  background-image: linear-gradient(to bottom right, #f9fafb, #eef2f7);
}
</style>
