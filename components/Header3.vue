<template>
  <div class="h-16 px-5 py-2.5 bg-[#151517] flex items-center justify-between text-white relative">
    <div class="absolute left-5 gap-8 hidden md:flex">
      <div class="relative">
        <button
          class="flex gap-2 text-lg font-medium tracking-wide justify-center items-center"
          @click="firstDropDownOpen = !firstDropDownOpen; secondDropDownOpen = false;"
        >
          О нас
          <ChevronDown
            class="transition-transform duration-200 scale-150"
            :class="{ 'rotate-180': firstDropDownOpen }"
          />
        </button>
        <div v-if="firstDropDownOpen" class="absolute bg-white text-black rounded shadow-lg mt-2">
          <ul>
            <li class="px-4 py-2 hover:bg-gray-200">
              <nuxt-link to="/Team">Наша команда</nuxt-link>
            </li>
            <li class="px-4 py-2 hover:bg-gray-200">
              <nuxt-link to="/Contacts">Контакты</nuxt-link>
            </li>
          </ul>
        </div>
      </div>
      <div class="relative">
        <button
          class="flex gap-2 text-lg font-medium tracking-wide justify-center items-center"
          @click="secondDropDownOpen = !secondDropDownOpen; firstDropDownOpen = false;"
        >
          О пищевых отходах
          <ChevronDown
            class="transition-transform duration-200 scale-150"
            :class="{ 'rotate-180': secondDropDownOpen }"
          />
        </button>
        <div v-if="secondDropDownOpen" class="absolute bg-white text-black rounded shadow-lg mt-2">
          <ul>
            <li class="px-4 py-2 hover:bg-gray-200">
              <nuxt-link to="/Reasons">Причины пищевых отходов</nuxt-link>
            </li>
            <li class="px-4 py-2 hover:bg-gray-200">
              <nuxt-link to="/ReduceWaste">О сокращении отходов</nuxt-link>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <a href="" class="relative left-1/2 transform -translate-x-1/2">
      <img :src="logo" :alt="описание" class="w-18 h-12" />
    </a>

    <div class="relative">
      <img
        src="https://i.pinimg.com/originals/1f/28/c6/1f28c68d2c35f389966b5a363b992d06.png"
        alt="User Avatar"
        class="cursor-pointer w-10 h-10 rounded-full"
      />
    <div class="md:hidden">
      <Menu />
    </div>
  </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { ChevronDown, Menu } from "lucide-vue-next";
import logo from "~/static/logos/logo.png";

const firstDropDownOpen = ref(false);
const secondDropDownOpen = ref(false);

</script>

<style scoped>
/* Optional: Adjust these styles for better visuals */
</style>
