<template>
  <div class=" p-5">
    <nav class="mb-5 flex justify-center items-center relative">

      <!-- Navigation desktop -->
      <div class="hidden md:flex flex-wrap justify-center space-x-5">
        <NuxtLink
            v-for="(item, index) in navLinks"
            :key="index"
            :to="item.to"
            class=" hover:text-[#6DA48F]"
        >
          {{ item.label }}
        </NuxtLink>
      </div>

      <!-- Menu burger mobile -->
      <div class="md:hidden text-3xl cursor-pointer absolute " @click="toggleModal">
        &#9776;
      </div>
    </nav>

    <!-- Modal mobile -->
    <div
        v-if="isModalOpen"
        class="fixed inset-0 bg-black bg-opacity-80 flex justify-center items-center z-50"
        @click.self="toggleModal"
    >
      <div class="bg-black p-6 rounded-lg flex flex-col items-center space-y-4">
        <NuxtLink
            v-for="(item, index) in navLinks"
            :key="index"
            :to="item.to"
            @click="toggleModal"
            class="py-1 px-2 border-b-2 border-transparent hover:border-white hover:text-orange-400 transition"
        >
          {{ item.label }}
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>

const isModalOpen = ref(false);
const toggleModal = () => {
  isModalOpen.value = !isModalOpen.value;
};

const navLinks = [
  { to: '/', label: 'Home' },
  { to: '/button', label: 'Buttons' },
  { to: '/contact', label: 'Contact' },
  { to: '/footer', label: 'Footer' },
  { to: '/header', label: 'Header' },
  { to: '/cards', label: 'Cards' },
];
</script>

<style scoped>
.nuxt-link:hover {
  color: #6DA48F !important;
}
</style>

