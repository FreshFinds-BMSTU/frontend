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

import partner1 from '~/static/logos/partner1.png';
import partner2 from '~/static/logos/partner2.png';
import partner3 from '~/static/logos/partner3.png';
import partner4 from '~/static/logos/partner4.png';
import partner5 from '~/static/logos/partner5.png';

export default {
  components: {
    Swiper,
    SwiperSlide
  },
  data() {
    return {
      partners: [
        { id: 1, name: 'Партнер 1', logo: partner1 },
        { id: 2, name: 'Партнер 2', logo: partner2 },
        { id: 3, name: 'Партнер 3', logo: partner3 },
        { id: 4, name: 'Партнер 4', logo: partner4 },
       { id: 5, name: 'Партнер 5', logo: partner5 }
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
  max-width: 50%;
  height: auto;
  display: block; /* Improve image display consistency */
  margin: 0 auto; /* Center images if they are smaller */
}
</style>
