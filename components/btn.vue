<template>
  <div>

      <button class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
          <NuxtLink to="/form">{{ msg }}</NuxtLink>
      </button>

  </div>
</template>

<script>
export default {
  name: 'Btn',
  props: {
    msg: String,
  }

}
</script>

<style>

</style>
