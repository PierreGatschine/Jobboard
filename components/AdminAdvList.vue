<template>
  <div>
    <div
      class="
        relative
        flex
        items-top
        justify-center
        bg-gray-700
        sm:items-center
        sm:pt-0
      "
    >
      <div class="max-w-4xl mx-auto mb-20 sm:px-6 lg:px-8">

        <div
          class="
            mt-8
            bg-gray-800
            text-gray-500
            overflow-hidden
            shadow
            rounded-lg
            m-2
            p-6
          "
          v-for="allAdvertisement in allAdvertisements"
          v-bind:key="allAdvertisement"
        >
          <div class="max-w-6xl flex justify-between items-center mx-auto">
            <div class="flex flex-col">
              <h2 class="text-2xl p-2 leading-7 font-semibold">
                {{ allAdvertisement.title }}
              </h2>
              <h3 class="text-xl p-2 leading-7 font-light">
                {{ allAdvertisement.name }}
              </h3>
            </div>
            <div class="flex justify-between items-center">
              <div class="btn ml-1">
              <NuxtLink to="/" class="btn"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 13h6m-3-3v6m-9 1V7a2 2 0 012-2h6l2 2h6a2 2 0 012 2v8a2 2 0 01-2 2H5a2 2 0 01-2-2z" />
                </svg>
              </NuxtLink>
              </div>
              <div class="btn ml-1">
              <NuxtLink to="/admin" class="btn"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z" />
                </svg>
              </NuxtLink>
              </div>
              <div class="btn ml-1">
              <NuxtLink to="/admin" class="btn"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" />
                </svg>
              </NuxtLink>
            </div>
          </div>

          </div>

<!--           <p class="mt-3 text-gray-600">
            <spam class="font-bold">Skills</spam><br />
            {{ item.resume }}
          </p>
          <div v-show="showModal">
            <p class="mt-4 pt-4 text-gray-600">
              <spam class="font-bold">Missions</spam><br />
              {{ item.description }}
            </p>
            <p class="mt-4 pt-4 text-gray-600">
              <spam class="font-bold">City</spam><br />
              {{ item.lieu }}
            </p>
            <p class="mt-4 pt-4 text-gray-600">
              <spam class="font-bold">Salaire annuel</spam><br />
              {{ item.salaire }}
            </p>
          </div>
          <p class="mt-4 pt-4 text-gray-600">
            <spam class="font-bold">Type de contrat</spam><br />
            {{ item.contrat_type }} - {{ item.temps_de_travail }}
          </p>
          <div class="flex justify-between items-center mx-auto">
            <p class="mt-4 pt-4 text-gray-600 border-t border-dashed">
              paru il y a, <spam class="font-thin">{{ item.parution }}</spam>
            </p>
            <div class="displayMoreInfo" @click.stop="showModal = !showModal">
              <button
                class="
                  bg-blue-600
                  hover:bg-blue-700
                  text-gray-50
                  focus:outline-none
                  focus:ring-2 focus:ring-opacity-50
                  rounded-full
                  px-6
                  py-4
                "
              >
                <span class="text-2xl font-semibold">+</span>
              </button>
            </div>
          </div>
          <div class="btn mt-4 mb-3">
            <btn msg="Apply" />
          </div> -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AdminAdvList",
   data() {
    return {
      allAdvertisements: [],
      showModal: false
    };
  },

  methods: {
    /* async asyncData({ params, $axios }) {
      const post = await $axios.$get(`http://localhost:3001/advertisements//${params.id}`)
      return { post } */
    async fetchSomething() {
      const advertisements = await this.$axios.$get(
        "http://localhost:3001/api/advertisements"
      );
      console.log("message:", advertisements);
      this.allAdvertisements = advertisements;
      console.log(allAdvertisements);
    },
    displayMoreInfo() {
      console.log("Toto continu !");
    }
  },

  mounted() {
    /* this.asyncData(); */
    this.fetchSomething();
  }
};
</script>
<style lang="postcss" scoped>
  .btn {
    @apply px-2 font-bold text-blue-500 items-end rounded-lg;
  }
  .btn:hover {
    @apply bg-blue-600 text-gray-50 py-2;
  }

</style>
