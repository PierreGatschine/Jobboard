<template>
  <div>
    <nav>
        <img src="../static/totoJob_logo2.svg"/>
      <div class="navBar">
        <NuxtLink to="/" class="btn "><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" />
          </svg>
        </NuxtLink>
        <NuxtLink to="/form" class="btn"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z" />
          </svg>
        </NuxtLink>
        <NuxtLink to="/login" class="btn"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 16l-4-4m0 0l4-4m-4 4h14m-5 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h7a3 3 0 013 3v1" />
          </svg>
        </NuxtLink>
        <Nuxtlink to="/logout" @click="logout" class="btn"><svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 16l4-4m0 0l-4-4m4 4H7m6 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h4a3 3 0 013 3v1" />
          </svg>
        </Nuxtlink>
      </div>
    </nav>
    <!-- <nav>
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
        <div v-if="$auth.loggedIn">

            {{ $auth.user.email }}

            <Nuxtlink to="/logout" class="btn">
              Logout
            </Nuxtlink>
        </div>
        <div v-else class="flex justify-around p-0">
            <NuxtLink to="/login" class="btn">
              Login
            </NuxtLink>
            <NuxtLink to="/register" class="btn">
              Register
            </NuxtLink>

        </div>

      </div>
    </nav> -->
  </div>
</template>

<script>
export default {
  name: 'Appbar',
  components: {

  },
  methods: {
    logout(){
            localStorage.userId = "";
            localStorage.token = "";
            localStorage.role = "";
            localStorage.removeItem();
        },
  }

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

</style>
