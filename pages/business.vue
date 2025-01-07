<template>
  <div class="text-white min-h-screen flex flex-col">
    <header>
      <Header4></Header4>
    </header>
    <main class="flex-grow p-4">
      <section class="mb-7">
        <h2 class="text-2xl font-semibold">Управление бизнесом</h2>
        <p class ="py-2">Здесь вы можете управлять своими предложениями и просматривать статистику.</p>
        <nuxt-link to="/businessactive" class="py-4"><button class="bg-green-500 text-black rounded-md px-6 py-2 self-start">Управлять бизнесом</button></nuxt-link>
      </section>
      <section class="mb-6">
        <h2 class="text-2xl font-semibold">Отзывы</h2>
        <p>Пользователи могут оставлять свои отзывы о вашем бизнесе.</p>
      </section>
      <section>
        <h2 class="text-2xl font-semibold">Контакты</h2>
        <p>Свяжитесь с нами для получения дополнительной информации.</p>
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
