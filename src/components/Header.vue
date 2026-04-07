<template>
  <nav class="sticky top-0 z-50 bg-white/80 backdrop-blur-md border-b border-gray-100">
    <div class="max-w-5xl mx-auto px-6 py-4 flex justify-between items-center">
      <span class="font-bold text-xl tracking-tighter">OSKARDEV</span>
      <ul class="hidden md:flex gap-6 text-sm font-medium items-center">
        <li>
          <a
            href="#inicio"
            class="hover:text-blue-700 transition-colors cursor-pointer"
            :class="{ 'underline': active === 'inicio' }"
          >
            {{ labels.inicio }}
          </a>
        </li>
        <li>
          <a
            href="#stack"
            class="hover:text-blue-700 transition-colors cursor-pointer"
            :class="{ 'underline': active === 'stack' }"
          >
            {{ labels.stack }}
          </a>
        </li>
        <li>
          <a
            href="#experiencia"
            class="hover:text-blue-700 transition-colors cursor-pointer"
            :class="{ 'underline': active === 'experiencia' }"
          >
            {{ labels.experiencia }}
          </a>
        </li>
        <li>
          <a
            href="#proyectos"
            class="hover:text-blue-700 transition-colors cursor-pointer"
            :class="{ 'underline': active === 'proyectos' }"
          >
            {{ labels.proyectos }}
          </a>
        </li>
        <li>
          <a
            href="#sobre-mi"
            class="hover:text-blue-700 transition-colors cursor-pointer"
            :class="{ 'underline': active === 'sobre-mi' }"
          >
            {{ labels.sobreMi }}
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
        <li>
          <button
            @click="emit('toggle-language')"
            class="bg-slate-100 text-slate-800 px-4 py-2 rounded-full text-xs hover:bg-slate-200 transition-all"
          >
            Spanish / English
          </button>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { computed, ref, onMounted, onUnmounted, defineProps, defineEmits } from 'vue';

const props = defineProps<{ language: 'en' | 'es' }>()
const emit = defineEmits(['toggle-language'])
const active = ref<string>(window.location.hash.replace('#', '') || 'inicio');

const labels = computed(() => {
  return props.language === 'en'
    ? {
        inicio: 'Home',
        stack: 'Stack',
        experiencia: 'Experience',
        proyectos: 'Projects',
        sobreMi: 'About'
      }
    : {
        inicio: 'Inicio',
        stack: 'Stack',
        experiencia: 'Experiencia',
        proyectos: 'Proyectos',
        sobreMi: 'Sobre mí'
      }
})

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
