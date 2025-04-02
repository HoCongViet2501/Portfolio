<script setup>
import { ref } from 'vue';

const skills = [
  {
    category: 'Languages',
    items: [
      { name: 'Java', level: 95 },
      { name: 'JavaScript', level: 80 },
      { name: 'SQL', level: 85 },
      { name: 'Python', level: 70 },
      { name: 'Kotlin', level: 75 },
    ]
  },
  {
    category: 'Frameworks',
    items: [
      { name: 'Spring Boot', level: 90 },
      { name: 'Spring MVC', level: 85 },
      { name: 'Hibernate/JPA', level: 85 },
      { name: 'JUnit/Mockito', level: 90 },
      { name: 'Vue.js', level: 75 },
    ]
  },
  {
    category: 'Tools & Platforms',
    items: [
      { name: 'Docker', level: 85 },
      { name: 'Kubernetes', level: 75 },
      { name: 'AWS', level: 80 },
      { name: 'Jenkins', level: 85 },
      { name: 'Git', level: 90 },
    ]
  },
  {
    category: 'Databases',
    items: [
      { name: 'MySQL', level: 90 },
      { name: 'PostgreSQL', level: 85 },
      { name: 'MongoDB', level: 80 },
      { name: 'Redis', level: 75 },
      { name: 'Elasticsearch', level: 70 },
    ]
  }
];

const activeTab = ref('Languages');

const setActiveTab = (category) => {
  activeTab.value = category;
};
</script>

<template>
  <section id="skills" class="py-20 bg-gray-50 dark:bg-gray-800 transition-colors duration-300">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="lg:text-center mb-16">
        <h2 class="text-base text-primary-600 dark:text-primary-400 font-semibold tracking-wide uppercase">Skills</h2>
        <p class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-gray-900 dark:text-white sm:text-4xl">
          Technical Expertise
        </p>
        <p class="mt-4 max-w-2xl text-xl text-gray-500 dark:text-gray-300 lg:mx-auto">
          My professional toolkit includes a wide range of technologies for building robust applications.
        </p>
      </div>
      
      <!-- Skills tabs -->
      <div class="max-w-3xl mx-auto">
        <!-- Tab navigation -->
        <div class="border-b border-gray-200 dark:border-gray-700">
          <nav class="-mb-px flex space-x-8 overflow-x-auto">
            <button
              v-for="category in skills.map(s => s.category)"
              :key="category"
              @click="setActiveTab(category)"
              class="whitespace-nowrap py-4 px-1 border-b-2 font-medium text-md transition-colors duration-300"
              :class="category === activeTab 
                ? 'border-primary-500 text-primary-600 dark:text-primary-400' 
                : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300 dark:text-gray-400 dark:hover:text-gray-300 dark:hover:border-gray-600'"
            >
              {{ category }}
            </button>
          </nav>
        </div>
        
        <!-- Skills bars -->
        <div class="mt-10">
          <div v-for="skillCategory in skills" :key="skillCategory.category">
            <div v-if="skillCategory.category === activeTab">
              <div v-for="skill in skillCategory.items" :key="skill.name" class="mb-6">
                <div class="flex justify-between mb-1">
                  <span class="text-base font-medium text-gray-800 dark:text-gray-200">{{ skill.name }}</span>
                  <span class="text-sm font-medium text-gray-600 dark:text-gray-400">{{ skill.level }}%</span>
                </div>
                <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5">
                  <div 
                    class="bg-primary-600 dark:bg-primary-500 h-2.5 rounded-full transition-all duration-500 ease-out" 
                    :style="{ width: skill.level + '%' }"
                  ></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- More skills badges -->
      <div class="mt-16 max-w-3xl mx-auto">
        <h3 class="text-lg font-medium text-gray-900 dark:text-white text-center mb-6">Other Technologies & Tools</h3>
        <div class="flex flex-wrap justify-center gap-3">
          <span class="px-3 py-1 text-sm font-medium bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-full">Maven</span>
          <span class="px-3 py-1 text-sm font-medium bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-full">Gradle</span>
          <span class="px-3 py-1 text-sm font-medium bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-full">RabbitMQ</span>
          <span class="px-3 py-1 text-sm font-medium bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-full">Kafka</span>
          <span class="px-3 py-1 text-sm font-medium bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-full">gRPC</span>
          <span class="px-3 py-1 text-sm font-medium bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-full">REST API</span>
          <span class="px-3 py-1 text-sm font-medium bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-full">GraphQL</span>
          <span class="px-3 py-1 text-sm font-medium bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-full">Microservices</span>
          <span class="px-3 py-1 text-sm font-medium bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-full">CI/CD</span>
          <span class="px-3 py-1 text-sm font-medium bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-full">Spring Security</span>
          <span class="px-3 py-1 text-sm font-medium bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-full">OAuth2</span>
          <span class="px-3 py-1 text-sm font-medium bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded-full">JWT</span>
        </div>
      </div>
    </div>
  </section>
</template> 