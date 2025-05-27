<template>
  <div class="flex flex-col gap-2 p-3 my-10 md:mx-50 w-auto">

    <CardBaseCodeCards
        title="Component Name"
        :code="Code1"
    >

    </CardBaseCodeCards>

    <CardBaseCodeCards
        title="Component Name"
        :code="Code2"
    >
      <FooterAppFooterTwdNuxt/>
    </CardBaseCodeCards>

    <CardBaseCodeCards
        title="Component Name"
        :code="Code3"
    >
      <FooterAppFooterTwdNuxt/>
    </CardBaseCodeCards>

    <CardBaseCodeCards
        title="Component Name"
        :code="Code4"
    >
      <FooterAppFooterTwdNuxt/>
    </CardBaseCodeCards>

  </div>
</template>

<script setup>

const Code1 = `<template>

</template>

<script setup>

<\/script>
<style scoped>


</style>`

const Code2 = `<template>

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

</template>

<script setup>

<\/script>
<style scoped>


</style>`
</script>