<template>
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
</style>
<script setup lang="ts">
import BaseButtonTlwd from "~/components/button/BaseButtonTlwd.vue";
</script>