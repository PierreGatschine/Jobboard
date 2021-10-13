<template>
  <div>
    <form @submit.prevent="handleSubmit" class="w-full max-w-sm mx-auto">

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="email">
            email
          </label>
          <input v-model="email" type="text" placeholder="email" name="email" id="email" autocomplete="email" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">

        </div>
      </div>

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="password">
            Password
          </label>
          <input v-model="password" type="password" name="password" id="password"  placeholder="******************" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
          <p class="text-gray-600 text-xs italic">Make it as long and as crazy as you'd like</p>
        </div>
      </div>

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
             <!--   @click="sendForm" -->
              <button type="submit" class="inline-flex justify-center mt-3 py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500">
                Save
              </button>
              <p class="mt-3">
                <span v-if="msg != 'err'" class="text-green-600 text-xs italic">{{ message }}</span>
                <span v-else class="text-red-500 text-xs italic">{{ message }}</span>
              </p>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'login',
  data(){
    return {

      email: "",
      password: "",

      msg: false,
      message: ""
    }
  },
  methods: {
    async handleSubmit() {
      let res = await this.$axios.$post('http://localhost:3001/api/admin', {
         email: this.email,
         password: this.password,
      })
        .then(
            res => {
              console.log('toto', res);
              this.message = 'Votre compte est créé';
              this.msg = true;
            }
        ).catch(
            err => {
              console.log('titi', err);
              this.message = err;
              this.msg = true;
            }
        );

    }

  },
  /* mounted() {
    this.handleSubmit();
  } */
}
</script>

<style lang="postcss" scoped>
  form {
    @apply bg-white rounded-lg p-3 mx-auto;
  }
</style>
