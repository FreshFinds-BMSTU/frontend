<template>
  <header>
    <Header2></Header2>
  </header>
  <div class="p-5 flex flex-wrap gap-5 justify-center">
    <Product :product="product1" />
    <Product :product="product2" />
    <Product :product="product3" />
    <Product :product="product4" />
    <Product :product="product5" />
  </div>
</template>

<script setup>
import Product from '/components/tovar.vue';
import one from '/static/logos/partner1.png'
import two from '/static/logos/partner4.png'
import three from '/static/logos/partner5.png'
import four from '/static/logos/partner2.png'
import five from '/static/logos/partner3.png'
import Header2 from '/components/Header2.vue'
const product1 = {
  id: 1,
  name: 'Пакет "Завтрак"',
  image:one,
  alt: 'Продукты для идеального завтрака',
  comp:'2 свежих круассана, 1 йогурт, 1 порция сезонных фруктов (например, яблоко или банан), 1 чашка кофе',
  price: 1500,
};
const product2 = {
  id: 2,
  name: 'Пакет "Сюрприз"',
  image:two,
  alt: 'Пакет, состав которого вы не знаете',
  comp:'Секрет',
  price: 500,
};
const product3 = {
  id: 3,
  name: 'Пакет "Здоровый"',
  image:three,
  alt: 'Пакет для тех, кто хочет правильно питаться',
  comp:'Салат овощной\n' +
      'Фрукты\n' +
      'Протеиновый батончик',
  price: 500,
};
const product4 = {
  id: 4,
  name: 'Сладкий пакет',
  image:four,
  alt: 'Для сладкоежек — идеальный набор десертов.',
  comp:'Ассорти из выпечки, тортов, печенья и конфет',
  price: 1500,
};
const product5 = {
  id: 5,
  name: 'Вегетарианский пакет',
  image:five,
  alt: 'Вкусные и сытные блюда для вегетарианцев',
  comp:'2 овощные котлеты, 1 порция гречки, 1 порция овощного салата, фруктовая нарезка (яблоко, мандарин, банан).',
  price: 1600,
};
</script>
