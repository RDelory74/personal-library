<template>
  <div
      class="flex flex-col md:flex-row items-center justify-between gap-6 p-6 bg-white/5 border border-[#6DA48F] my-10 mx-6 lg:mx-60
      transform transition-transform duration-300 hover:scale-101
       rounded-lg shadow-inner shadow-white/10"
      :class="reverse ? 'md:flex-row-reverse' : 'md:flex-row'"
  >
    <!-- Texte -->
    <div class="w-full md:w-1/2 flex flex-col items-center text-center">
      <h3 class="text-2xl font-semibold mb-4 text-white">{{ title }}</h3>
      <p class="text-white/90 leading-relaxed">{{ text }}</p>
    </div>

    <!-- Code + bouton copier -->
    <div class="relative w-full md:w-1/2">
      <button
          @click="copyCode"
          class="absolute top-2 right-2 bg-white/10 border border-white/20 text-white p-2 rounded hover:bg-white/20 transition flex items-center justify-center"
          :title="copied ? 'Copied!' : 'Copy to clipboard'"
      >
        <Copy class="w-4 h-4" />
      </button>

      <div
          class="max-h-[300px] overflow-auto bg-black text-green-400 font-mono text-sm p-4 rounded-lg border border-white/20"
      >
        <pre><code>{{ code }}</code></pre>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { Copy } from 'lucide-vue-next'

const props = defineProps({
  title: String,
  text: String,
  code: String,
  reverse: {
    type: Boolean,
    default: false,
  },
})

const copied = ref(false)

const copyCode = async () => {
  try {
    await navigator.clipboard.writeText(props.code)
    copied.value = true
    setTimeout(() => (copied.value = false), 2000)
  } catch (err) {
    console.error('Copy failed:', err)
  }
}
</script>