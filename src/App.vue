
<template>
 <div class="app flex">
  
  
  <SidebarVue/>
  <main class=" md:pl-[6rem]">

    <router-view />

  </main>

 </div>
</template>

<script setup  lang="ts">
import SidebarVue from "./components/Sidebar.vue";
</script>



<style lang="scss">
</style>
