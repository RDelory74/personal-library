<template>
  <footer class="bg-black text-white text-center px-4 pt-4 pb-0 font-inter">
    <div class="flex flex-col lg:flex-row justify-between text-xl gap-6 lg:gap-4">

      <div class="flex-1 px-4 flex flex-col">
        <h4 class="text-xl mb-2">Infos</h4>
        <div class="flex flex-col items-center bg-white/10 rounded border border-[#6DA48F] shadow-inner shadow-white/10 p-4 flex-1">
          <NuxtLink to="/">
            <img class="w-24 h-24 rounded-2xl" src="/logo-test-removebg-preview.png" alt="Logo" />
          </NuxtLink>
          <p class="text-lg leading-loose">
            R.Delory<br />
            Annecy
          </p>
          <div class="flex flex-col items-center gap-2 mt-2">
            <a href="tel:0661392013" class="hover:underline">Tel: 06 61 9 20 13</a>
            <a href="mailto:rodolphe.delory74@hotmail.com" class="hover:underline">rodolphe.delory74@hotmail.com</a>
          </div>
        </div>
      </div>

      <div class="flex-1 px-4 flex flex-col">
        <h4 class="text-xl mb-2">Quick tooch</h4>
        <div class="flex-1">
          <ContactFormBaseContactFormLite />
        </div>
      </div>

      <div class="flex-1 px-4 flex flex-col">
        <h4 class="text-xl mb-2">Location</h4>
        <div class="flex flex-col items-center bg-white/10 rounded border border-[#6DA48F] shadow-inner shadow-white/10 p-4 flex-1">
          <p class="text-sm mb-2">
            Savoie<br />
            Haute-Savoie<br />
            Ain
          </p>
          <div class="mb-2 flex-1 flex items-center">
            <iframe
                class="rounded border border-white/20 w-[300px] max-w-full h-[250px]"
                src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d79466.86673854114!2d6.125715272665547!3d45.88285895235016!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x478b8ffa1c0551c9%3A0x42781681620534ba!2sAnnecy!5e1!3m2!1sfr!2sfr!4v1747913175002!5m2!1sfr!2sfr"
                allowfullscreen
                loading="lazy"
                referrerpolicy="no-referrer-when-downgrade"
            ></iframe>
          </div>
        </div>
      </div>
    </div>

    <div class="flex flex-col items-center justify-center mt-6 pb-4">
      <div class="flex flex-col sm:flex-row justify-center sm:justify-around w-full gap-2 text-sm">
        <p>&copy; 2025 R.Delory Library</p>
        <p>
          DesignedBy :
          <a href="https://cv-rod-fr.vercel.app/" target="_blank" rel="noopener noreferrer" class="hover:underline">R.Delory</a>
        </p>
      </div>
    </div>
  </footer>
</template>
