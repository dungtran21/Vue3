<script setup>
import { RouterView } from 'vue-router'

import theHeader from './layouts/TheHeader.vue'
import theSidebar from './layouts/TheSidebar.vue'
</script>

<template>
  <div class="content-container">
    <the-header> </the-header>
    <div class="main-content flex-1">
      <the-sidebar> </the-sidebar>
      
      <RouterView />
      
    </div>
  </div>
</template>

<style scoped>
.content-container {
  height: 100%;
  display: flex;
  flex-direction: column;
}
.main-content{
  display: flex;
}
</style>
