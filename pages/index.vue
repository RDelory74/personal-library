<template>

  <CardBaseCardImgTextRowCol/>
  <CardBaseStaticCardCode
      title="Lucide for Icon"
      text=" Install Lucide for Vue"
      :code="Code1"
      :reverse="true"
  />
  <CardBaseStaticCardCode
      title="Better use Tailwind"
      text="Install Tailwind for Nuxt"
      :code="Code2"
      :reverse="false"
  />
  <CardBaseStaticCardCode
      title="Configure Tailwind"
      text="Add the @tailwindcss/vite plugin to your Nuxt configuration as a Vite plugin."
      :code="Code3"
      :reverse="false"
  />
  <CardBaseStaticCardCode
      title="Import Tailwind CSS"
      text="Create an ./assets/css/main.css file and add an @import that imports Tailwind CSS."
      :code="Code4"
      :reverse="false"
  />
</template>

<script setup>


const Code1 =
    `npm install lucide-vue-next`
const Code2 =
    `npm install tailwindcss @tailwindcss/vite`
const Code3 =
    `import tailwindcss from "@tailwindcss/vite";
export default defineNuxtConfig({
  compatibilityDate: "2024-11-01",
  devtools: { enabled: true },
  vite: {
    plugins: [
      tailwindcss(),
    ],
  },
});`
const Code4 =
    `@import "tailwindcss";`
</script>