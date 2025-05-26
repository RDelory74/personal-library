<template>
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
</script>