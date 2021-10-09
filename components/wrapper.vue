<template>
    <div class="flex justify-center sm:flex-wrap pt-8 sm:pt-0 text-6xl font-bold text-blue-600">toto<span class="text-blue-500">{{ msg }}</span></div>

</template>

<script>
export default {
    props:{
      msg: String,
    }
}
</script>

<style lang="postcss" scoped>

</style>
