<template>
  <div>

    <nav>
        <img src="../static/totoJob_logo2.svg"/>
      <div class="navBar">
        <NuxtLink to="/" class="btn "><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 20 20" fill="currentColor">
          <path d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z" />
          </svg>
        </NuxtLink>
        <NuxtLink to="/form" class="btn"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 20 20" fill="currentColor">
          <path fill-rule="evenodd" d="M10.496 2.132a1 1 0 00-.992 0l-7 4A1 1 0 003 8v7a1 1 0 100 2h14a1 1 0 100-2V8a1 1 0 00.496-1.868l-7-4zM6 9a1 1 0 00-1 1v3a1 1 0 102 0v-3a1 1 0 00-1-1zm3 1a1 1 0 012 0v3a1 1 0 11-2 0v-3zm5-1a1 1 0 00-1 1v3a1 1 0 102 0v-3a1 1 0 00-1-1z" clip-rule="evenodd" />
          </svg>
        </NuxtLink>
        <NuxtLink to="/login" class="btn"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 20 20" fill="currentColor">
          <path fill-rule="evenodd" d="M3 3a1 1 0 011 1v12a1 1 0 11-2 0V4a1 1 0 011-1zm7.707 3.293a1 1 0 010 1.414L9.414 9H17a1 1 0 110 2H9.414l1.293 1.293a1 1 0 01-1.414 1.414l-3-3a1 1 0 010-1.414l3-3a1 1 0 011.414 0z" clip-rule="evenodd" />
          </svg>
        </NuxtLink>
      </div>
    </nav>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="postcss" scoped>
  nav {
    @apply laptop:max-w-4xl mx-auto flex flex-row  justify-between items-center py-2 p-4 w-full bg-white rounded-lg ;
  }
  .navBar {
    @apply flex justify-around p-0;
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


  /*.login {
    @apply px-4 py-2 font-medium bg-blue-600 rounded-md text-gray-50;
  }
  .login:hover {
    @apply bg-gray-50 text-blue-600;
  }*/
</style>
