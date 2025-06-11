<template>
  <footer class="bg-black text-white px-6 py-10">
    <div class="max-w-7xl mx-auto flex flex-col md:flex-row md:justify-between md:items-start gap-10">
      <div class="flex flex-col md:flex-row gap-10 flex-1">
        <div>
          <h3 class="text-lg font-semibold mb-4">Contact</h3>
          <ul class="space-y-2 text-sm text-gray-300">
            <li>Email : rodolphe.delory74@hotmail.com</li>
            <li>Phone : 06 61 39 20 13</li>
            <li>Location : Annecy, Haute Savoie</li>
          </ul>
        </div>
      </div>
      <div class="flex justify-center md:justify-end md:w-48">
        <img src="/logo-sharpped.png" alt="Logo" class="h-24 object-contain" />
      </div>
    </div>
    <div class="border-t border-[#6DA48F] mt-10 pt-6 text-sm text-[#6DA48F] text-center">
      © {{ new Date().getFullYear() }} LibNuxt. Tous droits réservés.
    </div>
  </footer>
</template>
