<template>
  <div>
    <!-- Desktop Navbar -->
    <nav class="bg-gray-900/95 backdrop-blur-sm border-b border-cyan-400/30 shadow-lg shadow-cyan-400/20 relative z-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16 gap-3">
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
</script>