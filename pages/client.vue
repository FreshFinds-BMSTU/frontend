<script setup lang="ts">
import {Header2} from "#components";
import { ref } from 'vue';

const isModalVisible = ref(false);

const toggleModal = () => {
  isModalVisible.value = !isModalVisible.value;
};

const closeModal = () => {
  isModalVisible.value = false;
};

const isModalVisible2 = ref(false);

const toggleModal2 = () => {
  isModalVisible2.value = !isModalVisible2.value;
};

const closeModal2 = () => {
  isModalVisible2.value = false;
};
</script>

<template>
  <header>
    <Header2> </Header2>
  </header>
<div class=" items-center inline-flex">
    <div class="flex flex-wrap justify-center items-center gap-4 p-4">
        <div class="px-[39px] py-[13px] bg-[#2a2929] rounded-[5px] shadow-[0px_2px_5px_0px_rgba(0,0,0,0.10)] flex-col justify-center items-center gap-7 inline-flex">
            <div class="self-stretch h-[27px] text-center text-white text-2xl font-bold">Скидка 50% на выпечку</div>
            <img src="/static/logos/partner2.png" alt="Описание изображения" class="w-64 h-64" />
            <div class="self-stretch h-[15px] text-center text-white text-[14.88px] font-normal p-2 ">Не упустите возможность попробовать новинки сниженной цене!</div>
          <div class="p-4">
            <a class="px-8 py-1.5 bg-green-600 rounded-[5px] hidden md:block text-white" href="">
            В корзину
            </a>
          </div>
        </div>
      <div class="px-[39px] py-[13px] bg-[#2a2929] rounded-[5px] shadow-[0px_2px_5px_0px_rgba(0,0,0,0.10)] flex-col justify-center items-center gap-7 inline-flex">
            <div class="self-stretch h-[27px] text-center text-white text-2xl font-bold">Скидка 30% на пакет кофе + десерт</div>
            <img src="/static/logos/partner5.png" alt="Описание изображения" class="w-64 h-64" />
            <div class="self-stretch h-[15px] text-center text-white text-[14.88px] font-normal p-2 ">Порадуйте себя в этот прекрасный зимний день!</div>
          <div class="p-4">
            <a class="px-8 py-1.5 bg-green-600 rounded-[5px] hidden md:block text-white" href="">
            В корзину
            </a>
          </div>
      </div>
      <div class="px-[39px] py-[13px] bg-[#2a2929] rounded-[5px] shadow-[0px_2px_5px_0px_rgba(0,0,0,0.10)] flex-col justify-center items-center gap-7 inline-flex">
            <div class="self-stretch h-[27px] text-center text-white text-2xl font-bold">Набор "Завтрак"</div>
            <img src="/static/logos/partner1.png" alt="Описание изображения" class="w-64 h-64" />
            <div class="self-stretch h-[15px] text-center text-white text-[14.88px] font-normal p-2 ">Продукты для идеального завтрака</div>
        <button @click="toggleModal" class="text-white underline">Состав</button>
  <div v-if="isModalVisible" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center">
    <div class="bg-neutral-800 rounded-lg p-3 w-80">
      <button @click="closeModal" class="text-green-500 float-right">✖</button>
      <h2 class="text-lg font-bold text-white mb-2">Состав пакета:</h2>
      <textarea rows="4" class="w-full p-1 rounded-md bg-gray-800 text-white" readonly>
хз
      </textarea>
    </div>
  </div>
          <div class="p-2">
            <a class="px-8 py-1.5 bg-green-600 rounded-[5px] hidden md:block text-white" href="">
            В корзину
            </a>
          </div>
        </div>
      <div class="px-[39px] py-[13px] bg-[#2a2929] rounded-[5px] shadow-[0px_2px_5px_0px_rgba(0,0,0,0.10)] flex-col justify-center items-center gap-7 inline-flex">
            <div class="self-stretch h-[27px] text-center text-white text-2xl font-bold">Пакет "Сюрприз"</div>
        <img src="/static/logos/partner4.png" alt="Описание изображения" class="w-64 h-64" />
            <div class="self-stretch h-[15px] text-center text-white text-[14.88px] font-normal p-2 ">Пакет, состав которого вы не знаете</div>
          <div class="p-4">
            <a class="px-8 py-1.5 bg-green-600 rounded-[5px] hidden md:block text-white" href="">
            В корзину
            </a>
          </div>
        </div>
      <div class="px-[39px] py-[13px] bg-[#2a2929] rounded-[5px] shadow-[0px_2px_5px_0px_rgba(0,0,0,0.10)] flex-col justify-center items-center gap-7 inline-flex">
            <div class="self-stretch h-[27px] text-center text-white text-2xl font-bold">Пакет "Здоровое питание"</div>
        <img src="/static/logos/partner3.png" alt="Описание изображения" class="w-64 h-64" />
            <div class="self-stretch h-[15px] text-center text-white text-[14.88px] font-normal p-2 ">Пакет продуктов, которые способствуют здоровому питанию, включая свежие овощи, фрукты и полезные закуски.</div>

        <button @click="toggleModal2" class="text-white underline">Состав</button>
  <div v-if="isModalVisible2" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center">
    <div class="bg-neutral-800 rounded-lg p-3 w-80">
      <button @click="closeModal2" class="text-green-500 float-right">✖</button>
      <h2 class="text-lg font-bold text-white mb-2">Состав пакета:</h2>
      <textarea rows="4" class="w-full p-1 rounded-md bg-gray-800 text-white" readonly>
хз
      </textarea>
    </div>
    </div>
          <div class="p-3">
            <a class="px-8 py-1.5 bg-green-600 rounded-[5px] hidden md:block text-white" href="">
            В корзину
            </a>
          </div>
    </div>
</div>
</div>
</template>

<style scoped>

</style>