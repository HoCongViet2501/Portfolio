<script setup>
import { ref } from 'vue';
import { MoonIcon, SunIcon, Bars3Icon, XMarkIcon } from '@heroicons/vue/24/outline';

defineProps({
  isDarkMode: {
    type: Boolean,
    required: true
  }
});

const emit = defineEmits(['toggle-dark-mode']);
const mobileMenuOpen = ref(false);

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value;
};

const navItems = [
  { name: 'About', href: '#about' },
  { name: 'Skills', href: '#skills' },
  { name: 'Projects', href: '#projects' },
  { name: 'Experience', href: '#experience' },
  { name: 'Contact', href: '#contact' }
];
</script>

<template>
  <nav class="bg-white dark:bg-gray-900 shadow-sm fixed w-full z-10 transition-colors duration-300">
    <div class="w-full max-w-screen-2xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16">
        <div class="flex">
          <div class="flex-shrink-0 flex items-center">
            <a href="#" class="text-3xl font-bold text-primary-600 dark:text-primary-400">My Portfolio</a>
          </div>
        </div>
        
        <!-- Desktop Menu -->
        <div class="hidden sm:ml-6 sm:flex sm:items-center sm:space-x-8">
          <div class="flex space-x-8">
            <a v-for="item in navItems" :key="item.name" 
               :href="item.href" 
               class="px-3 py-2 text-sm font-medium text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-colors duration-300">
              {{ item.name }}
            </a>
          </div>
          
          <!-- Dark mode toggle -->
          <button @click="$emit('toggle-dark-mode')" 
                  class="p-2 text-gray-500 dark:text-gray-400 hover:text-primary-600 dark:hover:text-primary-400 focus:outline-none transition-colors duration-300">
            <SunIcon v-if="isDarkMode" class="h-6 w-6" aria-hidden="true" />
            <MoonIcon v-else class="h-6 w-6" aria-hidden="true" />
          </button>
        </div>
        
        <!-- Mobile menu button -->
        <div class="flex items-center sm:hidden">
          <button @click="toggleMobileMenu" 
                 class="p-2 rounded-md text-gray-500 dark:text-gray-400 hover:text-primary-600 dark:hover:text-primary-400 focus:outline-none transition-colors duration-300">
            <Bars3Icon v-if="!mobileMenuOpen" class="h-6 w-6" aria-hidden="true" />
            <XMarkIcon v-else class="h-6 w-6" aria-hidden="true" />
          </button>
          
          <!-- Dark mode toggle (mobile) -->
          <button @click="$emit('toggle-dark-mode')" 
                  class="p-2 text-gray-500 dark:text-gray-400 hover:text-primary-600 dark:hover:text-primary-400 focus:outline-none transition-colors duration-300">
            <SunIcon v-if="isDarkMode" class="h-6 w-6" aria-hidden="true" />
            <MoonIcon v-else class="h-6 w-6" aria-hidden="true" />
          </button>
        </div>
      </div>
    </div>
    
    <!-- Mobile menu -->
    <div v-if="mobileMenuOpen" class="sm:hidden bg-white dark:bg-gray-900 transition-colors duration-300">
      <div class="px-2 pt-2 pb-3 space-y-1">
        <a v-for="item in navItems" :key="item.name" 
           :href="item.href"
           @click="mobileMenuOpen = false"
           class="block px-3 py-2 text-base font-medium text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-colors duration-300">
          {{ item.name }}
        </a>
      </div>
    </div>
  </nav>
</template> 