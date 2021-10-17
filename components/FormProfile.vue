<template>
  <div>
    <form @submit.prevent="sendForm" class="max-w-sm mx-auto">
      <div class="flex flex-wrap mt-6 mb-6">
        <div class="w-full px-3">
          <fieldset>
                  <div>
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2">genre</label>
                  </div>
                  <div class="flex  mt-4 space-x-4">
                    <div class="flex items-center">
                      <input v-model="genre" value="male" id="genre_male" name="genre" type="radio" class="focus:ring-indigo-500 h-4 w-4 text-indigo-600 border-gray-300" />
                      <label for="genre_male" class="ml-3 block text-sm font-medium text-gray-700">
                        Mr
                      </label>
                    </div>
                    <div class="flex items-center">
                      <input v-model="genre" value="female" id="genre_female" name="genre" type="radio" class="focus:ring-indigo-500 h-4 w-4 text-indigo-600 border-gray-300" />
                      <label for="genre_female" class="ml-3 block text-sm font-medium text-gray-700">
                        Miss
                      </label>
                    </div>
                    <div class="flex items-center">
                      <input v-model="genre" value="other" id="genre_other" name="genre" type="radio" class="focus:ring-indigo-500 h-4 w-4 text-indigo-600 border-gray-300" />
                      <label for="genre_other" class="ml-3 block text-sm font-medium text-gray-700">
                        other
                      </label>
                    </div>
                  </div>
          </fieldset>
        </div>
      </div>

      <div class="flex flex-wrap laptop:mt-6 mb-6">
        <div class="w-full la  px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="first_name">
            First-naame
          </label>
          <input v-model="first_name" type="text" placeholder="Jane" name="first_name" id="first_name" autocomplete="first_name" class="appearance-none block w-full bg-gray-100 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white">
          <p class="text-red-500 text-xs italic" v-if="errors.emptyContent">Please fill out this field.</p>
        </div>
      </div>
      <div class="flex flex-wrap laptop:mt-6 mb-6">
        <div class="w-full la  px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="last_name">
            Last-name
          </label>
          <input v-model="last_name" type="text" placeholder="Doe" name="last_name" id="last_name" autocomplete="last_name" class="appearance-none block w-full bg-gray-100 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white">
          <p class="text-red-500 text-xs italic" v-if="errors.emptyContent">Please fill out this field.</p>
        </div>
      </div>

      <div class="flex  flex-wrap mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="password">
            Password
          </label>
          <input v-model="password" type="password" name="password" id="password"  placeholder="******************" class="appearance-none block w-full bg-gray-100 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
          <p class="text-gray-600 text-xs italic">Make it as long and as crazy as you'd like</p>
        </div>
      </div>

      <div class="flex flex-wrap mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="email">
            email
          </label>
          <input v-model="email" type="text" placeholder="email" name="email" id="email" autocomplete="email" class="appearance-none block w-full bg-gray-100 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">

        </div>
      </div>

      <div class="flex flex-wrap mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="phone">
            phone
          </label>
          <!-- <span class="inline-flex rounded-l-md py-3 px-4 mb-3 leading-tight focus:outline-none border-gray-300 bg-gray-50 text-gray-500 text-sm">
                      +33
          </span> -->
          <input v-model="phone" type="text" name="phone" id="phone" placeholder="+33 6 XX XX XX XX" class="appearance-none block w-full bg-gray-100 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">

        </div>
      </div>

      <div class="flex flex-wrap mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="address">
            address
          </label>
          <input v-model="address" type="text" name="address" id="address" placeholder="address" class="appearance-none block w-full bg-gray-100 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
        </div>
      </div>

      <div class="flex flex-wrap mb-6">
        <div class="w-full px-3">
            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="city">
              City
            </label>
            <input v-model="city" type="text" name="city" placeholder="Albuquerque" id="city" class="appearance-none block w-full bg-gray-100 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
        </div>
      </div>

      <div class="flex flex-wrap mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="website">
            website
          </label>
          <input v-model="website" type="text" name="website" id="website" placeholder="https://www.google.fr/" class="appearance-none block w-full bg-gray-100 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
        </div>
      </div>
      <div class="flex flex-wrap mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="city">
            CV
          </label>
            <div class="mt-1 flex justify-center px-6 pt-5 pb-6 border-2 border-gray-200 border-dashed rounded-md">
              <div class="space-y-1 text-center">
                <svg class="mx-auto h-12 w-12 text-gray-200" stroke="currentColor" fill="none" viewBox="0 0 48 48" aria-hidden="true">
                  <path d="M28 8H12a4 4 0 00-4 4v20m32-12v8m0 0v8a4 4 0 01-4 4H12a4 4 0 01-4-4v-4m32-4l-3.172-3.172a4 4 0 00-5.656 0L28 28M8 32l9.172-9.172a4 4 0 015.656 0L28 28m0 0l4 4m4-24h8m-4-4v8m-12 4h.02" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
                </svg>
                <div class="flex text-sm text-gray-600">
                  <label for="file_upload" class="relative cursor-pointer bg-blue-200 rounded-md font-medium text-indigo-600 hover:text-indigo-500 focus-within:outline-none focus-within:ring-2 focus-within:ring-offset-2 focus-within:ring-indigo-500">
                    <span>Upload a file</span>
                    <input id="file_upload" name="file_upload" type="file" class="sr-only" />
                  </label>
                  <p class="pl-1">or drag and drop</p>
                </div>
                <p class="text-xs text-gray-500">
                  PNG, JPG, GIF up to 10MB
                </p>
              </div>
            </div>
        </div>
      </div>

      <div class="flex laptop:grid laptop:grid-cols-3 laptop:place-self-center flex-wrap mb-6">
        <div class="w-full laptop:col-start-2   px-3">
             <!--   @click="sendForm" -->
              <button type="submit" class="mt-3 laptop:place-self-center py-2 px-4 laptop:py-4 laptop:px-17 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500">
                Save

              </button>
              <span v-if="msg != 'err'" class="text-green-600 text-xs italic">{{ message }}</span>
              <span v-if="msg === 'err'" class="text-red-500 text-xs italic">{{ message }}</span>
        </div>
      </div>
      <div class="flex laptop:grid laptop:grid-cols-3 laptop:place-self-center flex-wrap mb-6">
        <div class="w-full laptop:col-start-2   px-3">
              <span v-if="msg != 'err'" class="text-green-600 text-xs italic">{{ message }}</span>
              <span v-if="msg === 'err'" class="text-red-500 text-xs italic">{{ message }}</span>
        </div>
      </div>
    </form>
  </div>
