<template>
  <div class="flex flex-row items-center w-auto p-5">
    <div class="flex flex-col items-center rounded-lg max-w-xs mx-auto text-center bg-neutral-700 shadow-[0px_2px_5px_0px_rgba(0,0,0,0.10)]">
      <img
        src="https://main-cdn.sbermegamarket.ru/big2/hlr-system/166/668/630/575/203/2/100056492808b0.jpg"
        alt="Круассан"
        class="w-64 h-64 mb-4 rounded-md"
      />
      <p class="text-lg font-bold text-gray-950">Круассан</p>
      <p class="text-black">80₽</p>
      <div class="flex mt-4 gap-2 p-2 items-center justify-center">
        <button class="w-10 h-10 bg-green-500 text-black rounded-md hover:bg-blue-600">-</button>
        <span class="text-white">1</span>
        <button class="w-10 h-10 bg-green-500 text-black rounded-md hover:bg-blue-600">+</button>
      </div>
    </div>
    <div class="flex flex-col items-center rounded-lg max-w-xs mx-auto text-center bg-neutral-700 shadow-[0px_2px_5px_0px_rgba(0,0,0,0.10)]">
      <img
        src="https://main-cdn.sbermegamarket.ru/big1/hlr-system/-50/075/097/475/144/7/100055999361b0.jpg"
        alt="Слойка"
        class="w-64 h-64 mb-4 rounded-md"
      />
      <p class="text-lg font-bold text-gray-950">Слойка</p>
      <p class="text-black">60₽</p>
      <div class="flex mt-4 gap-2 p-2 items-center justify-center">
        <button class="w-10 h-10 bg-green-500 text-black rounded-md hover:bg-blue-600">-</button>
        <span class="text-white">1</span>
        <button class="w-10 h-10 bg-green-500 text-black rounded-md hover:bg-blue-600">+</button>
      </div>
    </div>
    <div class="flex flex-col items-center rounded-lg max-w-xs mx-auto text-center bg-neutral-700 shadow-[0px_2px_5px_0 rgba(0,0,0,0.10)]">
      <img
        src="https://apeti.ru/upload/iblock/a84/lepeshka_tomaty_s_bazilikom_180_g.jpg"
        alt="Пицца"
        class="w-64 h-64 mb-4 rounded-md"
      />
      <p class="text-lg font-bold text-gray-950">Пицца</p>
      <p class="text-black">120₽</p>
      <div class="flex mt-4 gap-2 items-center p-2 justify-center">
        <button class="w-10 h-10 bg-green-500 text-black rounded-md hover:bg-blue-600">-</button>
        <span class="text-white">1</span>
        <button class="w-10 h-10 bg-green-500 text-black rounded-md hover:bg-blue-600">+</button>
      </div>
    </div>
  </div>
  <div class="flex justify-end">
    <nuxt-link to="/cart" class="p-4">
      <button class="bg-green-500 text-primary-50 rounded-md px-6 py-2 self-start">Сохранить</button>
    </nuxt-link>
  </div>
</template>

<script setup lang="ts">
</script>

<style scoped>
</style>