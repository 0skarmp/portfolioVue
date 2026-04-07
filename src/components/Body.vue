<template>
  <div class="w-full font-sans bg-slate-300">
    <section id="inicio" class="bg-[#111827] pt-16 pb-24 text-white">
      <div class="max-w-5xl mx-auto px-6">
        <div class="flex flex-col md:flex-row items-center gap-10 animate-fade-in-up">
          <div class="relative">
            <img class="w-44 h-44 rounded-full object-cover border-4 border-white/10 shadow-2xl" src="../assets/oscar.jpg">
            <span class="absolute bottom-2 left-0 bg-[#10B981] text-white text-[10px] font-bold px-3 py-1 rounded-full border-2 border-[#111827]">
              Disponible
            </span>
          </div>

          <div class="text-center md:text-left flex-1">
            <h1 class="text-5xl font-bold tracking-tight">
              Hola, soy <span class="text-blue-500">Oskar Morales</span>
            </h1>
            <p class="mt-4 text-xl text-gray-400 leading-relaxed max-w-2xl">
              +2 años de experiencia. Desarrollador de Software y amante de la Programación, Peru, Lima PE.
            </p>
            
            <div class="mt-8 flex flex-wrap gap-4 justify-center md:justify-start">
              <a href="https://w.app/pioxnq" target="_blank" rel="noopener" class="bg-[#00A3C4] hover:bg-[#008ba8] text-white px-8 py-3 rounded-full font-bold transition-all shadow-lg shadow-cyan-900/20">
                Contáctame
              </a>
              <a href="https://www.linkedin.com/in/oskarmorales/" target="_blank" rel="noopener" class="bg-white/10 hover:bg-white/20 text-white px-8 py-3 rounded-full font-bold border border-white/10 transition-all flex items-center gap-2">
                <i class="fa-brands fa-linkedin"></i> LinkedIn
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="max-w-5xl mx-auto px-6 py-16 grid grid-cols-1 lg:grid-cols-12 gap-16">

    <div class="lg:col-span-5 space-y-16">
        <div id="stack">
            <h2 class="text-5xl font-bold mb-8 ">STACK</h2>
            <ul class="grid grid-cols-3 gap-6">
                <BaseList 
                v-for="skill in skills" 
                :key="skill.id" 
                :icon="skill.icon" 
                :label="skill.title"
                class="hover:scale-110 transition-transform duration-300" 
            />
            </ul>
        </div>

        <div id="experiencia">
            <h2 class=" font-bold text-5xl uppercase mb-8 ">
            Experiencia
            </h2>
          <div class="space-y-10 border-l-2 border-gray-200 pl-6 ml-2">
            <div class="relative">
              <div class="absolute -left-[33px] top-1 w-4 h-4 bg-blue-500 rounded-full border-4 border-white"></div>
              <h3 class="font-bold text-xl">
                Central Time Developers, Inc.
            </h3>
              <p class="text-gray-600 text-sm mt-2 leading-relaxed">
                Plataforma empresarial cloud-native con Vue.js 2.7 y arquitectura serverless en AWS (Lambda, DynamoDB).
              </p>
              <p class="text-gray-600 text-sm mt-2 leading-relaxed">
                Los Ángeles, California, Estados Unidos
              </p>
            </div>
            <div class="relative opacity-60">
              <div class="absolute -left-[33px] top-1 w-4 h-4 bg-gray-300 rounded-full border-4 border-white"></div>
              <h3 class="font-bold text-xl text-gray-800">
                MONKEY VALLEY E.I.R.L.
            </h3>
              <p class="text-gray-500 text-sm mt-2 leading-relaxed text-balance">
                Sistema de transportes usando Python (Flask) y Angular.
              </p>
              <p class="text-gray-500 text-sm mt-2 leading-relaxed text-balance">
                Lima, Perú 
              </p>
            </div>
            <div class="relative opacity-60">
              <div class="absolute -left-[33px] top-1 w-4 h-4 bg-gray-300 rounded-full border-4 border-white"></div>
              <h3 class="font-bold text-xl text-gray-800">
                Multilab
            </h3>
              <p class="text-gray-500 text-sm mt-2 leading-relaxed text-balance">
                Sistema de laboratorios en Python nest y next.
              </p>
              <p class="text-gray-500 text-sm mt-2 leading-relaxed text-balance">
                Lima, Perú 
              </p>
            </div>
          </div>
        </div>
      </div>

      <div class="lg:col-span-7 space-y-16 overflow-hidden">
        <div id="sobre-mi" class="bg-white p-8 rounded-3xl border border-gray-100 shadow-sm">
          <h2 class="text-5xl font-bold mb-4 flex items-center gap-2">
            <span>👤</span> SOBRE MI
          </h2>
          <p class="text-gray-600 leading-relaxed italic ">
            "Desarrollador web enfocado en crear soluciones digitales escalables. Disfruto optimizar la experiencia de usuario y compartir conocimiento con la comunidad tecnológica."
          </p>
        </div>

     <div id="proyectos">
        <h2 class="text-5xl font-bold mb-8">PROYECTOS</h2>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <BaseCard
            class="mt-6"
            title="UBIGEO"
            subtitle="UBIGEO"
            :image="UBIGEO"
            demoUrl="https://0skarmp.github.io/FirstProjectByGroup/"/>
            <BaseCard
            class="mt-6"
            subtitle="HOTEL VIRTUAL ASISTANT"
            :image="HOTEL"
            title="HOTEL VIRTUAL ASISTANT"
            demoUrl="https://juanrcoder.github.io/Project-Landing_HVA/"/>
            <BaseCard
            class="mt-6"
            subtitle="POKEDEX"
            :image="POKEDEX"
            title="POKEDEX"
            demoUrl="https://0skarmp.github.io/Basic-Pokedex/"/>
            <BaseCard
            class="mt-6"
            subtitle="Tetris Game"
            :image="TETRIS"
            title="Tetris"
            demoUrl="https://tetris-puce-six.vercel.app/"/>

        </div>
    </div>

      </div>
    </section>
  </div>
