<script setup lang="ts">
import { ref } from 'vue'
import Header from './components/Header.vue'
import Body from './components/Body.vue'
import Footer from './components/Footer.vue'

const language = ref<'en' | 'es'>('en')

function toggleLanguage() {
  language.value = language.value === 'en' ? 'es' : 'en'
}
</script>

<template>
  <div class="min-h-screen bg-[#F8FAFC] text-slate-900 font-sans selection:bg-blue-100">
    <Header :language="language" @toggle-language="toggleLanguage" />
    <main>
      <Body :language="language" />
    </main>
    <Footer :language="language" />
  </div>
</template>

<style scoped>
</style>
