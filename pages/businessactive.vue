<template>
  <header>
    <Header3></Header3>
  </header>
  <main>
    <h1 class="font-title text-3xl text-neutral-50 p-3">Управление пакетами продуктов</h1>
    <section class="grid gap-6 mb-8 p-3">
      <article
        v-for="(pkg, index) in packages"
        :key="index"
        class="flex justify-between items-center p-4 bg-neutral-700 rounded-md"
      >
        <div>
          <h2 class="text-lg font-medium text-neutral-50">{{ pkg.name }}</h2>
          <p class="text-sm text-neutral-400">{{ pkg.description }}</p>
        </div>
        <div class="flex gap-4">
          <button @click="openEditModal(index)" class="bg-green-500 text-primary-50 rounded-md px-4 py-2">Редактировать</button>
          <button @click="deletePackage(index)" class="bg-red-500 text-white rounded-md px-4 py-2">Удалить</button>
        </div>
      </article>
    </section>

    <!-- Форма для создания нового пакета -->
    <details class="bg-neutral-700 p-5 rounded-md form-width">
      <summary class="text-neutral-50 cursor-pointer">Создать новый пакет товаров</summary>
      <form @submit.prevent="addPackage" class="mt-4 grid gap-4">
        <input
          v-model="newPackage.name"
          class="border border-neutral-700 bg-neutral-800 text-neutral-50 rounded-md p-2"
          type="text"
          placeholder="Название пакета"
          required
        />
        <input
          v-model="newPackage.description"
          class="border border-neutral-700 bg-neutral-800 text-neutral-50 rounded-md p-2"
          type="text"
          placeholder="Описание пакета"
          required
        />
        <textarea
          v-model="newPackage.content"
          class="border border-neutral-700 bg-neutral-800 text-neutral-50 rounded-md p-2"
          placeholder="Состав пакета"
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

    <!-- Модальное окно для редактирования пакета -->
    <div v-if="isEditModalOpen" class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-50">
      <div class="bg-neutral-800 p-5 rounded-md">
        <h2 class="text-neutral-50">Редактировать пакет товаров</h2>
        <form @submit.prevent="updatePackage" class="mt-4 grid gap-4">
          <input
            v-model="editPackage.name"
            class="border border-neutral-700 bg-neutral-800 text-neutral-50 rounded-md p-2"
            type="text"
            placeholder="Название пакета"
            required
          />
          <input
            v-model="editPackage.description"
            class="border border-neutral-700 bg-neutral-800 text-neutral-50 rounded-md p-2"
            type="text"
            placeholder="Описание пакета"
            required
          />
          <textarea
            v-model="editPackage.content"
            class="border border-neutral-700 bg-neutral-800 text-neutral-50 rounded-md p-2"
            placeholder="Состав пакета"
            required
          ></textarea>
          <input
            v-model="editPackage.price"
            class="border border-neutral-700 bg-neutral-800 text-neutral-50 rounded-md p-2"
            type="number"
            placeholder="Цена пакета"
            min="0"
            required
          />
          <div class="flex justify-end">
            <button @click="resetEditPackageForm" class="bg-red-500 text-white rounded-md px-4 py-2 mr-2">Отмена</button>
                        <button @click="updatePackage" type="submit" class="bg-green-500 text-primary-50 rounded-md px-4 py-2">Обновить</button>
          </div>
        </form>
      </div>
    </div>

    <div class="flex justify-start">
      <nuxt-link to="/business" class="py-4"><button class="bg-green-500 text-primary-50 rounded-md px-6 py-2 self-start ml-3">Назад</button></nuxt-link>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      packages: [], // Массив для хранения пакетов
      newPackage: { // Данные для создания нового пакета
        name: '',
        description: '',
        content: '',
        price: null,
      },
      editPackage: { // Данные для редактируемого пакета
        name: '',
        description: '',
        content: '',
        price: null,
      },
      editingIndex: null, // Индекс редактируемого пакета
      isEditModalOpen: false, // Флаг для управления видимостью модального окна
    };
  },
  mounted() {
    this.loadPackages(); // Загружаем пакеты из localStorage при монтировании компонента
  },
  methods: {
    loadPackages() {
      const storedPackages = localStorage.getItem('packages');
      this.packages = storedPackages ? JSON.parse(storedPackages) : [];
    },
    savePackages() {
      localStorage.setItem('packages', JSON.stringify(this.packages));
    },
    addPackage() {
      this.packages.push({...this.newPackage});
      this.savePackages(); // Сохраняем пакеты в localStorage
      this.resetNewPackageForm();
    },
    openEditModal(index) {
      this.editingIndex = index;
      this.editPackage = {...this.packages[index]};
      this.isEditModalOpen = true;
    },
    updatePackage() {
      this.packages[this.editingIndex] = {
        name: this.editPackage.name,
        description: this.editPackage.description,
        content: this.editPackage.content,
        price: this.editPackage.price,
      };
      this.savePackages(); // Сохраняем пакеты в localStorage
      this.isEditModalOpen = false; // Закрыть модальное окно
      this.editingIndex = null;
    },
    deletePackage(index) {
      this.packages.splice(index, 1);
      this.savePackages(); // Сохраняем пакеты в localStorage
    },
    resetNewPackageForm() {
      this.newPackage = {
        name: '',
        description: '',
        content: '',
        price: null,
      };
    },
    resetEditPackageForm() {
      this.editPackage = {
        name: '',
        description: '',
        content: '',
        price: null,
      };
      this.isEditModalOpen = false; // Закрыть модальное окно
    },
  },
}
</script>

<style scoped>
.fixed {
  position: fixed;
}
.inset-0 {
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}
.bg-black {
  background-color: rgba(0, 0, 0, 0.5);
}
.form-width {
  max-width: 1290px;
  margin-left: 13px;
}
</style>

