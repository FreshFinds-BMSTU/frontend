<template>
  <div class="container mx-auto p-4">
    <h1 class="text-2xl text-white font-bold mb-4">История заказов</h1>
    <div v-if="orders.length === 0" class="text-center">
      <p class="text-white">У вас нет заказов.</p>
    </div>
    <ul v-else>
      <li v-for="order in orders" :key="order.id" class="flex flex-col border-b py-4">
        <h2 class="text-lg text-white font-semibold">Заказ #{{ order.id }}</h2>
        <p class="text-white">Содержимое:</p>
        <ul>
          <li v-for="item in order.items" :key="item.id" class="text-white">
            {{ item.name }} ({{ item.quantity }} шт.) - {{ item.price * item.quantity }} ₽
          </li>
        </ul>
        <p class="text-white font-bold">Итого: {{ order.totalPrice }} ₽</p>
      </li>
    </ul>
    <div class="mt-4">
      <button @click="clearHistory" class="mt-2 bg-red-500 text-white p-2 rounded">Очистить историю заказов</button>
    </div>
    <nuxt-link to="/client"><button class="bg-green-500 text-primary-50 rounded-md px-6 py-2 self-start mt-2">Назад</button></nuxt-link>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const orders = ref([]);

const loadOrders = () => {
  orders.value = JSON.parse(localStorage.getItem('orderHistory')) || [];
};

const clearHistory = () => {
  orders.value = [];
  localStorage.removeItem('orderHistory');
};

onMounted(() => {
  loadOrders();
});
</script>

<style scoped>
.container {
  max-width: 800px;
}
</style>
