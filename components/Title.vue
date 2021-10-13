<template>
  <div>
    <div class="flex justify-start mobile:justify-center mx-auto mT-5 flex-wrap pt-8 mobile:pt-4 text-3xl font-bold text-blue-600">toto<span class="text-blue-500 pl-3">{{ msg }}</span></div>
  </div>
</template>

<script>
export default {
  name: 'Title',
  props: {
    msg: String,
  }
}
</script>

<style>

</style>
