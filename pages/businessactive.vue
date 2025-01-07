<template>
      <header>
        <Header3></Header3>
      </header>
      <main>
        <h1 class="font-title text-3xl text-neutral-50 p-3">Управление пакетами продуктов</h1>
        <section class="grid gap-6 mb-8 p-3">
          <article class="flex justify-between items-center p-4 bg-neutral-700 rounded-md">
            <div class>
              <h2 class="text-lg font-medium text-neutral-50">Пакет товаров #1</h2>
              <p class="text-sm text-neutral-400">Детали о пакете товаров №1</p>
            </div>
            <div class="flex gap-4">
              <button class="bg-green-500 text-primary-50 rounded-md px-4 py-2">Редактировать</button>
              <button class="bg-red-500 text-white rounded-md px-4 py-2">Удалить</button>
            </div>
          </article>
          <article class="flex justify-between items-center p-4 bg-neutral-700 rounded-md">
            <div>
              <h2 class="text-lg font-medium text-neutral-50">Пакет товаров #2</h2>
              <p class="text-sm text-neutral-400">Детали о пакете товаров №2</p>
            </div>
            <div class="flex gap-4">
              <button class="bg-green-500 text-primary-50 rounded-md px-4 py-2">Редактировать</button>
              <button class="bg-red-500 text-white rounded-md px-4 py-2">Удалить</button>
            </div>
          </article>
        </section>
      <div class = "flex flex-col gap-3 px-3">
        <details class="bg-neutral-700 p-5 rounded-md">
          <summary class="text-neutral-50 cursor-pointer">Создать новый пакет товаров</summary>
          <form @submit.prevent="addPackage" class="mt-4 grid gap-4">
            <input
              v-model="newPackage.name"
              class="border border-neutral-700 bg-neutral-800 text-neutral-50 rounded-md p-2"
              type="text"
              placeholder="Название пакета"
              required
            />
            <textarea
              v-model="newPackage.description"
              class="border border-neutral-700 bg-neutral-800 text-neutral-50 rounded-md p-2"
              placeholder="Описание пакета"
              required
            ></textarea>
            <input
              v-model="newPackage.price"
              class="border border-neutral-700 bg-neutral-800 text-neutral-50 rounded-md p-2"
              type="number"
              placeholder="Цена пакета"
              min="0"
              required
            />
            <button class="bg-green-500 text-primary-50 rounded-md px-6 py-2 self-start">Сохранить</button>
          </form>
        </details>
        <div class = "flex justify-end">
          <nuxt-link to="/business" class="py-4"><button class="bg-green-500 text-primary-50 rounded-md px-6 py-2 self-start">Назад</button></nuxt-link>
        </div>
        </div>
      </main>
</template>

<script>
export default {
  data() {
    return {
      newPackage: {
        name: '',
        description: '',
        price: null,
      },
    };
  },
  methods: {
    addPackage() {
      console.log('Новый пакет товаров:', this.newPackage);

      this.newPackage.name = '';
      this.newPackage.description = '';
      this.newPackage.price = null;
    },
  },
};
import Header3 from "~/components/Header3.vue";
</script>

<style scoped>
/* Добавьте стили, если необходимо */
</style>
