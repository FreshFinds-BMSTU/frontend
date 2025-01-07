<script setup lang="ts">
import { CircleCheckBig, Clock8, Salad, DiamondPercent } from 'lucide-vue-next';
import PartnerCarousel from '@/components/PartnerCarousel.vue';
import Header1 from '@/components/Header1.vue'

</script>

<template>
  <header>
    <Header1></Header1>
  </header>
  <div class = "flex flex-col py-12 w-full items-center px-40 justified-text">
    <p class="text-white font-medium text-2xl ">Добро пожаловать в Fresh Finds! Мы стремимся сделать мир лучше, уменьшая количество пищевых отходов и помогая вам находить свежие продукты по доступным ценам. Присоединяйтесь к нашему сообществу и откройте для себя вкусные находки рядом с вами!</p>
  </div>
  <div class="flex flex-col items-center w-full py-10 gap-8">
      <h1 class="text-white text-4xl font-bold">Почему именно мы?</h1>
      <div class="flex w-3/4 h-fit gap-10">
        <div class="bg-neutral-700 w-full rounded-2xl items-center flex-col pt-10 px-5 pb-5 flex gap-4 h-fit">
          <Clock8 class="text-green-500 w-3/6 h-3/6"/>
          <div class="flex flex-col justify-center h-20" >
            <p class="text-white text-2xl text-center font-semibold tracking-wide">
              Привезём еду, когда другие не могут
            </p>
          </div>
        </div>
        <div class="bg-neutral-700 w-full rounded-2xl items-center flex-col pt-10 px-5 pb-5 flex gap-4 h-fit">
          <Salad class="text-green-500 w-3/6 h-3/6"/>
          <div class="flex flex-col justify-center h-20" >
            <p class="text-white text-2xl text-center font-semibold tracking-wide">
              Голодным не оcтанешься
            </p>
          </div>
        </div>
        <div class="bg-neutral-700 w-full rounded-2xl items-center flex-col pt-10 px-5 pb-5 flex gap-4 h-fit">
          <DiamondPercent class="text-green-500 w-3/6 h-3/6"/>
          <div class="flex flex-col justify-center h-20" >
            <p class="text-white text-2xl text-center font-semibold tracking-wide">
              Дешевле, чем ходить в магазин
            </p>
          </div>
        </div>
        <div class="bg-neutral-700 w-full rounded-2xl items-center flex-col pt-10 px-5 pb-5 flex gap-4 h-fit">
          <CircleCheckBig class="text-green-500 w-3/6 h-3/6"/>
          <div class="flex flex-col justify-center h-20" >
            <p class="text-white text-2xl text-center font-semibold tracking-wide">
              Проверяем качество
            </p>
          </div>
        </div>
    </div>
  </div>
   <div class="flex flex-col items-center w-full py-10 gap-8">
     <h1 class="text-white text-3xl font-bold">Наши партнеры</h1>
    <PartnerCarousel />
  </div>
</template>

<style scoped>
.justified-text {
  text-align: justify; /* Выравнивание текста по ширине */
}
</style>