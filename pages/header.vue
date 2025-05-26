<template>
  <div class="flex flex-col gap-1 p-3 my-10 w-auto">

    <CardBaseCodeCards
        title="Base Header Css wth Burger"
        :code="Code1"
    >
      <HeaderBaseNavBurger/>
    </CardBaseCodeCards>

    <CardBaseCodeCards
        title="Base Header Tailwind wth burger"
        :code="Code2"
    >
      <HeaderBaseNavBurgerTwdNuxt/>
    </CardBaseCodeCards>

    <CardBaseCodeCards
        title="Base Header Tailwind wth burger"
        :code="Code3"
    >
      <HeaderAppHeader/>
    </CardBaseCodeCards>

  </div>
</template>

<script setup>

import BaseContactStyleLite from "~/components/contact-form/BaseContactStyleLite.vue";

const Code1 = `<template>
    <div class="app-container">
      <nav>

        <div class="desktop-menu">
          <router-link to="/" class="nav-link">Accueil</router-link>
          <router-link to="/hobby" class="nav-link">Passion</router-link>
          <router-link to="/formation" class="nav-link">Formation</router-link>
          <router-link to="/experience" class="nav-link">Experience</router-link>
          <router-link to="/projet" class="nav-link">Projet</router-link>
          <router-link to="/contact" class="nav-link">Contact</router-link>
        </div>


        <div class="burger-menu" @click="toggleModal">
          &#9776;

        </div>
      </nav>

      <div class="modal" v-if="isModalOpen" @click.self="toggleModal">
        <div class="modal-content">
          <router-link to="/" class="modal-link" @click="toggleModal">Accueil</router-link>
          <router-link to="/hobby" class="modal-link" @click="toggleModal">Passion</router-link>
          <router-link to="/formation" class="modal-link" @click="toggleModal">Formation</router-link>
          <router-link to="/experience" class="modal-link" @click="toggleModal">Experience</router-link>
          <router-link to="/projet" class="modal-link" @click="toggleModal">Projet</router-link>
          <router-link to="/contact" class="modal-link" @click="toggleModal">Contact</router-link>
        </div>
      </div>
    </div>
</template>

<script setup>
export default {
    data() {
      return {
        isModalOpen: false,
      };
    },
    methods: {
      toggleModal() {
        this.isModalOpen = !this.isModalOpen;
      },
    },
  };

<\/script>
<style scoped>
 body {
    margin: 0;
    padding: 0;
    background-size: contain;
    background-color: black;
    color: white;
  }

  .app-container {

    padding: 20px;
  }


  nav {
    margin-bottom: 20px;
    display: flex;
    justify-content:center;
    align-items: center;
  }

  .nav-link {
    color: white;
    text-decoration: none;
    margin-right: 20px;
    padding: 5px 10px;
  }

  .nav-link:hover {
    text-decoration: none;
    color: rgb(223, 126, 70);
  }

  .router-link-active {
    font-weight: bold;
    border-bottom: 2px solid white;
  }


  .burger-menu {
    display: none;
    font-size: 24px;
    cursor: pointer;
    color: white;
  }


  .modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.8);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;
  }

  .modal-content {
    background: black;
    padding: 20px;
    border-radius: 8px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .modal-link {
    color: white;
    text-decoration: none;
    margin: 10px 0;
    font-size: 18px;
  }

  .modal-link:hover {
    color: rgb(223, 126, 70);
  }

  .desktop-menu {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }


  @media (max-width: 700px) {
    .desktop-menu {
      display: none;
    }

    .burger-menu {
      display: block;
    }
    .app-container {
    padding: 5px;
  }
  #app{
  padding: 5px;
  }

  }
  @media (max-width: 350px) {
    .nav-link {
      margin-right: 10px;
      padding: 5px;
    }

    .modal-link {
      font-size: 16px;
    }

    .modal-content {
      padding: 15px;
    }

    .burger-menu {
      font-size: 20px;
    }
  }
</style>`

const Code2 = `<template>
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
<\/script>
`

const Code3 = `<template>
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

const Code4 = `<template>

</template>

<script setup>

<\/script>
<style scoped>


</style>`
</script>