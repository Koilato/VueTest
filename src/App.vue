<script setup>
import TopHeader from './components/TopHeader.vue'
import ThreeColumnLayout from './components/ThreeColumnLayout.vue'
</script>

<template>
  <div id="main-container">
    <TopHeader />
    <ThreeColumnLayout />
  </div>
</template>

<style>
body {
  margin: 0;
  padding: 0;
  overflow: hidden;
}

#main-container {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

#app {
  height: 100%;
}
</style>
