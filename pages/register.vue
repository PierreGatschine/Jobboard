<template>
  <div>
    <Appbar/>
      <div class="m-3 mb-5">
        <Wrapper msg="Register"/>
        <div class="mt-5">
          <Register />
        </div>
      </div>
  </div>
</template>

<script>
import Register from '../components/Register.vue'
import Wrapper from '../components/Wrapper.vue'

export default {
   components: { Wrapper, Register },
  data() {
    return {
      mode: 'register'
    }
  }
}
</script>

<style>

</style>
