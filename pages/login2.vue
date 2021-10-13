<template>
  <div>
    <Appbar/>
    <div class="m-3 mb-5">
      <Wrapper msg="Login"/>
      <div class="mt-5">
        <UserAuthForm buttonText="Login" :subbmitForm="loginUser" />
      </div>
    </div>
  </div>
</template>

<script>
import UserAuthForm from '../components/UserAuthForm.vue'
import Wrapper from '../components/Wrapper.vue'
export default {
  components: { Wrapper, UserAuthForm },

  methods: {
    loginUser(logininfo){
      debugger
      console.log('coucou !');
      alert('You pressed a button')
    }
  },

}

</script>

<style lang="postcss" scoped>

</style>
