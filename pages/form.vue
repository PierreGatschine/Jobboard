<template>
  <div>
    <Appbar/>
    <div class="m-3 mb-5">
      <Wrapper msg="Formulaire"/>
    </div>
    <div class="m-3">
      <FormProfile/>
    </div>



  </div>
</template>


<script>
import AppBbar from '../components/Appbar.vue'
import Wrapper from '../components/Wrapper.vue'
import FormProfile from '../components/FormProfile.vue'

export default {
  components: {AppBbar, Wrapper, FormProfile},

}
</script>

<style lang="postcss" scoped>
  form {
    @apply laptop:max-w-4xl laptop:grid laptop:grid-cols-2 laptop:gap-2 bg-blue-200 rounded-lg p-3 shadow;
  }

</style>
