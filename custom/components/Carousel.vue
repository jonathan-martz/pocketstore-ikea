<template>
  <div class="carousel w-full">
    <div v-if="slide == 1" class="carousel-item relative w-full">
      <div
        style="
          background-image: url('/unsplash/aranprime-KbytCpI1i5I-unsplash.jpg');
        "
        class="w-full h-96 bg-cover bg-center"
      />
      <div
        class="absolute left-5 right-5 top-1/2 flex -translate-y-1/2 transform justify-between"
      >
        <button @click="slide = 2" class="btn">
          <FontAwesomeIcon :icon="faChevronLeft" />
        </button>
        <button @click="slide = 2" class="btn">
          <FontAwesomeIcon :icon="faChevronRight" />
        </button>
      </div>
    </div>
    <div v-if="slide == 2" class="carousel-item relative w-full">
      <div
        style="
          background-image: url('/unsplash/nathan-fertig-FBXuXp57eM0-unsplash.jpg');
        "
        class="w-full h-96 bg-cover bg-center"
      />
      <div
        class="absolute left-5 right-5 top-1/2 flex -translate-y-1/2 transform justify-between"
      >
        <button @click="slide = 1" class="btn">
          <FontAwesomeIcon :icon="faChevronLeft" />
        </button>
        <button @click="slide = 1" class="btn">
          <FontAwesomeIcon :icon="faChevronRight" />
        </button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import {
  faChevronLeft,
  faChevronRight,
} from "@fortawesome/free-solid-svg-icons";

const slide = ref(1);
</script>