<template>
  <div class="flex items-center justify-center min-h-screen">
    <div class="w-[1200px] min-h-[800px] p-10">
      <header class="flex justify-between items-center mb-8">
        <h1 class="font-title text-3xl text-neutral-50">Управление пакетами акций</h1>
        <button class="bg-green-500 text-primary-50 rounded-md px-6 py-2">Создать пакет</button>
      </header>
      <main>
        <section class="grid gap-6 mb-8">
          <article class="flex justify-between items-center p-4 bg-neutral-700 rounded-md">
            <div>
              <h2 class="text-lg font-medium text-neutral-50">Пакет акций #1</h2>
              <p class="text-sm text-neutral-400">Детали о пакете акций №1</p>
            </div>
            <div class="flex gap-4">
              <button class="bg-green-500 text-primary-50 rounded-md px-4 py-2">Редактировать</button>
              <button class="bg-red-500 text-white rounded-md px-4 py-2">Удалить</button>
            </div>
          </article>
          <article class="flex justify-between items-center p-4 bg-neutral-700 rounded-md">
            <div>
              <h2 class="text-lg font-medium text-neutral-50">Пакет акций #2</h2>
              <p class="text-sm text-neutral-400">Детали о пакете акций №2</p>
            </div>
            <div class="flex gap-4">
              <button class="bg-green-500 text-primary-50 rounded-md px-4 py-2">Редактировать</button>
              <button class="bg-red-500 text-white rounded-md px-4 py-2">Удалить</button>
            </div>
          </article>
        </section>
        <details class="bg-neutral-700 p-4 rounded-md">
          <summary class="text-neutral-50 cursor-pointer">Создать новый пакет акций</summary>
          <form class="mt-4 grid gap-4">
            <input class="border border-neutral-700 bg-neutral-800 text-neutral-50 rounded-md p-2" type="text" placeholder="Название пакета"/>
            <textarea class="border border-neutral-700 bg-neutral-800 text-neutral-50 rounded-md p-2" placeholder="Описание пакета"></textarea>
            <button class="bg-green-500 text-primary-50 rounded-md px-6 py-2 self-start">Сохранить</button>
          </form>
        </details>
      </main>
    </div>
  </div>
</template>
