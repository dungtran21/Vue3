<script setup>
import theHeader from './layouts/TheHeader.vue'
import theSidebar from './layouts/TheSidebar.vue'
import theMainContent from './layouts/TheMainContent.vue'
</script>

<template>
  <div class="content-container">
    <the-header />
    <div class="main-content flex-1">
      <the-sidebar />
      <the-main-content/>
    </div>
  </div>
</template>

<style scoped>
.content-container {
  height: 100%;
  display: flex;
  flex-direction: column;
}
.main-content {
  display: flex;
}
</style>
