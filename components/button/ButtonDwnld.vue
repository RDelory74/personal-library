<template>
  <div>
    <a
        :href="cvPath"
        download
        class="inline-block bg-orange-500 hover:bg-red-500 text-white no-underline px-5 py-2.5 rounded text-base transition-colors duration-300 ease-in-out"
    >
      Download Button
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
</script>
  

