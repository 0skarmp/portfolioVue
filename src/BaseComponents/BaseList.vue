<template>
  <li class="flex flex-col items-center group cursor-default">
    <div class="
                flex items-center justify-center mb-3 
                group-hover:border-blue-400 group-hover:shadow-md transition-all duration-300">
      
      <img 
        :src="`https://cdn.simpleicons.org/${icon}`" 
        :alt="label"
        class="w-40 h-32 opacity-80 group-hover:opacity-100 group-hover:scale-110 transition-all duration-300"
      />
    </div>
    
    <span class="text-[10px] font-bold tracking-widest text-slate-400 group-hover:text-slate-900 transition-colors uppercase">
      {{ label }}
    </span>
  </li>
</template>

<script setup lang="ts">
defineProps<{
  icon: string
  label: string
}>()
</script>