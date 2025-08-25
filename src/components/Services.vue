<template>
  <div class="container max-w-5xl mx-auto space-y-4">
    <!-- Accordion Item -->
    <div
      v-for="section in sections"
      :key="section.key"
      class="bg-white dark:bg-gray-900 rounded-xl shadow-md overflow-hidden border border-gray-200 dark:border-gray-700"
    >
      <button
        @click="toggleSection(section.key)"
        class="flex items-center justify-between w-full p-5 font-medium text-left text-gray-700 dark:text-gray-300 hover:bg-gray-50 dark:hover:bg-gray-800 transition-colors duration-300"
        :aria-expanded="openSection === section.key"
        :aria-controls="`${section.key}-panel`"
      >
        <span class="text-lg font-semibold">{{ section.title }}</span>
        <svg
          :class="['w-5 h-5 transition-transform duration-300', openSection === section.key ? 'rotate-180' : '']"
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 10 6"
        >
          <path
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M9 5 5 1 1 5"
          />
        </svg>
      </button>

      <Transition name="accordion">
        <div
          v-show="openSection === section.key"
          :id="`${section.key}-panel`"
          role="region"
          :aria-labelledby="section.key"
          class="p-5 border-t border-gray-200 dark:border-gray-700"
        >
          <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
            <ul
              v-for="(chunk, index) in section.chunks"
              :key="`${section.key}-${index}`"
              class="list-disc ps-5 text-gray-600 dark:text-gray-400 space-y-1"
            >
              <li v-for="(item, i) in chunk" :key="i">
                <a
                  :href="'/' + item"
                  class="hover:text-indigo-500 dark:hover:text-indigo-400 transition-colors duration-200"
                >
                  {{ item }}
                </a>
              </li>
            </ul>
          </div>
        </div>
      </Transition>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const services = [
  "Manutenção em Campo", "Balanceamento Dinâmico Industrial", "Manutenção em Geral", "Usinagem",
  "Fresadora", "Torno", "Plaina", "Soldas Especiais", "Adaptações", "Mandrilhamento",
  "Embuchamento", "Prensa", "Pintura"
];

const recovery = [
  "Ferramentas", "Pistões", "Eixos", "Rotores", "Engrenagens", "Rodas dentadas", "Mancais",
  "Rodas", "Cubos", "Polias", "Cremalheiras", "Flanges", "Rolos", "Pinos", "Buchas", "Porcas",
  "Prisioneiros", "Roscas", "Furos", "Chavetas", "Olhais", "Ganchos", "Prolongadores", "Separadores"
];

function chunkArray(arr, size = 5) {
  const result = [];
  for (let i = 0; i < arr.length; i += size) {
    result.push(arr.slice(i, i + size));
  }
  return result;
}

const serviceChunks = computed(() => chunkArray(services, 5));
const recoveryChunks = computed(() => chunkArray(recovery, 5));

const sections = computed(() => [
  { key: 'services', title: 'Serviços', chunks: serviceChunks.value },
  { key: 'recovery', title: 'Reconstrução', chunks: recoveryChunks.value }
]);

// Inicializamos já com 'recovery' aberta
const openSection = ref('recovery');

function toggleSection(section) {
  openSection.value = openSection.value === section ? null : section;
}
</script>
<style scoped>
.container {
  margin-top: 4vh;
}

.accordion-enter-active,
.accordion-leave-active {
  transition: max-height 0.3s ease, opacity 0.3s ease, padding 0.3s ease;
}
.accordion-enter-from,
.accordion-leave-to {
  max-height: 0;
  opacity: 0;
  padding-top: 0;
  padding-bottom: 0;
}
.accordion-enter-to,
.accordion-leave-from {
  max-height: 500px;
  opacity: 1;
  padding-top: 1.25rem;
  padding-bottom: 1.25rem;
}
</style>
