<template>
  <div class="flex flex-col gap-1 p-3 my-10 w-auto">

    <CardBaseCodeCards
        title="Base Cards tailwind"
        :code="Code1"
    >
      <CardBaseCardImgTextRowCol/>
    </CardBaseCodeCards>

    <CardBaseCodeCards
        title="Base Cards info Css"
        :code="Code2"
    >
      <CardBaseCardInfoCss/>
    </CardBaseCodeCards>

    <CardBaseCodeCards
        title="Card 3section head body button with code tailwind"
        :code="Code3"
    >
      <CardBaseCodeCards/>
    </CardBaseCodeCards>

    <CardBaseCodeCards
        title="Component Name"
        :code="Code4"
    >
   <!--insert component here-->
    </CardBaseCodeCards>

  </div>
</template>

<script setup>

const Code1 = `<template>
  <div class="flex flex-col lg:flex-row justify-center items-center min-h-[50vh] p-6 gap-2 text-white text-center lg:text-left">
    <div class="w-full lg:w-1/2 flex justify-center items-center ">
      <Logo />
    </div>
    <div class="w-full lg:w-2/2 px-4 flex items-center justify-center lg:justify-start">
      <p class="max-w-xl">
        This personal library is a curated collection of useful elements and resources gathered from across the web.
        It serves as a central place to store everything that might be helpful for building future digital projects.
        By organizing these assets, I ensure quick access and efficient development whenever inspiration strikes.
      </p>
    </div>
  </div>
</template>

<script setup>

<\/script>
<style scoped>


</style>`

const Code2 = `<template>
  <div class="eco-section">
    <div class="eco-text">
      <h4>Recyclage et Débarras Éco-Responsable</h4>
      <p>Nous nous engageons à réduire l'impact environnemental en recyclant les matériaux récupérés
        et en favorisant la réutilisation</p>
    </div>
    <div>
      <img src="@/public/logo-sharpped.png" alt="eco-image">
    </div>
  </div>
</template>

<script setup>

<\/script>
<style scoped>
h4 {
  font-family: 'Alkatra', sans-serif;
}


.eco-section {
  font-family: 'Inter', sans-serif;
  font-size: 24px;
  background-color: White;
  color: #25424C;
  padding: 5% 20%;
  gap: 3rem;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-around;
  text-align: center;
}

.eco-section img {
  transition: transform 0.5s ease;
}
.eco-section img:hover {
  transform: scale(1.05);
}

.eco-text {
  width: 50%;
}

@media (max-width: 900px) {
  .eco-section {
    padding: 5% 5%;
  }
  .eco-text {
    width: 100%;
  }
}

</style>`

const Code3 =`<template>

  <div class="flex flex-col justify-center items-center bg-white/10 rounded border border-[#6DA48F] shadow-inner shadow-white/10 p-4 mx-2 flex-1">
    <!-- La tête de la carte -->
    <div class="w-full text-center mb-4">
      <h3 v-if="title" class="text-lg font-semibold text-white">{{ title }}</h3>
    </div>
    <!-- Le body de la carte -->
    <div class="w-full h-1/3 flex flex-col justify-center items-center mb-4">
      <slot />
    </div>
    <!-- Le pied de la carte -->
    <div class="w-full">
      <div class="flex justify-center">
        <button
            @click="showCode = !showCode"
            class="mb-3 px-3 py-1 bg-[#6DA48F] text-black rounded text-sm hover:bg-[#5a8c7a] transition-colors"
        >
          {{ showCode ? 'Hide code' : 'Show code' }}
        </button>
      </div>
      <div v-if="showCode" class="w-full max-w-full">
        <pre class="bg-gray-900 text-green-400 p-4 rounded text-xs overflow-x-auto border border-gray-700 max-h-64 overflow-y-auto"><code>{{ code }}</code></pre>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const props = defineProps({
  title: {
    type: String,
    default: ''
  },
  code: {
    type: String,
    default: ''
  }
})

const showCode = ref(false)
<\/script>
<style scoped>


</style>`

const Code4 = `<template>

</template>

<script setup>

<\/script>
<style scoped>


</style>`
</script>