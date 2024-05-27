<script setup lang="ts">
import { Carousel, Slide } from "vue3-carousel";
import { allSliders } from "@/data/slilders";
import "vue3-carousel/dist/carousel.css";
</script>

<template>
  <Carousel :autoplay="4000" :itemsToShow="1" :wrapAround="true" :transition="0">
    <Slide v-for="slide in allSliders" :key="slide.id">
      <img :src="slide.src" alt="" />
    </Slide>
  </Carousel>
</template>

<style scoped>
.carousel {
  pointer-events: none !important;
}
.carousel__slide img {
  opacity: 0;
  transition: 0.75s;
}
.carousel__slide.carousel__slide--active img {
  opacity: 1;
}
</style>