<script setup>
import { ref, onMounted, watch } from 'vue';
import Navbar from './components/Navbar.vue';
import Hero from './components/Hero.vue';
import About from './components/About.vue';
import Skills from './components/Skills.vue';
import Projects from './components/Projects.vue';
import Experience from './components/Experience.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';

const isDarkMode = ref(false);

onMounted(() => {
  const savedMode = localStorage.getItem('darkMode');
  if (savedMode === 'true' || (!savedMode && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
    isDarkMode.value = true;
    document.documentElement.classList.add('dark');
  }
});

watch(isDarkMode, (newVal) => {
  localStorage.setItem('darkMode', newVal);
  if (newVal) {
    document.documentElement.classList.add('dark');
  } else {
    document.documentElement.classList.remove('dark');
  }
});

const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value;
};
</script>

<template>
  <div class="app-container">
    <Navbar :isDarkMode="isDarkMode" @toggle-dark-mode="toggleDarkMode" />
    <main>
      <Hero />
      <About />
      <Skills />
      <Projects />
      <Experience />
      <Contact />
    </main>
    <Footer />
  </div>
</template>

<style>
html, body {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  overflow-x: hidden;
}

html {
  overflow-y: auto;
  overscroll-behavior-y: none;
}

body {
  position: relative;
  min-height: 100vh;
}

#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  width: 100%;
}

/* Override Tailwind container behavior */
.container {
  width: 100%;
  max-width: 100%;
}

section {
  width: 100%;
}

/* Prevent footer issues */
footer {
  flex-shrink: 0;
  position: relative;
  bottom: 0;
  left: 0;
  right: 0;
}
</style>

<style scoped>
.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  width: 100%;
}

main {
  flex: 1 0 auto;
  display: flex;
  flex-direction: column;
}
</style>
