<script setup lang="ts">
import { Carousel, Slide } from "vue3-carousel";
import { allSliders } from "@/data/slilders";
import "vue3-carousel/dist/carousel.css";
import { ref } from "vue";

const transition = ref(0);
</script>

<template>
  <label for="">transition</label>
  <input type="number" v-model="transition" step="100" />
  <Carousel :autoplay="4000" :itemsToShow="1.5" :wrapAround="true" :transition="transition">
    <Slide v-for="slide in allSliders" :key="slide.id">
      <img :src="slide.src" :alt="`${slide.id}枚目の写真`" />
    </Slide>
  </Carousel>
</template>

<style scoped>
.carousel {
  pointer-events: none !important;
}
.carousel__slide img {
  opacity: 0;
}
.carousel__slide.carousel__slide--active img {
  opacity: 1;
  transition: 0.75s;
}
input {
  margin-bottom: 12px;
}
</style>
