<template>
  <div>
    <div class="m-3 mb-5">
      <NavForm/>
    </div>
    <div class="m-3 mb-5">
      <Wrapper msg="Add Company"/>
    </div>
    <form @submit.prevent="sendForm" class="w-full max-w-sm mx-auto">

      <div class="flex flex-wrap -mx-3 laptop:mt-6 mb-6">
        <div class="w-full la  px-3">
          <label class="block uppercase tracking-wide text-gray-400 text-xs font-bold mb-2" for="name">
            Name
          </label>
          <input v-model="name" type="text" placeholder="Doe" name="name" id="name" autocomplete="name" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white">
          <p class="text-red-500 text-xs italic" v-if="errors.emptyContent">Please fill out this field.</p>
        </div>
      </div>

      <div class="flex flex-wrap -mx-3 laptop:mt-6 mb-6">
        <div class="w-full la  px-3">
          <label class="block uppercase tracking-wide text-gray-400 text-xs font-bold mb-2" for="activies">
            Activies
          </label>
          <input v-model="activies" type="text" placeholder="IT" name="activies" id="activies" autocomplete="activies" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white">
          <p class="text-red-500 text-xs italic" v-if="errors.emptyContent">Please fill out this field.</p>
        </div>
      </div>

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-400 text-xs font-bold mb-2" for="address">
            address
          </label>
          <input v-model="address" type="text" name="address" id="address" placeholder="address" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
        </div>
      </div>

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
            <label class="block uppercase tracking-wide text-gray-400 text-xs font-bold mb-2" for="city">
              City
            </label>
            <input v-model="city" type="text" name="city" placeholder="Albuquerque" id="city" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
        </div>
      </div>

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-400 text-xs font-bold mb-2" for="postal_code">
            postal_code
          </label>
          <input v-model="postal_code" type="text" name="postal_code" id="postal_code" placeholder="13210" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
        </div>
      </div>

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-400 text-xs font-bold mb-2" for="siret">
            Siret
          </label>
          <input v-model="siret" type="text" name="siret" id="siret" placeholder="13210" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
        </div>
      </div>

      <div class="flex  flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-400 text-xs font-bold mb-2" for="password">
            Password
          </label>
          <input v-model="password" type="password" name="password" id="password"  placeholder="******************" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
          <p class="text-gray-600 text-xs italic">Make it as long and as crazy as you'd like</p>
        </div>
      </div>

      <div class="flex  flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-400 text-xs font-bold mb-2" for="number_employes">
            Number employes
          </label>
          <input v-model="number_employes" type="number_employes" name="number_employes" id="password"  placeholder="+50" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
          <p class="text-gray-600 text-xs italic">Make it as long and as crazy as you'd like</p>
        </div>
      </div>

      <div class="flex  flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-400 text-xs font-bold mb-2" for="website">
            Website
          </label>
          <input v-model="website" type="website" name="website" id="website"  placeholder="https://www.google.fr/" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
          <p class="text-gray-600 text-xs italic">Make it as long and as crazy as you'd like</p>
        </div>
      </div>

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-400 text-xs font-bold mb-2" for="phone">
            phone
          </label>
          <!-- <span class="inline-flex rounded-l-md py-3 px-4 mb-3 leading-tight focus:outline-none border-gray-300 bg-gray-50 text-gray-500 text-sm">
                      +33
          </span> -->
          <input v-model="phone" type="text" name="phone" id="phone" placeholder="+33 6 XX XX XX XX" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">

        </div>
      </div>

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-400 text-xs font-bold mb-2" for="email">
            email
          </label>
          <input v-model="email" type="text" placeholder="john.doe@gmail.com" name="email" id="email" autocomplete="email" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
        </div>
      </div>

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-400 text-xs font-bold mb-2" for="contact_name">
            Contact Name
          </label>
          <input v-model="contact_name" type="text" name="contact_name" id="contact_name" placeholder="Doe" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">

        </div>
      </div>

      <div class="flex laptop:grid laptop:grid-cols-3 laptop:place-self-center flex-wrap -mx-3 mb-6">
        <div class="w-full laptop:col-start-2   px-3">
             <!--   @click="sendForm" -->
              <button type="submit" class="mt-3 laptop:place-self-center py-2 px-4 laptop:py-4 laptop:px-17 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500">
                Save

              </button>
              <span v-if="msg != 'err'" class="text-green-600 text-xs italic">{{ message }}</span>
              <span v-else class="text-red-500 text-xs italic">{{ message }}</span>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
import Wrapper from '../components/Wrapper.vue'
import NavForm from '../components/NavForm.vue'
export default {
  components: { Wrapper, NavForm },
   data() {
    return {
        errors: {
                  emptyContent: false
        },
        valid: true,
        name:"",
        activies:"",
        address:"",
        city:"",
        zip:"",
        siret:"",
        password:"",
        number_employes:"",
        website:"",
        phone: "",
        email:"",
        contact_name:"",

        msg: false,
        message:"",
  }
    },
  methods: {
    async sendForm() {

      const res = await this.$axios.$post('http://localhost:3001/api/companies', {
         name: this.name,
         activies: this.activies,
         address: this.address,
         city: this.city,
         postal_code: this.postal_code,
         siret: this.siret,
         password: this.password,
         number_employes: this.number_employes,
         website: this.website,
         phone: this.phone,
         email: this.email,
         contact_name: this.contact_name

      })
         .then(
            res => {
              console.log('toto', res);
              this.message = 'Les informations de la compagnie sont enregistrées !';
              this.msg = true;
            }
        ).catch(
            err => {
              console.log('titi Ayaya !', err);
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

}
</script>

<style>

</style>
