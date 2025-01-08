<template>
  <div class="px-[39px] py-[13px] bg-[#2a2929] rounded-[5px] shadow-[0px_2px_5px_0px_rgba(0,0,0,0.10)] flex-col justify-center items-center gap-4 inline-flex">
            <p class="self-stretch h-[27px] text-center text-white text-2xl font-bold">{{ product.name }}</p>
            <img :src="product.image" alt="Описание изображения" class="w-60 h-60" />
            <div class="self-stretch h-[15px] text-center text-white text-[14.88px] font-normal p-2 ">{{ product.alt }}</div>
        <button @click="toggleModal" class="text-white underline">Состав</button>
  <div v-if="isModalVisible" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center">
    <div class="bg-neutral-800 rounded-lg p-2 w-80">
      <button @click="closeModal" class="text-green-500 float-right">✖</button>
      <h2 class="text-lg font-bold text-white mb-2">Состав пакета:</h2>
      <textarea rows="4" class="w-full p-1 rounded-md bg-gray-800 text-white" readonly>{{ product.comp }}</textarea>
    </div>
  </div>
    <p class="text-white">Цена: {{ product.price}} ₽</p>
    <button @click="addToCart" class="bg-green-500 p-2 text-black rounded-md">Добавить в корзину</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const isModalVisible = ref(false);

const toggleModal = () => {
  isModalVisible.value = !isModalVisible.value;
};

const closeModal = () => {
  isModalVisible.value = false;
};

const props = defineProps({
  product: {
    type: Object,
    required: true,
  },
});

const addToCart = () => {
  const cartItems = JSON.parse(localStorage.getItem('cartItems')) || [];
  const existingItem = cartItems.find(item => item.id === props.product.id);

  if (existingItem) {
    existingItem.quantity += 1;
  } else {
    cartItems.push({ ...props.product, quantity: 1 });
  }

  localStorage.setItem('cartItems', JSON.stringify(cartItems));
};
</script>
