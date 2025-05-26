<template>
  <div class="flex flex-col justify-center items-center bg-white/10 rounded border border-[#6DA48F] shadow-inner shadow-white/10 p-4 mx-2 flex-1">
    <!-- Section haute pour le titre -->
    <div class="w-full text-center mb-4">
      <h3 v-if="title" class="text-lg font-semibold text-white">{{ title }}</h3>
    </div>

    <!-- Section milieu pour le slot -->
    <div class="w-full h-1/3 flex flex-col justify-center items-center mb-4">
      <slot />
    </div>

    <!-- Section basse pour le bouton et le code -->
    <div class="w-full">
      <!-- Toggle pour afficher/masquer le code -->
      <div class="flex justify-center">
        <button
            @click="showCode = !showCode"
            class="mb-3 px-3 py-1 bg-[#6DA48F] text-black rounded text-sm hover:bg-[#5a8c7a] transition-colors"
        >
          {{ showCode ? 'Hide code' : 'Show code' }}
        </button>
      </div>

      <!-- Encadré du code -->
      <div v-if="showCode" class="w-full max-w-full">
        <pre class="bg-gray-900 text-green-400 p-4 rounded text-xs overflow-x-auto border border-gray-700 max-h-64 overflow-y-auto"><code>{{ code }}</code></pre>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const props = defineProps({
  title: {
    type: String,
    default: ''
  },
  code: {
    type: String,
    default: ''
  }
})

const showCode = ref(false)
</script>