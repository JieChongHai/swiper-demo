<script setup lang="ts">
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import "swiper/css/effect-cards";

import "./assets/style.css";

// import required modules
import { EffectCards } from "swiper";
import type { CardsEffectOptions, Swiper as SwiperType } from "swiper/types";

const modules = [EffectCards];
const cardsEffect: CardsEffectOptions = {
  perSlideOffset: 16,
  perSlideRotate: 0,
  rotate: false,
};
const clickSwiper = (swiper: SwiperType) => {
  console.log(swiper.clickedIndex);
  const { clickedIndex } = swiper;
  swiper.slideTo(clickedIndex);
};
</script>

<template>
  <swiper
    :direction="'vertical'"
    :effect="'cards'"
    :allowTouchMove="false"
    :cardsEffect="cardsEffect"
    :modules="modules"
    class="mySwiper"
    @click="clickSwiper"
  >
    <swiper-slide>Slide 1</swiper-slide>
    <swiper-slide>Slide 2</swiper-slide>
    <swiper-slide>Slide 3</swiper-slide>
  </swiper>
</template>

<style scoped></style>
