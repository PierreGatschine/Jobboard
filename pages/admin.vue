<template>
  <div>
    <Appbar v-bind:style="{ background: activeColor}"/>
    <div class="m-3 mb-5">
      <Wrapper msg="Administration"/>
    </div>
    <div class="m-3 mb-5 ">
      <Title msg="Advertisements"/>
      <AdminList />
      <Title msg="Companies"/>
      <AdminCompList />
    </div>


  </div>
</template>

<script>
import AppBbar from '../components/Appbar.vue'
import Wrapper from '../components/Wrapper.vue'
import AdminList from '../components/AdminAdvList.vue'
import Title from '../components/Title.vue'
import AdminCompList from '../components/AdminCompList.vue'

export default {
  components: {AppBbar, Wrapper, AdminList, Title, AdminCompList},
  data() {
    return {
      activeColor: ' ',
    }
  },
}

</script>

<style lang="postcss" scoped>
  html {
    @apply bg-gray-300;
  }
  nav {
    @apply laptop:max-w-4xl mx-auto flex flex-row  justify-between items-center py-2 p-4 w-full bg-gray-900 rounded-lg ;
  }
  .navBar {
    @apply flex justify-around p-0 bg-gray-800;
  }

</style>



