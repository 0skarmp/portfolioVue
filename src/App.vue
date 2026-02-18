<script setup lang="ts">
import Header from './components/Header.vue'
import Body from './components/Body.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="min-h-screen bg-[#F8FAFC] text-slate-900 font-sans selection:bg-blue-100">
    <Header></Header>
    <main>
      <Body></Body>
    </main>
    <Footer></Footer>
  </div>
</template>

<style scoped>
</style>
