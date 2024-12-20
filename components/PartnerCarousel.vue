<template>
  <div class="partner-carousel">
    <swiper
      :slides-per-view="3"
      :space-between="30"
      loop
      :autoplay="{ delay: 1000 }"
      pagination
      navigation
    >
      <swiper-slide v-for="partner in partners" :key="partner.id">
        <img :src="partner.logo" :alt="partner.name" />
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/swiper-bundle.css';

export default {
  components: {
    Swiper,
    SwiperSlide
  },
  data() {
    return {
      // Partners data defined here
      partners: [
        { id: 1, name: 'Партнер 1', logo: '~/assets/logos/partner1.png'},
        { id: 2, name: 'Партнер 2', logo: '~/assets/logos/partner2.png'},
        { id: 3, name: 'Партнер 3', logo: '~/assets/logos/partner3.png'},
        { id: 4, name: 'Партнер 4', logo: '~/assets/logos/partner4.png'},
        { id: 5, name: 'Партнер 5', logo: '~/assets/logos/partner5.png'}
      ]
    };
  }
};
</script>

<style scoped>
.partner-carousel {
  width: 100%;
  padding: 20px;
  box-sizing: border-box; /* Ensure padding is accounted for */
}
.partner-carousel img {
  max-width: 100%;
  height: auto;
  display: block; /* Improve image display consistency */
  margin: 0 auto; /* Center images if they are smaller */
}
</style>