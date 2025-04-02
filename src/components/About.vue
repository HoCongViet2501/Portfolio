<template>
  <section id="about" class="py-20 w-full bg-white dark:bg-gray-900 transition-colors duration-300">
    <div class="w-full max-w-screen-2xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="lg:text-center">
        <h2 class="text-base text-primary-600 dark:text-primary-400 font-semibold tracking-wide uppercase">About Me</h2>
        <p class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-gray-900 dark:text-white sm:text-4xl">
          Senior Java Software Engineer
        </p>
        <p class="mt-4 max-w-2xl text-xl text-gray-500 dark:text-gray-300 lg:mx-auto">
          With over 8 years of experience building enterprise applications and scalable systems
        </p>
      </div>
      
      <!-- Tech Stack Section -->
      <div class="mt-16 mb-12">
        <div class="bg-gray-50 dark:bg-gray-800 rounded-xl shadow-lg p-8">
          <div class="flex items-center mb-6">
            <div class="h-12 w-12 rounded-full bg-primary-100 dark:bg-primary-800 flex items-center justify-center mr-4">
              <svg class="h-6 w-6 text-primary-600 dark:text-primary-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"></path>
              </svg>
            </div>
            <h3 class="text-xl font-bold text-gray-900 dark:text-white">Tech Stack</h3>
          </div>
          
          <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
            <div class="text-center p-4 bg-blue-50 dark:bg-blue-900/30 rounded-lg">
              <span class="inline-block bg-blue-100 text-blue-800 dark:bg-blue-800 dark:text-blue-100 rounded-full px-3 py-1 text-sm font-medium mb-2">Java</span>
              <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5 mt-2">
                <div class="bg-blue-600 h-2.5 rounded-full" style="width: 95%"></div>
              </div>
              <span class="text-xs text-gray-500 dark:text-gray-400 mt-1">Advanced</span>
            </div>
            
            <div class="text-center p-4 bg-green-50 dark:bg-green-900/30 rounded-lg">
              <span class="inline-block bg-green-100 text-green-800 dark:bg-green-800 dark:text-green-100 rounded-full px-3 py-1 text-sm font-medium mb-2">Spring Boot</span>
              <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5 mt-2">
                <div class="bg-green-600 h-2.5 rounded-full" style="width: 90%"></div>
              </div>
              <span class="text-xs text-gray-500 dark:text-gray-400 mt-1">Advanced</span>
            </div>
            
            <div class="text-center p-4 bg-yellow-50 dark:bg-yellow-900/30 rounded-lg">
              <span class="inline-block bg-yellow-100 text-yellow-800 dark:bg-yellow-800 dark:text-yellow-100 rounded-full px-3 py-1 text-sm font-medium mb-2">Microservices</span>
              <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5 mt-2">
                <div class="bg-yellow-600 h-2.5 rounded-full" style="width: 85%"></div>
              </div>
              <span class="text-xs text-gray-500 dark:text-gray-400 mt-1">Proficient</span>
            </div>
            
            <div class="text-center p-4 bg-purple-50 dark:bg-purple-900/30 rounded-lg">
              <span class="inline-block bg-purple-100 text-purple-800 dark:bg-purple-800 dark:text-purple-100 rounded-full px-3 py-1 text-sm font-medium mb-2">REST APIs</span>
              <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5 mt-2">
                <div class="bg-purple-600 h-2.5 rounded-full" style="width: 90%"></div>
              </div>
              <span class="text-xs text-gray-500 dark:text-gray-400 mt-1">Advanced</span>
            </div>
            
            <div class="text-center p-4 bg-red-50 dark:bg-red-900/30 rounded-lg">
              <span class="inline-block bg-red-100 text-red-800 dark:bg-red-800 dark:text-red-100 rounded-full px-3 py-1 text-sm font-medium mb-2">Docker</span>
              <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5 mt-2">
                <div class="bg-red-600 h-2.5 rounded-full" style="width: 80%"></div>
              </div>
              <span class="text-xs text-gray-500 dark:text-gray-400 mt-1">Proficient</span>
            </div>
            
            <div class="text-center p-4 bg-indigo-50 dark:bg-indigo-900/30 rounded-lg">
              <span class="inline-block bg-indigo-100 text-indigo-800 dark:bg-indigo-800 dark:text-indigo-100 rounded-full px-3 py-1 text-sm font-medium mb-2">Kubernetes</span>
              <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5 mt-2">
                <div class="bg-indigo-600 h-2.5 rounded-full" style="width: 75%"></div>
              </div>
              <span class="text-xs text-gray-500 dark:text-gray-400 mt-1">Intermediate</span>
            </div>
            
            <div class="text-center p-4 bg-pink-50 dark:bg-pink-900/30 rounded-lg">
              <span class="inline-block bg-pink-100 text-pink-800 dark:bg-pink-800 dark:text-pink-100 rounded-full px-3 py-1 text-sm font-medium mb-2">AWS</span>
              <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5 mt-2">
                <div class="bg-pink-600 h-2.5 rounded-full" style="width: 80%"></div>
              </div>
              <span class="text-xs text-gray-500 dark:text-gray-400 mt-1">Proficient</span>
            </div>
            
            <div class="text-center p-4 bg-gray-50 dark:bg-gray-700/30 rounded-lg">
              <span class="inline-block bg-gray-100 text-gray-800 dark:bg-gray-700 dark:text-gray-100 rounded-full px-3 py-1 text-sm font-medium mb-2">CI/CD</span>
              <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5 mt-2">
                <div class="bg-gray-600 h-2.5 rounded-full" style="width: 85%"></div>
              </div>
              <span class="text-xs text-gray-500 dark:text-gray-400 mt-1">Proficient</span>
            </div>
          </div>
        </div>
      </div>

      <div class="mt-8">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-12 items-start">
          <!-- Profile Image - First column -->
          <div>
            <div class="aspect-w-1 aspect-h-1 rounded-lg overflow-hidden shadow-lg">
              <!-- Placeholder image - in a real portfolio, you'd use a professional photo -->
              <div class="bg-gradient-to-br from-primary-500 to-primary-700 h-full w-full flex items-center justify-center">
                <svg class="h-32 w-32 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"></path>
                </svg>
              </div>
            </div>
            
            <!-- Professional details -->
            <div class="mt-8 bg-gray-50 dark:bg-gray-800 rounded-lg p-6 shadow-md">
              <h3 class="text-lg font-bold text-gray-900 dark:text-white mb-4">Professional Details</h3>
              
              <div class="space-y-4">
                <div>
                  <h4 class="text-md font-medium text-gray-900 dark:text-white">Location</h4>
                  <p class="text-gray-600 dark:text-gray-400">San Francisco, CA</p>
                </div>
                
                <div>
                  <h4 class="text-md font-medium text-gray-900 dark:text-white">Email</h4>
                  <p class="text-gray-600 dark:text-gray-400">johndoe@example.com</p>
                </div>
                
                <div>
                  <h4 class="text-md font-medium text-gray-900 dark:text-white">Availability</h4>
                  <p class="text-gray-600 dark:text-gray-400">Full-time</p>
                </div>
              </div>
            </div>
          </div>
          
          <!-- Bio - Second column -->
          <div>
            <p class="text-lg text-gray-700 dark:text-gray-300 mb-6">
              I'm a passionate Java developer with expertise in building robust, scalable, and high-performance applications. I specialize in Java, Spring Boot, microservices architecture, and cloud technologies.
            </p>
            
            <p class="text-lg text-gray-700 dark:text-gray-300 mb-6">
              Throughout my career, I've worked on various complex projects, from designing RESTful APIs to implementing enterprise-level applications. I'm committed to writing clean, maintainable code and following best practices.
            </p>
            
            <div class="mt-8">
              <a href="#contact" class="inline-flex items-center px-4 py-2 border border-transparent text-base font-medium rounded-md shadow-sm text-white bg-primary-600 hover:bg-primary-700 transition-colors duration-300">
                Get in Touch
              </a>
              <a href="#" class="ml-4 inline-flex items-center px-4 py-2 border border-gray-300 dark:border-gray-600 text-base font-medium rounded-md text-gray-700 dark:text-gray-300 bg-white dark:bg-gray-800 hover:bg-gray-50 dark:hover:bg-gray-700 transition-colors duration-300">
                Download Resume
              </a>
            </div>
          </div>
          
          <!-- Stats and skills - Third column -->
          <div>
            <div class="bg-gray-50 dark:bg-gray-800 rounded-lg p-6 shadow-md">
              <h3 class="text-lg font-bold text-gray-900 dark:text-white mb-4">Expertise</h3>
              
              <!-- Skills with progress bars -->
              <div class="space-y-6">
                <div>
                  <div class="flex justify-between mb-1">
                    <span class="text-gray-700 dark:text-gray-300">Java</span>
                    <span class="text-gray-700 dark:text-gray-300">95%</span>
                  </div>
                  <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5">
                    <div class="bg-primary-600 h-2.5 rounded-full" style="width: 95%"></div>
                  </div>
                </div>
                
                <div>
                  <div class="flex justify-between mb-1">
                    <span class="text-gray-700 dark:text-gray-300">Spring Boot</span>
                    <span class="text-gray-700 dark:text-gray-300">90%</span>
                  </div>
                  <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5">
                    <div class="bg-primary-600 h-2.5 rounded-full" style="width: 90%"></div>
                  </div>
                </div>
                
                <div>
                  <div class="flex justify-between mb-1">
                    <span class="text-gray-700 dark:text-gray-300">Microservices</span>
                    <span class="text-gray-700 dark:text-gray-300">85%</span>
                  </div>
                  <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5">
                    <div class="bg-primary-600 h-2.5 rounded-full" style="width: 85%"></div>
                  </div>
                </div>
                
                <div>
                  <div class="flex justify-between mb-1">
                    <span class="text-gray-700 dark:text-gray-300">Cloud (AWS/Azure)</span>
                    <span class="text-gray-700 dark:text-gray-300">80%</span>
                  </div>
                  <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2.5">
                    <div class="bg-primary-600 h-2.5 rounded-full" style="width: 80%"></div>
                  </div>
                </div>
              </div>
            </div>
            
            <!-- Stats -->
            <div class="mt-6 grid grid-cols-2 gap-4">
              <div class="bg-white dark:bg-gray-800 p-4 rounded-lg shadow-md text-center">
                <span class="block text-3xl font-bold text-primary-600 dark:text-primary-400">8+</span>
                <span class="text-gray-600 dark:text-gray-300">Years Experience</span>
              </div>
              
              <div class="bg-white dark:bg-gray-800 p-4 rounded-lg shadow-md text-center">
                <span class="block text-3xl font-bold text-primary-600 dark:text-primary-400">50+</span>
                <span class="text-gray-600 dark:text-gray-300">Projects</span>
              </div>
              
              <div class="bg-white dark:bg-gray-800 p-4 rounded-lg shadow-md text-center">
                <span class="block text-3xl font-bold text-primary-600 dark:text-primary-400">20+</span>
                <span class="text-gray-600 dark:text-gray-300">Clients</span>
              </div>
              
              <div class="bg-white dark:bg-gray-800 p-4 rounded-lg shadow-md text-center">
                <span class="block text-3xl font-bold text-primary-600 dark:text-primary-400">100%</span>
                <span class="text-gray-600 dark:text-gray-300">Satisfaction</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template> 