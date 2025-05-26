<template>
  <div class="flex flex-col gap-1 p-3 my-10 w-auto">

    <CardBaseCodeCards
        title="Base Footer Css"
        :code="Code1"
    >
      <FooterAppFooter/>
    </CardBaseCodeCards>

    <CardBaseCodeCards
        title="Base Footer Tailwind"
        :code="Code2"
    >
      <FooterAppFooterTwdNuxt/>
    </CardBaseCodeCards>

  </div>
</template>

<script setup>

const Code1 = `<template>
<footer>
    <div class="footer-info">
      <div>
        <h4>Coordonnées</h4>
        <div class="footer-info-container">
          <NuxtLink to="/">
            <img class="logo" src="/logo-sharpped.png" alt="Logo" />
          </NuxtLink>
          <p>
            R.Delory<br />
            Annecy<br />
          </p>
          <div class="footer-info-contact">
            <a href="tel:0661392013">Tel: 06 61 9 20 13</a>
            <a href="mailto:rodolphe.delory74@hotmail.com">rodolphe.delory74@hotmail.com</a>
          </div>
        </div>
      </div>
      <div>
        <h4>Contact Rapide</h4>
        <div>
          <ContactFormBaseContactFormLite/>
        </div>
      </div>
      <div>
        <h4>Situation</h4>
        <div class="localite-container">
          <p>
            Savoie <br />
            Haute-Savoie <br />
            Ain<br />
          </p>
          <div class="footer-map-locator">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d79466.86673854114!2d6.125715272665547!3d45.88285895235016!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x478b8ffa1c0551c9%3A0x42781681620534ba!2sAnnecy!5e1!3m2!1sfr!2sfr!4v1747913175002!5m2!1sfr!2sfr"
              width="300" height="250" style="border: 1px solid rgba(255, 255, 255, 0.2); border-radius: 4px;"
              allowfullscreen
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"></iframe>
          </div>
        </div>
      </div>
    </div>
    <div class="footer-signature">
      <div class="footer-signature-container">
        <p>&copy; 2025 R.Delory Library </p>
        <p>Réalisation :
          <a href="https://cv-rod-fr.vercel.app/" target="_blank" rel="noopener noreferrer">R.Delory </a>
        </p>
      </div>
    </div>

  </footer>
</template>

<script setup>

<\/script>
<style scoped>
/*general behavior*/
footer {
  background-color: black;
  color: white;
  text-align: center;
  padding: 1rem 1rem 0 1rem;
}
h4 {
  font-family: 'Inter', sans-serif;
}

p {
  font-size: 24px;
  line-height: 2;
}


.logo {
  width: 100px;
  height: 100px;
}

.footer-info {
  display: flex;
  justify-content: space-between;
  font-family: 'Inter', sans-serif;
  font-size: 24px;
}

.footer-info>div {
  flex: 1;
  padding: 0 1rem;
  box-sizing: border-box;
}

.footer-info-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 2px;
  border: 1px solid #6DA48F;
  box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.1),
    0 0 0 1px rgba(255, 255, 255, 0.274);
  padding: 10px;
}

.localite-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 2px;
  border: 1px solid #6DA48F;
  box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.1),
    0 0 0 1px rgba(255, 255, 255, 0.274);
}
.footer-map-locator {
  margin-bottom: 10px;
}

.localite-container>p {
  margin: 0;
  font-size: 14px;

}

.footer-info-contact {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 1rem;
}

.footer-info-contact>a {
  color: inherit;
  text-decoration: none;
}


/*signature*/
.footer-signature {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-family: 'Inter', sans-serif;
  color: white;
}



.footer-signature-container {
  display: flex;
  justify-content: space-around;
  gap: 1rem;
  width: 100%;
}

.footer-signature-container>p>a {
  display: inline-block;
  gap: 1rem;
  color: inherit;
  text-decoration: none;
  margin: 0 5px;
}

.footer-signature-container a:hover {
  cursor: pointer;
  text-decoration: underline;
}


.footer-signature-container>p {
  font-size: 14px;
  margin: 0;
}

@media (max-width: 1024px) {
  .footer-info {
    flex-direction: column;
  }

  .localite-container {
    gap: 1%;
  }
}

@media (max-width: 768px) {
  .footer-info {
    flex-direction: column;

  }

  .footer-info>div {
    margin-bottom: 1rem;
  }

  .footer-info p {
    display: flex;
    justify-content: center;
    text-align: center;
  }

}

@media (max-width: 550px) {
  .footer-signature-container {
    display: flex;
    flex-direction: column;

  }
}

@media (max-width: 388px) {
  .footer-map-locator iframe {
    width: 270px;
  }
}

</style>`

const Code2 = `<template>
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

<script setup>

<\/script>
<style scoped>


</style>`

const Code3 =`<template>

</template>

<script setup>

<\/script>
<style scoped>


</style>`

const Code4 = `<template>
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
</script>