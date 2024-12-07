<script setup lang="ts">
import { ref } from "vue";
import { ChevronDown, Menu } from "lucide-vue-next";

const firstDropDownOpen = ref(false);
const secondDropDownOpen = ref(false);
</script>

<template>
  <div class="h-16 px-5 py-2.5 bg-[#151517] flex items-center justify-between text-white relative">
    <div class="absolute left-5 gap-8 hidden md:flex">
      <button
          class="flex gap-2 text-lg font-medium tracking-wide justify-center items-center"
          @click="firstDropDownOpen = !firstDropDownOpen; secondDropDownOpen = false"
      >
        О нас
        <ChevronDown
            class="transition-transform duration-200 scale-150"
            :class="{ 'rotate-180': firstDropDownOpen }"
        />
      </button>
      <button
          class="flex gap-2 text-lg font-medium tracking-wide justify-center items-center"
          @click="secondDropDownOpen = !secondDropDownOpen; firstDropDownOpen = false"
      >
        О пищевых отходах
        <ChevronDown
            class="transition-transform duration-200 scale-150"
            :class="{ 'rotate-180': secondDropDownOpen }"
        />
      </button>
    </div>
    <a href="/" class="relative left-1/2 transform -translate-x-1/2">
      <h2 class="text-2xl font-semibold">[Логотип]</h2>
    </a>
    <a class="px-8 py-1.5 bg-green-600 rounded-full hidden md:block" href="https://auth.spoverlay.ru/authorize">
      Войти
    </a>
    <div class="md:hidden">
      <Menu />
    </div>
  </div>

</template>


<style scoped>
/* Optional: Adjust these styles for better visuals */
</style>
