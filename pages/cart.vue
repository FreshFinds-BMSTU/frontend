<template>
  <div class="container mx-auto p-4">
    <h1 class="text-2xl text-white font-bold mb-4">Корзина</h1>
    <div v-if="cartItems.length === 0" class="text-center">
      <p class="text-white">Ваша корзина пуста.</p>
    </div>
    <ul v-else>
      <li v-for="item in cartItems" :key="item.id" class="flex items-center justify-between border-b py-4">
        <img :src="item.image" alt="Изображение товара" class="w-16 h-16 object-cover mr-4" />
        <div class="flex-1">
          <h2 class="text-lg text-white font-semibold">{{ item.name }}</h2>
          <p class="text-white">Цена: {{ item.price }} ₽</p>
        </div>
        <div class="flex items-center">
          <button @click="decreaseQuantity(item)" class="bg-green-500 p-1 rounded">-</button>
          <span class="mx-2 text-white">{{ item.quantity }}</span>
          <button @click="increaseQuantity(item)" class="bg-green-500 p-1 rounded">+</button>
          <button @click="removeItem(item)" class="ml-4 text-red-500">Удалить</button>
        </div>
      </li>
    </ul>
    <div class="mt-4">
      <p class="text-white font-bold">Итого: {{ totalPrice }} ₽</p>
      <div class="flex flex-col w-[150px] h-[150px]">
        <div v-if="cartItems.length > 0">
          <button @click="placeOrder" class="mt-2 bg-green-600 text-white p-2 rounded">Заказать</button>
        </div>

          <button @click="clearCart" class="mt-2 bg-red-500 text-white p-2 rounded  w-40 h-12">Очистить корзину</button>
          <nuxt-link to="/client" class="py-4"><button class="bg-green-500 text-primary-50 rounded-md px-3 py-2 self-start">Вернуться назад</button></nuxt-link>

      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted } from 'vue';

const cartItems = ref([]);

const loadCart = () => {
  cartItems.value = JSON.parse(localStorage.getItem('cartItems')) || [];
};

const totalPrice = computed(() => {
  return cartItems.value.reduce((total, item) => total + item.price * item.quantity, 0);
});

const increaseQuantity = (item) => {
  item.quantity += 1;
  saveCart();
};

const decreaseQuantity = (item) => {
  if (item.quantity > 1) {
    item.quantity -= 1;
    saveCart();
  }
};

const removeItem = (item) => {
  cartItems.value = cartItems.value.filter(cartItem => cartItem.id !== item.id);
  saveCart();
};

const clearCart = () => {
  cartItems.value = [];
  localStorage.removeItem('cartItems'); // Очищаем localStorage
};

const saveCart = () => {
  localStorage.setItem('cartItems', JSON.stringify(cartItems.value));
};

const placeOrder = () => {
  const order = {
    id: Date.now(), // Уникальный идентификатор заказа
    items: cartItems.value.map(item => ({
      id: item.id,
      name: item.name,
      quantity: item.quantity,
      price: item.price
    })),
    totalPrice: totalPrice.value
  };

  // Сохранение заказа в localStorage
  const orderHistory = JSON.parse(localStorage.getItem('orderHistory')) || [];
  orderHistory.push(order);
  localStorage.setItem('orderHistory', JSON.stringify(orderHistory));

  // Очистка корзины после оформления заказа
  clearCart();
};

onMounted(() => {
  loadCart(); // Загружаем корзину при монтировании компонента
});
</script>

<style scoped>
.container {
  max-width: 800px;
}
</style>