</template>

<script setup lang="ts">

import BaseCard from '../BaseComponents/BaseCard.vue'
import BaseList from '../BaseComponents/BaseList.vue'
import POKEDEX from '../assets/POKEDEX.png'
import HOTEL from '../assets/HOTEL.png'
import UBIGEO from '../assets/UBIGEO.png'
import TETRIS from '../assets/tetris.png'

interface Skill {
  id: string;
  icon: string;
  title: string;
}
const skills: Skill[] = [
  { id: 'js', icon: 'javascript', title: 'JS' },
  { id: 'ts', icon: 'typescript', title: 'TS' },
  { id: 'angular', icon: 'angular', title: 'ANGULAR' },
  { id: 'next', icon: 'nextdotjs', title: 'NEXT' },
  { id: 'nest', icon: 'nestjs', title: 'NEST' },
  { id: 'vue', icon: 'vuedotjs', title: 'VUE' },
  { id: 'node', icon: 'nodedotjs', title: 'NODE' },
  { id: 'mysql', icon: 'mysql', title: 'MYSQL' },
  { id: 'mongodb', icon: 'mongodb', title: 'MONGO' },
  { id: 'tailwind', icon: 'tailwindcss', title: 'TW' },
  { id: 'git', icon: 'git', title: 'GIT' },
  { id: 'react', icon: 'react', title: 'REACT' },
  { id: 'python', icon: 'python', title: 'PYTHON' }
]

</script>
<style scoped>
@keyframes fadeInUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
.animate-fade-in-up {
  animation: fadeInUp 0.8s ease-out forwards;
}

:deep(.swiper-pagination-bullet-active) {
  background-color: #3b82f6; 
}

:deep(.swiper-pagination) {
  bottom: 0px !important;
}
</style>