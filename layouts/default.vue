<template>
  <div class="flex flex-col min-h-screen">
    <LogoBg/>
    <HeaderBaseNavBurgerTwdNuxt/>
    <main class="flex-grow min-h-screen">
      <NuxtPage />
    </main>
    <LibFooterMini/>
  </div>
</template>

<script setup lang="ts">
import EcomerceFooter from "~/components/footer/EcomerceFooter.vue";
import LibFooterMini from "~/components/footer/LibFooterMini.vue";
</script>