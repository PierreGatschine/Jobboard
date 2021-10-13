<template>
  <div>
      <div class="navBar">
        <NuxtLink to="/" class="btn "><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" />
          </svg>
        </NuxtLink>
        <NuxtLink to="/admin" class="btn"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z" />
          </svg>
        </NuxtLink>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="postcss" scoped>
  nav {
    @apply laptop:max-w-4xl mx-auto flex flex-row  justify-between items-center py-2 p-4 w-full rounded-lg shadow-sm sticky;
  }
  .navBar {
    @apply flex justify-center p-0;
  }
  img {
    @apply w-32 p-0;
  }
  .logo {

   /*  @apply text-2xl p-2 font-bold text-blue-600; */
  }
  .btn {
    @apply px-4 font-bold text-blue-500 items-end rounded-lg;
  }
  .btn:hover {
    @apply bg-blue-600 text-gray-50 py-2;
  }
  .nuxt-link-exact-active {
    @apply bg-blue-600 text-gray-50 py-2 items-end rounded-lg;
  }

</style>
