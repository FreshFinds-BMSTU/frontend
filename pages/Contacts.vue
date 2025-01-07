<template>
  <header><Header1></Header1></header>
  <div>
    <div class = "flex flex-row items-center p-3 gap-2">
    <h1 class="text-white text-2xl font-bold">Контакты</h1>
     <Contact class=" text-green-500 w-4/10 h-4/10"/>
  </div>
    <p class = "px-3 text-white font-medium">По вопросам сотрудничества: FreshFinds@yandex.ru</p>
  </div>
</template>

<script setup lang="ts">
import {Contact} from 'lucide-vue-next';
import Header1 from '@/components/Header1.vue'
</script>
