<template>
  <div ref="dropdownRef" class="relative inline-block text-left">
    <button
        @click="toggle"
        class="bg-gradient-to-r from-pink-500 via-purple-500 to-indigo-500 text-white font-bold py-2 px-4 rounded-full shadow-xl hover:scale-105 transition-transform"
    >
      🌈 Licorne Menu
    </button>

    <transition
        enter-active-class="transition-opacity duration-200"
        enter-from-class="opacity-0"
        leave-active-class="transition-opacity duration-200"
        leave-to-class="opacity-0"
    >
      <div
          v-if="isOpen"
          class="absolute right-0 mt-2 w-56 rounded-xl shadow-xl bg-white/90 backdrop-blur border border-pink-300 z-50"
      >
        <ul class="py-2 text-sm text-gray-800">
          <li
              v-for="item in items"
              :key="item"
              @click="selectItem(item)"
              class="px-4 py-2 hover:bg-pink-100 hover:text-pink-600 cursor-pointer transition"
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

const items = ['Licorne 1', 'Paillettes', 'Arc-en-ciel', 'Magie ✨']

const selectItem = (item) => {
  console.log('Sélectionné :', item)
  isOpen.value = false
}

// Le clik en dehros
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
