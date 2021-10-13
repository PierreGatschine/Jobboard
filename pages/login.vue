<template>
  <div>
    <Appbar/>
    <div class="m-3 mb-5">
      <Wrapper msg="Connexion"/>
      <div class="mt-5">
            <div class="w-full max-w-sm mx-auto bg-gray-100 shadow  rounded-lg p-3">
              <div class="flex flex-wrap -mx-3 mb-2">

                  <p class="text-gray-600 text-ms font-bold pl-6 mr-4" v-if="mode == 'login'">LOGIN</p>
                  <p class="text-gray-600 text-ms font-bold pl-6 mr-4" v-else>REGISTER</p>
                  <p class="text-gray-600 text-ms italic" v-if="mode == 'login'"><span class="text-blue-600 text-xs " @click="switchToCreateAccount()">Create an account</span></p>
                  <p class="text-gray-600 text-ms italic" v-else><span class="text-blue-600 text-xs " @click="switchToCreateAccount()">Connexion an account</span></p>
              </div>
              <Login v-if=" mode == 'login'" />
              <Register v-else/>
            </div>

      </div>
    </div>

  </div>
</template>

<script>
import Register from '../components/Register.vue'
import Login from '../components/Login.vue'
import Wrapper from '../components/Wrapper.vue'
export default {
  components: { Wrapper, Register, Login },
  data() {
    return {
      mode: 'login'
    }
  },
  methods: {
    switchToCreateAccount() {
      this.mode = 'create';
    },
    switchToLogin() {
      this.mode = 'login';
    },
  },

  }

</script>

<style lang="postcss" scoped>

</style>
