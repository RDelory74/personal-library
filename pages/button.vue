<template>
  <div class="flex flex-wrap gap-1 p-3 my-10">

    <CardBaseCodeCards
        title="Bouton Base Tailwind"
        :code="buttonTlwdCode"
    >
      <ButtonBaseButtonTlwd/>
    </CardBaseCodeCards>

    <CardBaseCodeCards
        title="Button Base Css"
        :code="buttonCssCode"
    >
      <ButtonBaseButtonCss/>
    </CardBaseCodeCards>

    <CardBaseCodeCards
        title="Button Download Tailwind"
        :code="buttonDwnldCode"
    >
      <ButtonDwnld/>
    </CardBaseCodeCards>

  </div>
</template>

<script setup>

const buttonTlwdCode = `<template>
  <NuxtLink
      class="inline-block rounded px-8 py-4 shadow-md font-bold text-lg no-underline transition-transform duration-300"
      :to="to"
      :class="{ 'scale-105': hovering }"
      :style="{
      backgroundColor: hovering ? hoverColor : bgColor,
      color:color
    }"
      @mouseover="hovering = true"
      @mouseleave="hovering = false"
  >
    {{ label }}
  </NuxtLink>
</template>

<script setup>
import { ref } from 'vue'

const props = defineProps({
  label: {
    type: String,
    required: true,
    default: 'Button'
  },
  color:{
    type: String,
    default: 'black'
  },
  bgColor: {
    type: String,
    default: '#a59046'
  },
  hoverColor: {
    type: String,
    default: '#FAECD6'
  },
  to: {
    type: String,
    default: '/'
  }
})

const hovering = ref(false)
<\/script>`

const buttonCssCode = `<template>
   <NuxtLink  class="app-button" :style="{ backgroundColor: bgColor, color: color }" :to="to">
    {{ label }}
  </NuxtLink>
</template>
<script setup>
defineProps({
  label: {
    type: String,
    required: true,
    default: 'Button'
  },
  color:{
    type: String,
    default: 'black'
  },
  bgColor: {
    type: String,
    default: '#FEF0C1'
  },
  hoverColor: {
    type: String,
    default: '#FAECD6'
  },
  to: {
    type: String,
    default: '/'
  }
});
<\/script>
<style scoped>
.app-button {
  border: none;
  border-radius: 5px;
  padding: 1rem 2rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
  font-family: 'Inter', sans-serif;
  font-size: 1.2rem;
  font-weight: bold;
  cursor: pointer;
  text-decoration: none;
  color: #25424C;
  transition: transform 0.5s ease, background-color 0.3s ease;
}

.app-button:hover {
  background-color: v-bind(hoverColor);
  transform: scale(1.05);
}
</style>`

const buttonDwnldCode = `<template>
  <div>
    <a
        :href="cvPath"
        download
        class="inline-block bg-orange-500 hover:bg-red-500 text-white no-underline px-5 py-2.5 rounded text-base transition-colors duration-300 ease-in-out"
    >
      Télécharger mon CV
    </a>
  </div>
</template>

<script setup>
const props = defineProps({
  cvPath: {
    type: String,
    default: "/cv.pdf",
  },
});
<\/script>`
</script>