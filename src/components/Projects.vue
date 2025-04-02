<script setup>
import { ref } from 'vue';

const projects = [
  {
    id: 1,
    title: 'E-Commerce Microservices Platform',
    description: 'A scalable e-commerce platform built with Spring Boot microservices architecture. Includes services for product catalog, orders, authentication, and payment processing.',
    image: 'ecommerce',
    tags: ['Java', 'Spring Boot', 'Microservices', 'Docker', 'Kubernetes', 'MySQL', 'Redis'],
    githubLink: 'https://github.com',
    demoLink: 'https://example.com'
  },
  {
    id: 2,
    title: 'Real-time Analytics Dashboard',
    description: 'A real-time analytics dashboard that processes and visualizes data streams. Built with Spring WebFlux for reactive processing and Vue.js for the frontend.',
    image: 'dashboard',
    tags: ['Java', 'Spring WebFlux', 'Reactive', 'Vue.js', 'WebSockets', 'MongoDB', 'Docker'],
    githubLink: 'https://github.com',
    demoLink: 'https://example.com'
  },
  {
    id: 3,
    title: 'Enterprise Document Management System',
    description: 'A secure document management system for enterprises with role-based access control, versioning, and full-text search capabilities.',
    image: 'document',
    tags: ['Java', 'Spring Security', 'Hibernate', 'PostgreSQL', 'Elasticsearch', 'AWS S3', 'JWT'],
    githubLink: 'https://github.com',
    demoLink: 'https://example.com'
  },
  {
    id: 4,
    title: 'DevOps Automation Platform',
    description: 'A platform for automating CI/CD pipelines, infrastructure provisioning, and monitoring. Integrates with popular tools and cloud platforms.',
    image: 'devops',
    tags: ['Java', 'Spring Boot', 'Terraform', 'Jenkins', 'AWS', 'Docker', 'Kubernetes'],
    githubLink: 'https://github.com',
    demoLink: 'https://example.com'
  },
  {
    id: 5,
    title: 'Banking API Gateway',
    description: 'A secure API gateway for banking applications that handles authentication, rate limiting, and request routing to multiple backend services.',
    image: 'banking',
    tags: ['Java', 'Spring Cloud Gateway', 'OAuth2', 'Redis', 'Resilience4j', 'Prometheus', 'Grafana'],
    githubLink: 'https://github.com',
    demoLink: 'https://example.com'
  },
  {
    id: 6,
    title: 'Smart Home IoT Platform',
    description: 'An IoT platform for smart home devices that enables device management, automation, and data analysis.',
    image: 'iot',
    tags: ['Java', 'Spring Boot', 'MQTT', 'Kafka', 'Time-series DB', 'React', 'Docker'],
    githubLink: 'https://github.com',
    demoLink: 'https://example.com'
  }
];

// Placeholder gradient colors for project cards
const gradients = [
  'from-blue-500 to-purple-500',
  'from-green-500 to-blue-500',
  'from-purple-500 to-pink-500',
  'from-yellow-500 to-red-500',
  'from-teal-500 to-green-500',
  'from-indigo-500 to-blue-500'
];
</script>

<template>
  <section id="projects" class="py-20 bg-white dark:bg-gray-900 transition-colors duration-300">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="lg:text-center mb-16">
        <h2 class="text-base text-primary-600 dark:text-primary-400 font-semibold tracking-wide uppercase">Projects</h2>
        <p class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-gray-900 dark:text-white sm:text-4xl">
          Featured Work
        </p>
        <p class="mt-4 max-w-2xl text-xl text-gray-500 dark:text-gray-300 lg:mx-auto">
          Explore some of my recent projects that showcase my technical expertise and problem-solving abilities.
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(project, index) in projects" :key="project.id" 
             class="bg-white dark:bg-gray-800 rounded-lg shadow-lg overflow-hidden transition-transform duration-300 hover:transform hover:scale-105 flex flex-col">
          
          <!-- Project image/placeholder -->
          <div :class="`bg-gradient-to-br ${gradients[index % gradients.length]} h-48 w-full`" aria-hidden="true">
            <!-- In a real app, you'd use actual images -->
            <div class="h-full w-full flex items-center justify-center">
              <svg class="h-16 w-16 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" 
                      d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path>
              </svg>
            </div>
          </div>
          
          <div class="p-6 flex-grow">
            <h3 class="text-lg font-bold text-gray-900 dark:text-white mb-2">{{ project.title }}</h3>
            <p class="text-gray-600 dark:text-gray-300 mb-4">{{ project.description }}</p>
            
            <!-- Tags -->
            <div class="flex flex-wrap gap-2 mb-4">
              <span v-for="tag in project.tags.slice(0, 3)" :key="tag" 
                    class="px-2 py-1 text-xs font-medium bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded">
                {{ tag }}
              </span>
              <span v-if="project.tags.length > 3" class="px-2 py-1 text-xs font-medium bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-gray-200 rounded">
                +{{ project.tags.length - 3 }} more
              </span>
            </div>
          </div>
          
          <!-- Project links -->
          <div class="px-6 py-4 bg-gray-50 dark:bg-gray-750 border-t border-gray-200 dark:border-gray-700">
            <div class="flex space-x-4">
              <a :href="project.githubLink" target="_blank" class="text-gray-600 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-colors duration-300">
                <span class="sr-only">GitHub</span>
                <!-- GitHub icon -->
                <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                  <path fill-rule="evenodd" d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z" clip-rule="evenodd" />
                </svg>
              </a>
              <a :href="project.demoLink" target="_blank" class="text-gray-600 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-colors duration-300">
                <span class="sr-only">Live Demo</span>
                <!-- External link icon -->
                <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"></path>
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
      
      <!-- View More Projects Button -->
      <div class="mt-12 text-center">
        <a href="#" class="inline-flex items-center px-6 py-3 border border-transparent text-base font-medium rounded-md shadow-sm text-white bg-primary-600 hover:bg-primary-700 transition-colors duration-300">
          View All Projects
          <svg class="ml-2 -mr-1 h-5 w-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path>
          </svg>
        </a>
      </div>
    </div>
  </section>
</template> 