<template>
  <div>

    <nav>
        <img src="../static/totoJob_logo2.svg"/>
      <div>
        <NuxtLink to="/" class="btn">Home</NuxtLink>
        <NuxtLink to="/form" class="btn">Form</NuxtLink>
        <NuxtLink to="/login" class="btn">Login</NuxtLink>
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
    @apply flex flex-row  justify-between items-center py-2 p-2.5 w-full bg-gray-50;
  }
  img {
    @apply w-1/3 p-0;
  }
  .logo {

   /*  @apply text-2xl p-2 font-bold text-blue-600; */
  }
  .btn {
    @apply px-4 font-bold text-blue-500 rounded-lg;
  }
  .btn:hover {
    @apply bg-blue-600 text-gray-50 py-2;
  }
  .nuxt-link-exact-active {
    @apply bg-blue-600 text-gray-50 py-2 rounded-lg;
  }


  /*.login {
    @apply px-4 py-2 font-medium bg-blue-600 rounded-md text-gray-50;
  }
  .login:hover {
    @apply bg-gray-50 text-blue-600;
  }*/
</style>
