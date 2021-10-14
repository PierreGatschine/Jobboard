<template>
  <div>
    <div class="flex justify-start mobile:justify-center mx-auto flex-wrap overflow-hidden pt-8 sm:pt-0 text-6xl font-bold text-blue-600">toto<span class="text-blue-500">{{ msg }}</span></div>

  </div>

</template>

<script>
export default {
    name: 'Wrapper',
    props:{
      msg: String,
    }
}
</script>

<style lang="postcss" scoped>

</style>
