<script setup>
import { ref, onMounted } from 'vue';

const roles = ['Software Engineer', 'Java Developer', 'Full Stack Developer', 'Backend Engineer'];
const currentRole = ref(roles[0]);
const typewriterText = ref('');
const cursorVisible = ref(true);

onMounted(() => {
  let roleIndex = 0;
  let charIndex = 0;
  let isDeleting = false;
  let typingSpeed = 100; // milliseconds per character
  
  const typeWriter = () => {
    const currentText = roles[roleIndex];
    
    if (isDeleting) {
      typewriterText.value = currentText.substring(0, charIndex - 1);
      charIndex--;
      typingSpeed = 50; // faster when deleting
    } else {
      typewriterText.value = currentText.substring(0, charIndex + 1);
      charIndex++;
      typingSpeed = 100; // slower when typing
    }
    
    // If word is complete, pause before deleting
    if (!isDeleting && charIndex === currentText.length) {
      typingSpeed = 1500; // pause at the end
      isDeleting = true;
    } else if (isDeleting && charIndex === 0) {
      isDeleting = false;
      roleIndex = (roleIndex + 1) % roles.length; // move to next role
      typingSpeed = 500; // pause before starting next word
    }
    
    setTimeout(typeWriter, typingSpeed);
  };
  
  // Start the typewriter effect
  typeWriter();
  
  // Cursor blinking
  setInterval(() => {
    cursorVisible.value = !cursorVisible.value;
  }, 500);
});
</script>

<template>
  <section id="home" class="w-full min-h-screen flex items-center pt-16 pb-20 bg-gray-50 dark:bg-gray-900">
    <div class="container mx-auto px-4 md:px-6">
      <div class="flex flex-col lg:flex-row items-center gap-12">
        <!-- Left Column - Name and Intro -->
        <div class="w-full lg:w-1/2 flex flex-col items-center lg:items-start lg:pr-8">
          <div class="relative">
            <div class="absolute -top-10 -left-10 w-24 h-24 bg-blue-400/20 dark:bg-blue-600/20 rounded-full blur-xl"></div>
            <div class="absolute -bottom-10 -right-10 w-24 h-24 bg-primary-400/20 dark:bg-primary-600/20 rounded-full blur-xl"></div>
            
            <h1 class="text-5xl md:text-6xl lg:text-7xl font-bold text-gray-900 dark:text-white mb-6 relative">
              Hi, I'm <span class="text-blue-600 dark:text-blue-400 inline-block relative">
                Ho Cong Viet
                <span class="absolute -bottom-2 left-0 w-full h-2 bg-blue-600/20 dark:bg-blue-400/20 rounded-full"></span>
              </span>
            </h1>
          </div>
          
          <div class="flex items-center mb-6 mt-4">
            <span class="text-xl md:text-2xl text-gray-600 dark:text-gray-300 mr-2">I'm a</span>
            <div class="typewriter-container h-8 overflow-hidden relative">
              <span class="text-xl md:text-2xl font-semibold text-blue-600 dark:text-blue-400">{{ typewriterText }}</span>
              <span class="cursor" :class="{ 'blink': !cursorVisible }">|</span>
            </div>
          </div>
          
          <p class="text-gray-600 dark:text-gray-300 text-lg mb-8 max-w-xl text-center lg:text-left">
            A passionate developer committed to crafting clean, user-friendly solutions that combine technical excellence with creative problem-solving.
          </p>
          
          <div class="flex flex-wrap gap-4 mb-8">
            <a href="#contact" class="px-6 py-3 bg-blue-600 hover:bg-blue-700 text-white font-medium rounded-lg transition duration-300 flex items-center shadow-lg shadow-blue-600/20 hover:shadow-blue-600/30 transform hover:-translate-y-1">
              <span>Contact Me</span>
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
              </svg>
            </a>
            <a href="#projects" class="px-6 py-3 border border-blue-600 text-blue-600 dark:text-blue-400 dark:border-blue-400 hover:bg-blue-50 dark:hover:bg-gray-800 font-medium rounded-lg transition duration-300 flex items-center transform hover:-translate-y-1">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 12l3-3m0 0l3 3m-3-3v15m10-12l-3 3m0 0l-3-3m3 3V3" />
              </svg>
              <span>View Projects</span>
            </a>
          </div>
          
          <!-- Social Icons with animated hover -->
          <div class="flex items-center space-x-4">
            <span class="text-gray-500 dark:text-gray-400 text-sm">Find me on:</span>
            <a href="https://github.com" target="_blank" class="text-gray-600 hover:text-blue-600 dark:text-gray-400 dark:hover:text-blue-400 transition-all duration-300 transform hover:-translate-y-1">
              <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
              </svg>
            </a>
            <a href="https://linkedin.com" target="_blank" class="text-gray-600 hover:text-blue-600 dark:text-gray-400 dark:hover:text-blue-400 transition-all duration-300 transform hover:-translate-y-1">
              <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
                <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
              </svg>
            </a>
            <a href="https://twitter.com" target="_blank" class="text-gray-600 hover:text-blue-600 dark:text-gray-400 dark:hover:text-blue-400 transition-all duration-300 transform hover:-translate-y-1">
              <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
                <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/>
              </svg>
            </a>
          </div>
        </div>
        
        <!-- Right Column - Profile Image and Animated Elements -->
        <div class="w-full lg:w-1/2 flex justify-center">
          <div class="relative">
            <!-- Profile Image - Increased size -->
            <div class="w-80 h-80 md:w-96 md:h-96 rounded-full overflow-hidden border-4 border-blue-600 dark:border-blue-400 shadow-2xl relative z-10">
              <img src="../assets/profile.png" alt="Profile" class="w-full h-full object-cover" />
            </div>
            
            <!-- Decorative overlay elements -->
            <div class="absolute -top-6 -left-6 w-20 h-20 bg-blue-100 dark:bg-blue-900 rounded-full z-0 animate-pulse-slow"></div>
            <div class="absolute -bottom-6 -right-6 w-16 h-16 bg-primary-100 dark:bg-primary-900 rounded-full z-0 animate-pulse-slow"></div>
            
            <!-- Floating Stats Card -->
            <div class="absolute -bottom-16 right-0 bg-white dark:bg-gray-800 p-6 rounded-xl shadow-2xl border border-gray-200 dark:border-gray-700 z-20 transform transition-transform hover:scale-105">
              <div class="grid grid-cols-2 gap-6">
                <div class="text-center">
                  <h3 class="font-bold text-blue-600 dark:text-blue-400 text-3xl">3+</h3>
                  <p class="text-gray-600 dark:text-gray-300 text-sm">Years Exp</p>
                </div>
                <div class="text-center">
                  <h3 class="font-bold text-blue-600 dark:text-blue-400 text-3xl">10+</h3>
                  <p class="text-gray-600 dark:text-gray-300 text-sm">Projects</p>
                </div>
              </div>
            </div>
            
            <!-- Tech badges floating around the avatar -->
            <div class="absolute top-5 -left-12 transform -rotate-12 bg-white dark:bg-gray-800 px-3 py-1 rounded-lg shadow-lg animate-float-slow">
              <span class="font-medium text-blue-600 dark:text-blue-400">Java</span>
            </div>
            <div class="absolute top-1/4 -right-16 transform rotate-12 bg-white dark:bg-gray-800 px-3 py-1 rounded-lg shadow-lg animate-float-slower">
              <span class="font-medium text-green-600 dark:text-green-400">Spring</span>
            </div>
            <div class="absolute bottom-1/3 -left-14 transform -rotate-6 bg-white dark:bg-gray-800 px-3 py-1 rounded-lg shadow-lg animate-float">
              <span class="font-medium text-purple-600 dark:text-purple-400">Web</span>
            </div>
            <div class="absolute top-2/3 -right-12 transform rotate-6 bg-white dark:bg-gray-800 px-3 py-1 rounded-lg shadow-lg animate-float-slow">
              <span class="font-medium text-yellow-600 dark:text-yellow-400">Cloud</span>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Scroll down indicator -->
      <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 flex flex-col items-center opacity-70 hover:opacity-100 transition-opacity">
        <span class="text-sm text-gray-600 dark:text-gray-400 mb-2">Scroll Down</span>
        <div class="w-6 h-10 border-2 border-gray-600 dark:border-gray-400 rounded-full flex justify-center">
          <div class="w-1 h-3 bg-gray-600 dark:bg-gray-400 rounded-full mt-2 animate-scroll-down"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
