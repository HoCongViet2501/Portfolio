<script setup>
import { ref } from 'vue';

const formData = ref({
  name: '',
  email: '',
  subject: '',
  message: ''
});

const isSubmitting = ref(false);
const isSubmitted = ref(false);
const hasError = ref(false);

const handleSubmit = async () => {
  try {
    isSubmitting.value = true;
    
    // In a real application, you would make an API call here
    // For demo purposes, we'll simulate a successful submission
    await new Promise(resolve => setTimeout(resolve, 1500));
    
    isSubmitted.value = true;
    formData.value = { name: '', email: '', subject: '', message: '' };
  } catch (error) {
    hasError.value = true;
    console.error('Error submitting form:', error);
  } finally {
    isSubmitting.value = false;
  }
};
</script>

<template>
  <section id="contact" class="py-20 bg-white dark:bg-gray-900 transition-colors duration-300">
    <div class="max-w-screen-2xl mx-auto px-4 sm:px-6 lg:px-8 w-full">
      <div class="lg:text-center mb-16">
        <h2 class="text-base text-primary-600 dark:text-primary-400 font-semibold tracking-wide uppercase">Contact</h2>
        <p class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-gray-900 dark:text-white sm:text-4xl">
          Get In Touch
        </p>
        <p class="mt-4 max-w-2xl text-xl text-gray-500 dark:text-gray-300 lg:mx-auto">
          Have a project in mind or interested in working together? Let's connect!
        </p>
      </div>
      
      <div class="lg:grid lg:grid-cols-12 lg:gap-12">
        <!-- Contact Information -->
        <div class="lg:col-span-4 mb-12 lg:mb-0">
          <div class="bg-gray-50 dark:bg-gray-800 rounded-lg shadow-md p-8 h-full">
            <h3 class="text-2xl font-bold text-gray-900 dark:text-white mb-6">Connect With Me</h3>
            
            <!-- Contact Details -->
            <div class="space-y-8">
              <div class="flex items-start">
                <div class="flex-shrink-0">
                  <svg class="h-6 w-6 text-primary-600 dark:text-primary-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path>
                  </svg>
                </div>
                <div class="ml-3">
                  <p class="text-lg font-medium text-gray-900 dark:text-white">Email</p>
                  <p class="mt-1 text-base text-gray-500 dark:text-gray-300">johndoe@example.com</p>
                </div>
              </div>
              
              <div class="flex items-start">
                <div class="flex-shrink-0">
                  <svg class="h-6 w-6 text-primary-600 dark:text-primary-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path>
                  </svg>
                </div>
                <div class="ml-3">
                  <p class="text-lg font-medium text-gray-900 dark:text-white">Phone</p>
                  <p class="mt-1 text-base text-gray-500 dark:text-gray-300">(123) 456-7890</p>
                </div>
              </div>
              
              <div class="flex items-start">
                <div class="flex-shrink-0">
                  <svg class="h-6 w-6 text-primary-600 dark:text-primary-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path>
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path>
                  </svg>
                </div>
                <div class="ml-3">
                  <p class="text-lg font-medium text-gray-900 dark:text-white">Location</p>
                  <p class="mt-1 text-base text-gray-500 dark:text-gray-300">San Francisco, CA</p>
                </div>
              </div>
            </div>
            
            <!-- Social Links -->
            <div class="mt-12">
              <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-4">Follow Me</h3>
              <div class="flex space-x-5">
                <a href="https://github.com" target="_blank" class="text-gray-500 hover:text-gray-700 dark:text-gray-400 dark:hover:text-gray-300">
                  <span class="sr-only">GitHub</span>
                  <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                    <path fill-rule="evenodd" d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z" clip-rule="evenodd" />
                  </svg>
                </a>
                <a href="https://linkedin.com" target="_blank" class="text-gray-500 hover:text-gray-700 dark:text-gray-400 dark:hover:text-gray-300">
                  <span class="sr-only">LinkedIn</span>
                  <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                    <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.454C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.225 0z" />
                  </svg>
                </a>
                <a href="https://twitter.com" target="_blank" class="text-gray-500 hover:text-gray-700 dark:text-gray-400 dark:hover:text-gray-300">
                  <span class="sr-only">Twitter</span>
                  <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                    <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z" />
                  </svg>
                </a>
              </div>
            </div>
          </div>
        </div>
        
        <!-- Contact Form -->
        <div class="lg:col-span-4">
          <div class="bg-gray-50 dark:bg-gray-800 rounded-lg shadow-md p-8 h-full">
            <h3 class="text-2xl font-bold text-gray-900 dark:text-white mb-6">Send Me a Message</h3>
            
            <!-- Success Message -->
            <div v-if="isSubmitted" class="mb-6 bg-green-100 dark:bg-green-800 p-4 rounded-md">
              <p class="text-green-800 dark:text-green-200 font-medium">
                Thank you for your message! I'll get back to you as soon as possible.
              </p>
            </div>
            
            <!-- Error Message -->
            <div v-if="hasError" class="mb-6 bg-red-100 dark:bg-red-800 p-4 rounded-md">
              <p class="text-red-800 dark:text-red-200 font-medium">
                There was an error submitting your message. Please try again.
              </p>
            </div>
            
            <form @submit.prevent="handleSubmit" class="space-y-6">
              <div>
                <label for="name" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Name</label>
                <div class="mt-1">
                  <input
                    id="name"
                    v-model="formData.name"
                    type="text"
                    required
                    class="shadow-sm focus:ring-primary-500 focus:border-primary-500 block w-full sm:text-sm border-gray-300 dark:border-gray-600 rounded-md dark:bg-gray-700 dark:text-white"
                    placeholder="Your Name"
                  />
                </div>
              </div>
              
              <div>
                <label for="email" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Email</label>
                <div class="mt-1">
                  <input
                    id="email"
                    v-model="formData.email"
                    type="email"
                    required
                    class="shadow-sm focus:ring-primary-500 focus:border-primary-500 block w-full sm:text-sm border-gray-300 dark:border-gray-600 rounded-md dark:bg-gray-700 dark:text-white"
                    placeholder="your.email@example.com"
                  />
                </div>
              </div>
              
              <div>
                <label for="subject" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Subject</label>
                <div class="mt-1">
                  <input
                    id="subject"
                    v-model="formData.subject"
                    type="text"
                    required
                    class="shadow-sm focus:ring-primary-500 focus:border-primary-500 block w-full sm:text-sm border-gray-300 dark:border-gray-600 rounded-md dark:bg-gray-700 dark:text-white"
                    placeholder="Subject"
                  />
                </div>
              </div>
              
              <div>
                <label for="message" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Message</label>
                <div class="mt-1">
                  <textarea
                    id="message"
                    v-model="formData.message"
                    rows="4"
                    required
                    class="shadow-sm focus:ring-primary-500 focus:border-primary-500 block w-full sm:text-sm border-gray-300 dark:border-gray-600 rounded-md dark:bg-gray-700 dark:text-white"
                    placeholder="Your message..."
                  ></textarea>
                </div>
              </div>
              
              <div>
                <button
                  type="submit"
                  :disabled="isSubmitting"
                  class="w-full inline-flex justify-center py-3 px-6 border border-transparent shadow-sm text-base font-medium rounded-md text-white bg-primary-600 hover:bg-primary-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-primary-500 transition-colors duration-300 disabled:opacity-50 disabled:cursor-not-allowed"
                >
                  <svg v-if="isSubmitting" class="animate-spin -ml-1 mr-3 h-5 w-5 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                    <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                    <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                  </svg>
                  {{ isSubmitting ? 'Sending...' : 'Send Message' }}
                </button>
              </div>
            </form>
          </div>
        </div>
        
        <!-- Map/Location Feature -->
        <div class="lg:col-span-4 mt-12 lg:mt-0">
          <div class="bg-gray-50 dark:bg-gray-800 rounded-lg shadow-md h-full">
            <div class="p-8">
              <h3 class="text-2xl font-bold text-gray-900 dark:text-white mb-4">Find Me</h3>
              <p class="text-gray-500 dark:text-gray-300 mb-4">Based in San Francisco, California</p>
            </div>
            <!-- Map Placeholder - Would be a real map in production -->
            <div class="aspect-w-16 aspect-h-9 w-full rounded-b-lg overflow-hidden">
              <div class="bg-gray-200 dark:bg-gray-700 w-full h-full">
                <!-- This would be a Google Map or other map integration -->
                <div class="w-full h-full flex items-center justify-center">
                  <div class="text-center">
                    <svg class="h-12 w-12 text-primary-600 dark:text-primary-400 mx-auto" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path>
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path>
                    </svg>
                    <p class="mt-2 text-gray-600 dark:text-gray-400">San Francisco, CA, USA</p>
                    <div class="mt-4">
                      <p class="text-sm text-gray-500 dark:text-gray-400">Available for remote opportunities worldwide</p>
                      <p class="text-sm text-gray-500 dark:text-gray-400">Open to relocation for the right opportunity</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            
            <!-- Working Hours Card -->
            <div class="p-8">
              <h4 class="text-xl font-semibold text-gray-900 dark:text-white mb-4">Working Hours</h4>
              <div class="space-y-3">
                <div class="flex justify-between">
                  <span class="text-gray-600 dark:text-gray-400">Monday - Friday</span>
                  <span class="text-gray-900 dark:text-white">9:00 AM - 5:00 PM</span>
                </div>
                <div class="flex justify-between">
                  <span class="text-gray-600 dark:text-gray-400">Saturday</span>
                  <span class="text-gray-900 dark:text-white">By appointment</span>
                </div>
                <div class="flex justify-between">
                  <span class="text-gray-600 dark:text-gray-400">Sunday</span>
                  <span class="text-gray-900 dark:text-white">Closed</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template> 