<template>
  <div ref="dropdownRef" class="relative inline-block text-left">
    <button
        @click="toggle"
        class="bg-gray-800 text-white font-medium px-4 py-2 rounded-md hover:bg-gray-700 transition"
    >
      ☰ Catégories
    </button>

    <transition
        enter-active-class="transition-opacity duration-200"
        enter-from-class="opacity-0"
        leave-active-class="transition-opacity duration-200"
        leave-to-class="opacity-0"
    >
      <div
          v-if="isOpen"
          class="absolute right-0 mt-2 w-48 rounded-md shadow-lg bg-white border z-40"
      >
        <ul class="py-2 text-sm text-gray-700">
          <li
              v-for="item in items"
              :key="item"
              @click="selectItem(item)"
              class="px-4 py-2 hover:bg-gray-100 cursor-pointer"
          >
            {{ item }}
          </li>
        </ul>
      </div>
    </transition>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const isOpen = ref(false)
const toggle = () => (isOpen.value = !isOpen.value)

const items = ['Vêtements', 'Chaussures', 'Accessoires', 'Promos']

const selectItem = (item) => {
  console.log('Sélectionné :', item)
  isOpen.value = false
}

//gestion clik en dehors
const dropdownRef = ref(null)

const handleClickOutside = (event) => {
  if (dropdownRef.value && !dropdownRef.value.contains(event.target)) {
    isOpen.value = false
  }
}

onMounted(() => {
  document.addEventListener('click', handleClickOutside)
})

onBeforeUnmount(() => {
  document.removeEventListener('click', handleClickOutside)
})
</script>
