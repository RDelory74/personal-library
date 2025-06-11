<template>
  <footer class="bg-gradient-to-r from-pink-500 via-purple-500 to-indigo-500 text-white px-6 py-12">
    <div class="max-w-7xl mx-auto flex flex-col md:flex-row md:justify-between gap-10">

      <!-- Infos principales -->
      <div class="flex flex-col md:flex-row gap-10 flex-1">
        <!-- Contact -->
        <div>
          <h3 class="text-xl font-bold mb-4">🌟 Contact</h3>
          <ul class="space-y-2 text-sm">
            <li>Email : magie@licorne.com</li>
            <li>Téléphone : 07 77 77 77 77</li>
            <li>Arc-en-ciel : 42 Rue des Paillettes, Féérie</li>
          </ul>
        </div>

        <!-- Infos -->
        <div>
          <h3 class="text-xl font-bold mb-4">📖 Infos</h3>
          <ul class="space-y-2 text-sm">
            <li><a href="#" class="hover:underline">À propos</a></li>
            <li><a href="#" class="hover:underline">CGV enchantées</a></li>
            <li><a href="#" class="hover:underline">Politique magique</a></li>
          </ul>
        </div>

        <!-- Services -->
        <div>
          <h3 class="text-xl font-bold mb-4">🛍️ Nos services</h3>
          <ul class="space-y-2 text-sm">
            <li><a href="#" class="hover:underline">Livraison astrale</a></li>
            <li><a href="#" class="hover:underline">Retours en nuage</a></li>
            <li><a href="#" class="hover:underline">Support féérique</a></li>
          </ul>
        </div>
      </div>

      <!-- Logo + Réseaux sociaux + Newsletter -->
      <div class="flex flex-col items-center md:items-end space-y-6">
        <!-- Logo -->
        <img src="/logo-sharpped.png" alt="Logo Licorne" class="h-14 object-contain" />

        <!-- Réseaux sociaux -->
        <div class="flex gap-4 text-2xl">
          <a href="#" aria-label="Instagram" class="hover:text-pink-100 transition"><i class="fab fa-instagram"></i></a>
          <a href="#" aria-label="Twitter" class="hover:text-pink-100 transition"><i class="fab fa-twitter"></i></a>
          <a href="#" aria-label="Facebook" class="hover:text-pink-100 transition"><i class="fab fa-facebook"></i></a>
        </div>

        <!-- Newsletter -->
        <form @submit.prevent="subscribe" class="w-full max-w-xs">
          <label for="email" class="block text-sm mb-1">🌈 Abonne-toi à la magie :</label>
          <div class="flex">
            <input
                type="email"
                id="email"
                v-model="email"
                placeholder="ton@email.com"
                class="w-full px-3 py-2 rounded-l-md text-gray-800 placeholder-gray-400 focus:outline-none"
                required
            />
            <button
                type="submit"
                class="bg-white text-pink-600 font-bold px-4 rounded-r-md hover:bg-pink-100 transition"
            >
              Go ✨
            </button>
          </div>
        </form>
      </div>
    </div>

    <!-- Bas de page -->
    <div class="mt-10 border-t border-white/30 pt-6 text-center text-sm text-pink-100">
      © {{ new Date().getFullYear() }} La Boutique des Licornes. Galopons vers demain 🦄
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue'
const email = ref('')

const subscribe = () => {
  console.log(`Inscription newsletter : ${email.value}`)
  email.value = ''
  // ajouter un appel à une API / toasts / feedback
}
</script>
