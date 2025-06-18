<template>
  <section class="page">
    <div class="mx-auto max-w-6xl grid grid-cols-6 gap-3">
      <div class="col-span-6">
        <carousel />
      </div>
      <div class="col-span-6 md:col-span-2">
        <div class="w-full h-96 bg-cover bg-center" style="background-image: url('/unsplash/nathan-fertig-FBXuXp57eM0-unsplash.jpg');"></div>
      </div>
      <div class="col-span-6 md:col-span-2">
        <div class="w-full h-96 bg-cover bg-center" style="background-image: url('/unsplash/spacejoy-IH7wPsjwomc-unsplash.jpg');"></div>
      </div>
      <div class="col-span-6 md:col-span-2">
        <div class="w-full h-96 bg-cover bg-center" style="background-image: url('/unsplash/kirill-9uH-hM0VwPg-unsplash.jpg');"></div>
      </div>
      <CatalogProductGrid identifier="bowling" />
    </div>
  </section>
</template>

<script setup lang="ts">
import config from './../pocketstore.json'
const { t } = useI18n();
useHead({
  title: t('general.title'),
});
</script>