<template>
  <section class="page min-h-screen" data-theme="light">
    <header>
      <Header />
    </header>
    <main class="mx-auto max-w-6xl min-h-screen px-3 xl:px-0">
      <Messages />
      <Breadcrumb />
      <CookieBanner />
      <BackToTop />
      <slot />
    </main>
    <footer>
      <Footer />
    </footer>
  </section>
</template>
<script setup lang="ts">
import "../main.css";
import Footer from "~/components/Footer.vue";
import Header from "~/components/Header.vue";
</script>

<style scoped>
.page {
  background-color: hsl(34, 53%, 82%);
  background-image: repeating-linear-gradient(
      45deg,
      transparent 5px,
      hsla(197, 62%, 11%, 0.5) 5px,
      hsla(197, 62%, 11%, 0.5) 10px,
      hsla(5, 53%, 63%, 0) 10px,
      hsla(5, 53%, 63%, 0) 35px,
      hsla(5, 53%, 63%, 0.5) 35px,
      hsla(5, 53%, 63%, 0.5) 40px,
      hsla(197, 62%, 11%, 0.5) 40px,
      hsla(197, 62%, 11%, 0.5) 50px,
      hsla(197, 62%, 11%, 0) 50px,
      hsla(197, 62%, 11%, 0) 60px,
      hsla(5, 53%, 63%, 0.5) 60px,
      hsla(5, 53%, 63%, 0.5) 70px,
      hsla(35, 91%, 65%, 0.5) 70px,
      hsla(35, 91%, 65%, 0.5) 80px,
      hsla(35, 91%, 65%, 0) 80px,
      hsla(35, 91%, 65%, 0) 90px,
      hsla(5, 53%, 63%, 0.5) 90px,
      hsla(5, 53%, 63%, 0.5) 110px,
      hsla(5, 53%, 63%, 0) 110px,
      hsla(5, 53%, 63%, 0) 120px,
      hsla(197, 62%, 11%, 0.5) 120px,
      hsla(197, 62%, 11%, 0.5) 140px
    ),
    repeating-linear-gradient(
      135deg,
      transparent 5px,
      hsla(197, 62%, 11%, 0.5) 5px,
      hsla(197, 62%, 11%, 0.5) 10px,
      hsla(5, 53%, 63%, 0) 10px,
      hsla(5, 53%, 63%, 0) 35px,
      hsla(5, 53%, 63%, 0.5) 35px,
      hsla(5, 53%, 63%, 0.5) 40px,
      hsla(197, 62%, 11%, 0.5) 40px,
      hsla(197, 62%, 11%, 0.5) 50px,
      hsla(197, 62%, 11%, 0) 50px,
      hsla(197, 62%, 11%, 0) 60px,
      hsla(5, 53%, 63%, 0.5) 60px,
      hsla(5, 53%, 63%, 0.5) 70px,
      hsla(35, 91%, 65%, 0.5) 70px,
      hsla(35, 91%, 65%, 0.5) 80px,
      hsla(35, 91%, 65%, 0) 80px,
      hsla(35, 91%, 65%, 0) 90px,
      hsla(5, 53%, 63%, 0.5) 90px,
      hsla(5, 53%, 63%, 0.5) 110px,
      hsla(5, 53%, 63%, 0) 110px,
      hsla(5, 53%, 63%, 0) 140px,
      hsla(197, 62%, 11%, 0.5) 140px,
      hsla(197, 62%, 11%, 0.5) 160px
    );
}
</style>

