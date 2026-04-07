<template>
  <footer class="bg-gray-500 py-12 border-t border-gray-100 text-center">
    <p class="text-gray-400 text-sm font-medium">
      © {{ new Date().getFullYear() }} — {{ text }}
    </p>
    <div class="mt-4 flex justify-center gap-4">
      <a href="https://www.linkedin.com/in/oskarmorales/" target="_blank" rel="noopener" class="text-gray-300 hover:text-white">
        <i class="fa-brands fa-linkedin fa-lg"></i>
      </a>
      <a href="https://w.app/pioxnq" target="_blank" rel="noopener" class="text-gray-300 hover:text-white">
        <i class="fa-brands fa-whatsapp fa-lg"></i>
      </a>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{ language: 'en' | 'es' }>()
const text = computed(() => props.language === 'en' ? 'Made by Oskardev' : 'Hecho por Oskardev')
</script>
