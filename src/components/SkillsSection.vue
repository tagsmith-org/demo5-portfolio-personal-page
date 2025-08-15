<template>
  <section class="section-padding bg-background">
    <div class="container-max">
      <!-- Section Header -->
      <div class="text-center mb-16 animate-fade-in-up">
        <h2 class="text-3xl md:text-4xl font-bold text-text mb-4">
          Skills & Technologies
        </h2>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          My technical expertise spans across frontend, backend, and design technologies, 
          allowing me to create comprehensive digital solutions.
        </p>
      </div>
      
      <!-- Skills Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <!-- Frontend Skills -->
        <div class="bg-white rounded-xl p-8 shadow-lg animate-fade-in-up" style="animation-delay: 0.1s">
          <div class="flex items-center mb-6">
            <div class="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center mr-4">
              <svg class="w-6 h-6 text-accent" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path>
              </svg>
            </div>
            <h3 class="text-xl font-semibold text-text">Frontend Development</h3>
          </div>
          <div class="space-y-4">
            <div v-for="skill in frontendSkills" :key="skill.name" class="flex items-center justify-between">
              <span class="text-gray-700">{{ skill.name }}</span>
              <div class="flex items-center">
                <div class="w-24 bg-gray-200 rounded-full h-2 mr-3">
                  <div 
                    class="bg-accent h-2 rounded-full transition-all duration-1000"
                    :style="{ width: skill.level + '%' }"
                  ></div>
                </div>
                <span class="text-sm text-gray-500 w-8">{{ skill.level }}%</span>
              </div>
            </div>
          </div>
        </div>
        
        <!-- Backend Skills -->
        <div class="bg-white rounded-xl p-8 shadow-lg animate-fade-in-up" style="animation-delay: 0.2s">
          <div class="flex items-center mb-6">
            <div class="w-12 h-12 bg-green-100 rounded-lg flex items-center justify-center mr-4">
              <svg class="w-6 h-6 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01"></path>
              </svg>
            </div>
            <h3 class="text-xl font-semibold text-text">Backend Development</h3>
          </div>
          <div class="space-y-4">
            <div v-for="skill in backendSkills" :key="skill.name" class="flex items-center justify-between">
              <span class="text-gray-700">{{ skill.name }}</span>
              <div class="flex items-center">
                <div class="w-24 bg-gray-200 rounded-full h-2 mr-3">
                  <div 
                    class="bg-green-600 h-2 rounded-full transition-all duration-1000"
                    :style="{ width: skill.level + '%' }"
                  ></div>
                </div>
                <span class="text-sm text-gray-500 w-8">{{ skill.level }}%</span>
              </div>
            </div>
          </div>
        </div>
        
        <!-- Design Skills -->
        <div class="bg-white rounded-xl p-8 shadow-lg animate-fade-in-up" style="animation-delay: 0.3s">
          <div class="flex items-center mb-6">
            <div class="w-12 h-12 bg-purple-100 rounded-lg flex items-center justify-center mr-4">
              <svg class="w-6 h-6 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 21a4 4 0 01-4-4V5a2 2 0 012-2h4a2 2 0 012 2v12a4 4 0 01-4 4zM21 5a2 2 0 00-2-2h-4a2 2 0 00-2 2v12a4 4 0 004 4h4a2 2 0 002-2V5z"></path>
              </svg>
            </div>
            <h3 class="text-xl font-semibold text-text">Design & Tools</h3>
          </div>
          <div class="space-y-4">
            <div v-for="skill in designSkills" :key="skill.name" class="flex items-center justify-between">
              <span class="text-gray-700">{{ skill.name }}</span>
              <div class="flex items-center">
                <div class="w-24 bg-gray-200 rounded-full h-2 mr-3">
                  <div 
                    class="bg-purple-600 h-2 rounded-full transition-all duration-1000"
                    :style="{ width: skill.level + '%' }"
                  ></div>
                </div>
                <span class="text-sm text-gray-500 w-8">{{ skill.level }}%</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
interface Skill {
  name: string
  level: number
}

const frontendSkills: Skill[] = [
  { name: "Vue.js", level: 95 },
  { name: "React", level: 90 },
  { name: "TypeScript", level: 88 },
  { name: "Tailwind CSS", level: 92 },
  { name: "HTML/CSS", level: 95 }
]

const backendSkills: Skill[] = [
  { name: "Node.js", level: 85 },
  { name: "Python", level: 80 },
  { name: "PostgreSQL", level: 75 },
  { name: "MongoDB", level: 82 },
  { name: "REST APIs", level: 90 }
]

const designSkills: Skill[] = [
  { name: "Figma", level: 85 },
  { name: "Adobe XD", level: 80 },
  { name: "Photoshop", level: 75 },
  { name: "Illustrator", level: 70 },
  { name: "UI/UX Design", level: 88 }
]
</script>
