<template>
  <header>
    <Header1></Header1>
  </header>
  <div>
    <h1 class = "text-white text-3xl font-bold p-4">Как сократить отходы</h1>
    <h2 class = "text-white px-5 font-medium text-xl ">Для семей</h2>
    <ul class="dot-list">
      <li class = "text-white">Составлять меню на неделю вперед</li>
      <li class = "text-white">Проверять холодильник перед походом в магазин</li>
      <li class = "text-white">Делать список покупок и строго его придерживаться</li>
      <li class = "text-white">Не ходить в магазин голодным</li>
    </ul>
    <h2 class = "text-white px-5  font-medium text-xl ">Для кафе и ресторанов</h2>
    <ul class="dot-list">
      <li class = "text-white">Планирование запасов: Эффективное управление запасами и прогнозирование спроса помогут избежать излишков продуктов.
        Использование систем учета и анализа данных может помочь в этом.
</li>
      <li class = "text-white">Оптимизация меню: Рестораны могут анализировать популярность блюд и адаптировать меню, чтобы уменьшить количество незаказанных позиций.
        Это поможет сократить количество приготовленной, но не использованной пищи.</li>
      <li class = "text-white">Обучение персонала: Обучение сотрудников правильным методам хранения и обработки продуктов поможет снизить количество отходов на кухне.</li>
    </ul>
<h2 class = "text-white px-5 py-2 font-medium text-xl ">Использование Fresh Finds и аналогичных сервисов также поможет сократить количество пищевых отходов </h2>  </div>
</template>

<script setup lang="ts">
import Header1 from '@/components/Header1.vue'
</script>

<style scoped>
.dot-list {
  list-style-type: disc; /* Устанавливаем маркеры в виде точек */
  padding-left: 5%; /* Отступ слева для списка */
}
</style>
