<template>
  <div class="max-w-4xl mx-auto sm:px-6 lg:px-8">
    <div
      class="
        mt-8
        bg-blue-100

        text-gray-600
        overflow-hidden
        shadow
        rounded-lg
        m-2
        p-6
      "
      v-for="(item, index) in allAdvertisements"
      v-bind:key="index"
    >
      <div class="flex justify-between items-center mx-auto">
        <h2 class="text-2xl leading-7 font-semibold">
          {{ item.title }}
        </h2>
        <div class="btn ml-1">
          <btn direction="form" msg="Apply" />
        </div>
      </div>

      <h3 class="text-xl leading-7 font-light">
        {{ item.name }}
      </h3>
      <p class="mt-3 text-gray-600">
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
        <p class="mt-4 pt-4 text-gray-600">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
          </svg> <spam class="font-thin">{{ item.parution }}</spam>
        </p>
        <div class="displayMoreInfo" @click.stop="showModal = !showModal">
          <button
            class="
              bg-blue-600
              hover:bg-blue-700
              text-gray-100
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
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AdvList",

  data() {
    return {
      allAdvertisements: [],
      showModal: false,
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
    },
  },

  mounted() {
    /* this.asyncData(); */
    this.fetchSomething();
  },
};
</script>

<style></style>
