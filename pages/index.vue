<script setup lang="ts">
import { CircleCheckBig, Clock8, Salad, DiamondPercent } from 'lucide-vue-next';


</script>

<template>
  <div class="flex flex-col items-center w-full py-20">
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
</template>

<style scoped>

</style>