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

    <CardBaseCodeCards
        title="Cyber Central Mini NavBar"
        :code="Code5"
    >
      <CyberNavBar/>
    </CardBaseCodeCards>

  </div>
</template>

<script setup>

import BaseContactStyleLite from "~/components/contact-form/BaseContactStyleLite.vue";
import AppHeader from "~/components/header/AppHeader.vue";
import CyberNavBar from "~/components/header/CyberNavBar.vue";

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

const Code5 = `<template>
  <div>
    <!-- Desktop Navbar -->
    <nav class="bg-gray-900/95 backdrop-blur-sm border-b border-cyan-400/30 shadow-lg shadow-cyan-400/20 relative z-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
          <!-- Logo -->
          <div class="flex-shrink-0 hidden md:block">
            <img
                src="/logo-sharpped.png"
                alt="Logo"
                class="h-10 w-auto filter drop-shadow-lg drop-shadow-cyan-400/30"
            />
          </div>

          <!-- Desktop Navigation -->
          <div class="hidden md:flex items-center space-x-8">
            <!-- Bouton 1 -->
            <button class="relative px-6 py-2 bg-transparent text-cyan-400 font-medium transition-all duration-300 border border-cyan-400/50 hover:border-cyan-400 hover:text-cyan-300 hover:shadow-lg hover:shadow-cyan-400/25 bg-gradient-to-br from-cyan-400/10 to-cyan-400/5 hover:from-cyan-400/20 hover:to-cyan-400/10" style="clip-path: polygon(0 0, calc(100% - 10px) 0, 100% 100%, 10px 100%);">
              <span class="relative z-10">Accueil</span>
            </button>

            <!-- Bouton 2 -->
            <button class="relative px-6 py-2 bg-transparent text-cyan-400 font-medium transition-all duration-300 border border-cyan-400/50 hover:border-cyan-400 hover:text-cyan-300 hover:shadow-lg hover:shadow-cyan-400/25 bg-gradient-to-br from-cyan-400/10 to-cyan-400/5 hover:from-cyan-400/20 hover:to-cyan-400/10" style="clip-path: polygon(0 0, calc(100% - 10px) 0, 100% 100%, 10px 100%);">
              <span class="relative z-10">Services</span>
            </button>

            <!-- Dropdown -->
            <div class="relative" ref="dropdown">
              <button
                  @click="toggleDropdown"
                  class="relative px-6 py-2 bg-transparent text-cyan-400 font-medium transition-all duration-300 border border-cyan-400/50 hover:border-cyan-400 hover:text-cyan-300 hover:shadow-lg hover:shadow-cyan-400/25 bg-gradient-to-br from-cyan-400/10 to-cyan-400/5 hover:from-cyan-400/20 hover:to-cyan-400/10 flex items-center space-x-2"
                  style="clip-path: polygon(0 0, calc(100% - 10px) 0, 100% 100%, 10px 100%);"
              >
                <span class="relative z-10">Produits</span>
                <Icon
                    :name="dropdownOpen ? 'heroicons:chevron-up' : 'heroicons:chevron-down'"
                    class="w-4 h-4 text-cyan-400 transition-transform duration-200"
                />
              </button>

              <!-- Dropdown Menu -->
              <Transition
                  enter-active-class="transition ease-out duration-200"
                  enter-from-class="opacity-0 translate-y-1"
                  enter-to-class="opacity-100 translate-y-0"
                  leave-active-class="transition ease-in duration-150"
                  leave-from-class="opacity-100 translate-y-0"
                  leave-to-class="opacity-0 translate-y-1"
              >
                <div
                    v-show="dropdownOpen"
                    class="absolute right-0 mt-2 w-48 bg-gray-800/95 backdrop-blur-sm rounded-md shadow-xl border border-cyan-400/30 shadow-cyan-400/10"
                >
                  <div class="py-1">
                    <a href="#" class="flex items-center space-x-3 px-4 py-2 text-sm text-gray-300 hover:text-cyan-400 hover:bg-cyan-400/10 transition-all duration-200">
                      <Icon name="heroicons:cube" class="w-4 h-4" />
                      Produit 1
                    </a>
                    <a href="#" class="flex items-center space-x-3 px-4 py-2 text-sm text-gray-300 hover:text-cyan-400 hover:bg-cyan-400/10 transition-all duration-200">
                      <Icon name="heroicons:cog-6-tooth" class="w-4 h-4" />
                      Produit 2
                    </a>
                    <a href="#" class="flex items-center space-x-3 px-4 py-2 text-sm text-gray-300 hover:text-cyan-400 hover:bg-cyan-400/10 transition-all duration-200">
                      <Icon name="heroicons:rocket-launch" class="w-4 h-4" />
                      Produit 3
                    </a>
                  </div>
                </div>
              </Transition>
            </div>
          </div>

          <!-- Auth Icon Desktop -->
          <div class="hidden md:block">
            <button class="p-2 text-cyan-400 hover:text-cyan-300 transition-all duration-300 hover:bg-cyan-400/10 rounded-lg border border-transparent hover:border-cyan-400/30 hover:shadow-lg hover:shadow-cyan-400/25">
              <Icon name="heroicons:user-circle" class="w-6 h-6" />
            </button>
          </div>

          <!-- Mobile menu button -->
          <div class="md:hidden flex items-center space-x-4">
            <!-- Logo mobile -->
            <img
                src="/logo-sharpped.png"
                alt="Logo"
                class="h-8 w-auto filter drop-shadow-lg drop-shadow-cyan-400/30"
            />
            <!-- Auth mobile -->
            <button class="p-2 text-cyan-400 hover:text-cyan-300 transition-all duration-300 hover:bg-cyan-400/10 rounded-lg border border-transparent hover:border-cyan-400/30 hover:shadow-lg hover:shadow-cyan-400/25">
              <Icon name="heroicons:user-circle" class="w-6 h-6" />
            </button>
          </div>
        </div>
      </div>
    </nav>

    <!-- Sticky Burger Menu Button (Mobile) -->
    <button
        @click="toggleMobileMenu"
        class="md:hidden fixed top-4 left-4 z-50 w-12 h-12 bg-gray-900/95 backdrop-blur-sm rounded-lg border border-cyan-400/50 hover:border-cyan-400 flex flex-col items-center justify-center transition-all duration-300 hover:shadow-lg hover:shadow-cyan-400/25"
        :class="{ 'burger-open': mobileMenuOpen }"
        style="gap: 4px;"
    >
      <span class="block h-0.5 w-6 bg-cyan-400 transition-all duration-300 origin-center burger-line-1" :class="{ 'rotate-45': mobileMenuOpen }" :style="mobileMenuOpen ? 'transform: rotate(45deg) translate(3px, 3px);' : ''"></span>
      <span class="block h-0.5 w-6 bg-cyan-400 transition-all duration-300 origin-center burger-line-2" :class="{ 'opacity-0': mobileMenuOpen }"></span>
      <span class="block h-0.5 w-6 bg-cyan-400 transition-all duration-300 origin-center burger-line-3" :class="{ '-rotate-45': mobileMenuOpen }" :style="mobileMenuOpen ? 'transform: rotate(-45deg) translate(3px, -3px);' : ''"></span>
    </button>

    <!-- Mobile Menu Overlay -->
    <Transition
        enter-active-class="transition-all duration-300 ease-out"
        enter-from-class="opacity-0"
        enter-to-class="opacity-100"
        leave-active-class="transition-all duration-300 ease-in"
        leave-from-class="opacity-100"
        leave-to-class="opacity-0"
    >
      <div
          v-show="mobileMenuOpen"
          class="md:hidden fixed inset-0 z-40 bg-gray-900/98 backdrop-blur-sm"
          @click="closeMobileMenu"
      >
        <div class="flex flex-col items-center justify-center h-full space-y-8">
          <!-- Mobile Navigation -->
          <div class="flex flex-col items-center space-y-6">
            <button class="text-2xl font-medium text-cyan-400 hover:text-cyan-300 transition-all duration-300 hover:scale-105 hover:drop-shadow-lg hover:drop-shadow-cyan-400/30" @click="closeMobileMenu">
              Accueil
            </button>
            <button class="text-2xl font-medium text-cyan-400 hover:text-cyan-300 transition-all duration-300 hover:scale-105 hover:drop-shadow-lg hover:drop-shadow-cyan-400/30" @click="closeMobileMenu">
              Services
            </button>

            <!-- Mobile Dropdown -->
            <div class="flex flex-col items-center">
              <button
                  @click="toggleMobileDropdown"
                  class="text-2xl font-medium text-cyan-400 hover:text-cyan-300 transition-all duration-300 hover:scale-105 hover:drop-shadow-lg hover:drop-shadow-cyan-400/30 flex items-center space-x-2"
              >
                <span>Produits</span>
                <Icon
                    :name="mobileDropdownOpen ? 'heroicons:chevron-up' : 'heroicons:chevron-down'"
                    class="w-4 h-4 text-cyan-400"
                />
              </button>

              <Transition
                  enter-active-class="transition-all duration-200"
                  enter-from-class="opacity-0 -translate-y-2"
                  enter-to-class="opacity-100 translate-y-0"
                  leave-active-class="transition-all duration-200"
                  leave-from-class="opacity-100 translate-y-0"
                  leave-to-class="opacity-0 -translate-y-2"
              >
                <div v-show="mobileDropdownOpen" class="mt-4 flex flex-col items-center space-y-3">
                  <a href="#" class="flex items-center space-x-3 text-lg text-gray-400 hover:text-cyan-400 transition-all duration-200 hover:scale-105 hover:drop-shadow-lg hover:drop-shadow-cyan-400/30" @click="closeMobileMenu">
                    <Icon name="heroicons:cube" class="w-4 h-4" />
                    Produit 1
                  </a>
                  <a href="#" class="flex items-center space-x-3 text-lg text-gray-400 hover:text-cyan-400 transition-all duration-200 hover:scale-105 hover:drop-shadow-lg hover:drop-shadow-cyan-400/30" @click="closeMobileMenu">
                    <Icon name="heroicons:cog-6-tooth" class="w-4 h-4" />
                    Produit 2
                  </a>
                  <a href="#" class="flex items-center space-x-3 text-lg text-gray-400 hover:text-cyan-400 transition-all duration-200 hover:scale-105 hover:drop-shadow-lg hover:drop-shadow-cyan-400/30" @click="closeMobileMenu">
                    <Icon name="heroicons:rocket-launch" class="w-4 h-4" />
                    Produit 3
                  </a>
                </div>
              </Transition>
            </div>
          </div>
        </div>
      </div>
    </Transition>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const dropdownOpen = ref(false)
const mobileMenuOpen = ref(false)
const mobileDropdownOpen = ref(false)
const dropdown = ref(null)

const toggleDropdown = () => {
  dropdownOpen.value = !dropdownOpen.value
}

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
  if (mobileMenuOpen.value) {
    mobileDropdownOpen.value = false
  }
}

const toggleMobileDropdown = () => {
  mobileDropdownOpen.value = !mobileDropdownOpen.value
}

const closeMobileMenu = () => {
  mobileMenuOpen.value = false
  mobileDropdownOpen.value = false
}

// Close dropdown when clicking outside
const handleClickOutside = (event) => {
  if (dropdown.value && !dropdown.value.contains(event.target)) {
    dropdownOpen.value = false
  }
}

onMounted(() => {
  document.addEventListener('click', handleClickOutside)
})

onUnmounted(() => {
  document.removeEventListener('click', handleClickOutside)
})
<\/script>`
</script>