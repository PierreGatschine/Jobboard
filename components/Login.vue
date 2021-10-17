<template>
  <div>
    <form @submit.prevent="sendLogin" class="w-full max-w-sm mx-auto">

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="email">
            email
          </label>
          <input v-model="email" type="text" placeholder="email" name="email" id="email" autocomplete="email" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
          <p class="text-red-500 text-xs italic" v-if="errors.emptyEmail">Please fill out this field.</p>
          <p class="text-red-500 text-xs italic" v-else-if="errors.badValueEmail">Please enter a valid address.</p>
        </div>
      </div>

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="password">
            Password
          </label>
          <input v-model="password" type="password" name="password" id="password"  placeholder="******************" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
          <p class="text-red-500 text-xs italic" v-if="errors.emptyPassword">Please fill out this field.</p>
          <p class="text-red-500 text-xs italic" v-else-if="errors.badValuePassword">Please enter a valid password.</p>
        </div>
      </div>

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
             <!--   @click="sendForm" -->
              <button type="submit" class="inline-flex justify-center mt-3 py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500">
                Login
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
      message: "",

      errors: {
                emptyEmail: false,
                badValueEmail: false,
                emptyPassword: false,
                badValuePassword: false,
            }
    }
  },
  methods: {
           checkEmail(email) {
            let re = /^(([^<>()[]\.,;:s@]+(.[^<>()[]\.,;:s@]+)*)|(.+))@(([[0-9]{1,3}.[0-9]{1,3}.[0-9]{1,3}.[0-9]{1,3}])|(([a-zA-Z-0-9]+.)+[a-zA-Z]{2,}))$/;
            return re.test(email);
        },
        checkOnlyLetters(value) {
            let re = /^[a-zA-ZáàâäãåçéèêëíìîïñóòôöõúùûüýÿæœÁÀÂÄÃÅÇÉÈÊËÍÌÎÏÑÓÒÔÖÕÚÙÛÜÝŸÆŒ]{2,70}$/;
            return re.test(value);
        },
        checkPassword(password) {
            let re = /[a-zA-Z0-9]{8}/;
            return re.test(password);
        },
        test(field, emptyValue, badValue) {
            if (!field) {
                emptyValue = true;
                console.log(emptyValue)
                return emptyValue;
            } else {
                emptyValue = false; //drop error message if user correct the answer
            }

            if (!this.checkOnlyLetters(field)) {
                badValue = true;
                return badValue
            } else {
                badValue = false; //drop error message if user correct the answer
            }
            console.log(field, emptyValue, badValue)
        },
        isFormError() {

            if (!this.email) {
                this.errors.emptyEmail = true;
            } else {
                this.errors.emptyEmail = false; //drop error message if user correct the answer
            }
            if (!this.checkEmail(this.email)) {
                this.errors.badValueEmail = true;
            } else {
                this.errors.badValueEmail = false; //drop error message if user correct the answer
            }


            if (!this.password) {
                this.errors.emptyPassword = true;
            } else {
                this.errors.emptyPassword = false; //drop error message if user correct the answer
            }
            if (!this.checkPassword(this.password)) {
                this.errors.badValuePassword = true;
            } else {
                this.errors.badValuePassword = false;
            }
            if (
                this.errors.emptyEmail ||
                this.errors.badValueEmail ||
                this.errors.emptyPassword ||
                this.errors.badValuePassword
            ) {
                console.log("erreur dans le login");
                return true;
            }
            return false;
      },

    async sendLogin() {
      const jwt = localStorage.getItem("jwt")
      let res = await this.$axios.$post('http://localhost:3001/api/admin', {
         email: this.email,
         password: this.password,
      })
        .then(
            res => {
              console.log('toto', res);
              localStorage.setItem("jwt", res.data.token)
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
    @apply laptop:grid laptop:grid-cols-1 laptop:gap-3 bg-blue-200 rounded-lg p-3 mx-auto;
  }
</style>