</template>

<script>

export default {
  name: 'formProfile',
  data() {
    return {
        errors: {
                  emptyContent: false
        },
       /*  valid: true, */


          genre:"",
          first_name:"",
          last_name:"",
          password:"",
          email:"",
          phone_code: "",
          address:"",
          city:"",
          website:"",
          /* file_upload:"" */

        msg: false,
        message:"",
  }
},
  methods: {
    async sendForm() {

      const res = await this.$axios.$post('http://localhost:3001/api/peoples/signup', {
         genre: this.genre,
         password: this.password,
         first_name: this.first_name,
         last_name: this.last_name,
         email: this.email,
         phone_code: this.phone,
         address: this.address,
         city: this.city,
         website: this.website,
         /* picture: this.picture */

      })
         .then(
            res => {
              console.log('toto', res);
              this.message = 'Vos informations personnelles ont été enregistrées !';
              this.msg = true;
            }
        ).catch(
            err => {
              console.log('titi', err);
              this.message = err;
            }
        );


    },
    /* e.preventDefault; */
    /* async sendForm() {
      this.dataForms = JSON.stringify(this.dataForm)
      console.log("C'est parti !");
        const form  = await this.$axios.$post('http://localhost:3001/peoples', this.dataForms);
        console.log("message:", form);
    }, */

  },
  /* mounted() {
      this.sendForm();
      } */

}
</script>

<style lang="postcss" scoped>
  form {
    @apply laptop:max-w-4xl laptop:grid laptop:grid-cols-3 laptop:gap-3 bg-blue-200 rounded-lg p-3;
  }

</style>