section {
  margin-top: 0;
  padding-top: 0; /* Removed fixed padding */
  position: relative;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

.cursor.blink {
  opacity: 0;
}

.typewriter-container {
  display: inline-flex;
  align-items: center;
}

/* Animation keyframes */
@keyframes float {
  0% { transform: translateY(0) rotate(-12deg); }
  50% { transform: translateY(-10px) rotate(-6deg); }
  100% { transform: translateY(0) rotate(-12deg); }
}

@keyframes float-slow {
  0% { transform: translateY(0) rotate(12deg); }
  50% { transform: translateY(-15px) rotate(6deg); }
  100% { transform: translateY(0) rotate(12deg); }
}

@keyframes float-slower {
  0% { transform: translateY(0) rotate(-6deg); }
  50% { transform: translateY(-8px) rotate(0deg); }
  100% { transform: translateY(0) rotate(-6deg); }
}

@keyframes pulse-slow {
  0% { opacity: 0.5; }
  50% { opacity: 0.8; }
  100% { opacity: 0.5; }
}

@keyframes scroll-down {
  0% { transform: translateY(0); opacity: 1; }
  50% { transform: translateY(6px); opacity: 0.5; }
  100% { transform: translateY(0); opacity: 1; }
}

.animate-float {
  animation: float 4s ease-in-out infinite;
}

.animate-float-slow {
  animation: float-slow 6s ease-in-out infinite;
}

.animate-float-slower {
  animation: float-slower 8s ease-in-out infinite;
}

.animate-pulse-slow {
  animation: pulse-slow 4s ease-in-out infinite;
}

.animate-scroll-down {
  animation: scroll-down 2s ease-in-out infinite;
}
</style>