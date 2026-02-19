<template>
  <nav class="sticky top-0 z-50 bg-white/80 backdrop-blur-md border-b border-gray-100">
    <div class="max-w-5xl mx-auto px-6 py-4 flex justify-between items-center">
      <span class="font-bold text-xl tracking-tighter">OSKARDEV</span>
      <ul class="hidden md:flex gap-8 text-sm font-medium">
        <li>
          <a
            href="#inicio"
            class="hover:text-blue-700 transition-colors cursor-pointer"
            :class="{ 'underline': active === 'inicio' }"
          >
            Inicio
          </a>
        </li>
        <li>
          <a
            href="#stack"
            class="hover:text-blue-700 transition-colors cursor-pointer"
            :class="{ 'underline': active === 'stack' }"
          >
            Stack
          </a>
        </li>
        <li>
          <a
            href="#experiencia"
            class="hover:text-blue-700 transition-colors cursor-pointer"
            :class="{ 'underline': active === 'experiencia' }"
          >
            Experiencia
          </a>
        </li>
        <li>
          <a
            href="#proyectos"
            class="hover:text-blue-700 transition-colors cursor-pointer"
            :class="{ 'underline': active === 'proyectos' }"
          >
            Proyectos
          </a>
        </li>
        <li>
          <a
            href="#sobre-mi"
            class="hover:text-blue-700 transition-colors cursor-pointer"
            :class="{ 'underline': active === 'sobre-mi' }"
          >
            Sobre mí
          </a>
        </li>
        <li>
          <a
            href="https://github.com/0skarmp"
            target="_blank" rel="noopener"
            class="bg-blue-500 text-white px-4 py-2 rounded-full text-xs hover:bg-blue-600 transition-all cursor-pointer"
          >
            Github
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';

const active = ref<string>(window.location.hash.replace('#', '') || 'inicio');

function updateHash() {
  active.value = window.location.hash.replace('#', '') || 'inicio';
}

onMounted(() => {
  window.addEventListener('hashchange', updateHash);
});

onUnmounted(() => {
  window.removeEventListener('hashchange', updateHash);
});
</script>