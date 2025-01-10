<template>
  <div class="text-white min-h-screen flex flex-col">
    <header>
      <Header4></Header4>
    </header>
    <main class="flex-grow px-6 py-4">
      <section class="mb-7">
        <h2 class="text-2xl font-semibold">Управление бизнесом</h2>
        <p class ="py-2">Здесь вы можете управлять своими предложениями.</p>
        <nuxt-link to="/businessactive" class="py-4"><button class="bg-green-500 text-black rounded-md px-6 py-2 self-start">Управлять бизнесом</button></nuxt-link>
      </section>
      <section>
        <h2 class="text-2xl font-semibold">Контакты</h2>
        <p>Свяжитесь с нами для получения дополнительной информации.</p>
      </section>
      <section class="mb-7 py-7">
        <h2 class="text-2xl font-semibold">Информация о бизнесе</h2>
        <p class ="py-2">Здесь вы можете редактировать данные о вашей компании, их будет видеть клиент.</p>
        <nuxt-link to="/businessinfo" class="py-4"><button class="bg-green-500 text-black rounded-md px-6 py-2 self-start">Информация о бизнесе</button></nuxt-link>
      </section>
    </main>
  </div>
</template>

<script>
import Header4 from "~/components/Header4.vue";
</script>

<style scoped>
/* Дополнительные стили для страницы можно добавить здесь */
</style>
