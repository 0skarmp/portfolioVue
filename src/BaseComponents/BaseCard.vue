<template>
  <div class="w-full bg-slate-50 rounded-2xl shadow-lg overflow-hidden border border-gray-100 flex flex-col transition-all duration-300 hover:shadow-2xl hover:-translate-y-1 group">
    
    <div class="w-full h-48 overflow-hidden bg-slate-200">
      <img 
        :src="image" 
        :alt="title" 
        class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105"
      />
    </div>

    <div class="p-5 flex flex-col flex-grow">
      <h3 class="text-lg font-bold text-slate-800 uppercase tracking-tight mb-3">
        {{ title }}
      </h3>

      <div class="flex flex-wrap gap-2 mb-6">
        <span 
          v-for="(feature, index) in features" 
          :key="index"
          class="px-3 py-1 bg-slate-100 text-slate-600 rounded-lg text-xs font-semibold"
        >
          {{ feature }}
        </span>
      </div>

      <div class="mt-auto flex gap-3">
        <a 
          v-if="demoUrl"
          :href="demoUrl" 
          target="_blank"
          class="flex-1 bg-[#00A3C4] hover:bg-[#008ba8] text-white text-center py-2.5 rounded-full text-sm font-bold transition-colors"
        >
          Ver Demo
        </a>
        <a 
          v-if="repoUrl"
          :href="repoUrl" 
          target="_blank"
          class="flex-1 border-2 border-[#00A3C4] text-[#00A3C4] hover:bg-cyan-50 text-center py-2 rounded-full text-sm font-bold transition-colors"
        >
          Código
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  subtitle: String, 
  image: {
    type: String,
    required: true
  },
  features: {
    type: Array,
    default: () => []
  },
  demoUrl: {
    type: String,
    default: ''
  },
  repoUrl: {
    type: String,
    default: ''
  }
})
</script>