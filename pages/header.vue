<template>
  <div class="flex flex-col gap-2 p-3 my-10 lg:mx-5 w-auto">

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
        title="Base Header Css "
        :code="Code3"
    >
      <HeaderAppHeader/>
    </CardBaseCodeCards>

    <CardBaseCodeCards
        title="Call to Action Bar over Header "
        :code="Code4"
    >
      <HeaderBaseCtaOverHeader/>
    </CardBaseCodeCards>

  </div>
</template>

<script setup>

import BaseContactStyleLite from "~/components/contact-form/BaseContactStyleLite.vue";
import AppHeader from "~/components/header/AppHeader.vue";

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
 <header>
    <div class="nav-display">
      <NuxtLink to="/">
        <img
            class="logo"
            src="@/public/logo-sharpped.png"
            alt="Logo"
        />
      </NuxtLink>
      <div class="nav-button">
        <BaseButtonTlwd class="nav-specific-button" label="Accueil" bgColor="#FEF0C1" hoverColor="#A0BDAF" to="/"/>
        <BaseButtonTlwd class="nav-specific-button" label="Services" bgColor="#FEF0C1" hoverColor="#A0BDAF" to="/service"/>
        <BaseButtonTlwd class="nav-specific-button" label="Contact" bgColor="#FEF0C1" hoverColor="#A0BDAF" to="/contact"/>
      </div>
    </div>
  </header>
</template>

<script setup>
import BaseButtonTlwd from "~/components/button/BaseButtonTlwd.vue";
<\/script>
<style scoped>
header {
  background-color: #6DA48F80;
  color: white;
  padding: 1rem;
  width: 100%;
}

.logo {
  height: 5rem;
}

.nav-display {
  display: flex;
  justify-content: space-between;
  align-items: center;

}

.nav-button {
  display: flex;
  justify-content: space-between;
  gap: 2rem;
  margin-right: 2rem;
}

.nav-specific-button:hover {
  background-color: #D2B48C !important;
  opacity: 1 !important;
}

@media (max-width: 850px) {
  .nav-display {
    flex-direction: column;
    gap: 0.5rem;
  }

  .nav-specific-button {
    margin-right: 0;
    padding: 0.7rem 1rem !important;
  }

  .nav-button {
    margin-right: 0;
  }
}

@media (max-width: 440px) {
.nav-button {
    gap: 0.5rem;
  }
}
</style>`

const Code4 = `<template>
  <div class="header-cta-band">
    <div class="header-cta-band-contact">
      <div class="header-cta-band-contact-mail">
        <Send
            color="#ff4444"
            :size="20"
        />
        <a href="mailto:rodolphe.delory74@hotmail.com">rodolphe.delory74@hotmail.com</a>
      </div>
      <div class="header-cta-band-contact-phone">
        <PhoneOutgoing
            color="#ff4444"
            :size="20"
        />
        <a href="tel:0661392013">Tel: 06 61 39 20 13</a>
      </div>
      <div class="header-cta-band-contact-locator">
        <Map
            color="#ff4444"
            :size="20"
        />
        <p>Haute Savoie | Savoie | Ain | Geneve</p>
      </div>
    </div>
    <div class="header-cta-band-button-container">
      <NuxtLink to="/contact" class="header-cta-band-button">
        <NotebookPen />
        Un Projet ?
      </NuxtLink>
    </div>
  </div>
</template>

<script setup>
import {Send} from 'lucide-vue-next'
import {PhoneOutgoing} from 'lucide-vue-next'
import {NotebookPen} from 'lucide-vue-next'
import {Map} from 'lucide-vue-next';

<\/script>
<style scoped>

.header-cta-band {
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-align: center;
  padding: 0 5%;
  font-family: 'Inter', sans-serif;
  color: #D2B48C;
  background-color: #24424A;
  height: 50px;
}

.header-cta-band-contact {
  display: flex;
  justify-content: space-around;
  align-items: center;
  text-align: center;
  gap: 40px;
  padding: 0 10px;
  font-family: 'Inter', sans-serif;
  color: #D2B48C;
}

.header-cta-band-contact-mail {
  display: flex;
  justify-content: space-around;
  align-items: center;
  text-align: center;
  gap: 5px;
  padding: 0 10px;
  font-family: 'Inter', sans-serif;
  color: #D2B48C;
}
.header-cta-band-contact-mail a,
.header-cta-band-contact-phone a {
  color: inherit;
  text-decoration: none;
}

.header-cta-band-contact-phone {
  display: flex;
  justify-content: space-around;
  align-items: center;
  text-align: center;
  gap: 5px;
  padding: 0 10px;
  font-family: 'Inter', sans-serif;
  color: #D2B48C;
}
.header-cta-band-contact-locator{
  display: flex;
  justify-content: space-around;
  align-items: center;
  text-align: center;
  gap: 5px;
  padding: 0 10px;
  font-family: 'Inter', sans-serif;
  color: #D2B48C;
}

.header-cta-band-button-container {
  padding: 0;
}

.header-cta-band-button {
  display: flex;
  justify-content: space-around;
  align-items: center;
  text-align: center;
  gap: 5px;
  text-decoration: none;
  border: none;
  background: #ff4444;
  color: #FEF0C1;
  cursor: pointer;
  transition: transform 0.5s ease, background-color 0.3s ease;
  padding: 10px 20px;
  font-size: 18px;
  border-radius: 2px;
}


.header-cta-band-button:hover {
  background: #ff6666;
  transform: scale(1.05);
}

@media (max-width: 768px) {
  .header-cta-band-contact {
    font-size: 12px;
    gap: 10px;
    padding: 0;
  }
}

@media (max-width: 1110px) {
  .header-cta-band-contact-mail {
    display: none;
  }
  .header-cta-band-button {
   padding: 5px 10px;
 }
}

@media (max-width: 800px) {
  .header-cta-band-contact-locator {
    display: none;
  }
}

</style>`
</script>