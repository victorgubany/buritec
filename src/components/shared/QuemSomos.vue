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
</template>

<style scoped>
    .quem-somos {
    background-image: linear-gradient(to bottom right, #f9fafb, #eef2f7);
    }
</style>

<script setup>
    import { defineProps } from 'vue';
    const props = defineProps({
        name: String
    })


</script>
