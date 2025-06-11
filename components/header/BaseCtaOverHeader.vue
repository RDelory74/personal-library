<script setup lang="ts">
import {Send} from 'lucide-vue-next'
import {PhoneOutgoing} from 'lucide-vue-next'
import {NotebookPen} from 'lucide-vue-next'
import {Map} from 'lucide-vue-next';

</script>

<template>
  <div class="header-cta-band">
    <div class="header-cta-band-contact">
      <div class="header-cta-band-contact-mail">
        <Send color="#ff4444" :size="20"/>
        <a href="mailto:rodolphe.delory74@hotmail.com">rodolphe.delory74@hotmail.com</a>
      </div>
      <div class="header-cta-band-contact-phone">
        <PhoneOutgoing color="#ff4444" :size="20"/>
        <a href="tel:0661392013">Tel: 06 61 39 20 13</a>
      </div>
      <div class="header-cta-band-contact-locator">
        <Map color="#ff4444" :size="20"/>
        <p>Haute Savoie | Savoie | Ain | Geneve</p>
      </div>
    </div>
    <div class="header-cta-band-button-container">
      <NuxtLink to="/contact" class="header-cta-band-button">
        <NotebookPen/>
        Un Projet ?
      </NuxtLink>
    </div>
  </div>
</template>

<style scoped>
.header-cta-band {
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-align: center;
  font-family: 'Inter', sans-serif;
  color: #D2B48C;
  background-color: #24424A;
  height: 50px;
  /* css adapté pour la miniature librairie à adapter*/
  font-size: x-small;
  padding: 0 1%;
  /*css desktop 
  padding 0 5%; 
  */
  /*css pour miniature*/
  width: 100%;
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

.header-cta-band-contact-locator {
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
  /* css original
   padding: 10px 20px;
  font-size: 18px;
  */
  /*pour la miniature a enlever pour desktop*/
  padding: 4px 5px;
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
</style>