<template>
  <header>
    <Header1></Header1>
  </header>
  <div class = "flex gap-2 items-center py-3 px-4">
    <h1 class="text-white text-xl font-bold">Наша команда</h1>
     <Users class=" text-green-500 w-1/10 h-1/10"/>
  </div>
  <p class="text-white px-4">
    Мы молодые разработчики из ГБОУ школы № 1580. Сайт сделан в рамках проектной деятельности в  МГТУ им. Н. Э. Баумана
  </p>
</template>

<script setup lang="ts">
import {Users} from 'lucide-vue-next';
import Header1 from '@/components/Header1.vue'
</script>
