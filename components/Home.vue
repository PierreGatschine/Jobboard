<template>
    <div class="wrapper">
      <div class="title">
        toto<span class="text-blue-500">Offres</span>
      </div>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="postcss" scoped>
  .wrapper {
    @apply min-h-screen flex-col justify-center items-center text-center p-2.5 mx-auto bg-gray-100 ;
  }
  .card {
    @apply max-w-md mx-auto bg-white rounded-xl shadow-md overflow-hidden;

  }
  .title {
      @apply flex flex-wrap  justify-start text-8xl font-bold text-blue-600;
    }


</style>
