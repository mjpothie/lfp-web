<script setup lang="ts">
import About from './components/About.vue'
import Photos from './components/Photos.vue'
import Contact from './components/Contact.vue'
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<template>
  <div class="min-h-screen bg-black">
    <!-- Navigation -->
    <nav class="bg-black border-b border-gray-800 relative z-50 px-8 py-4">
      <div class="flex justify-between items-center">
        <div class="flex space-x-7">
          <div>
            <a href="#" class="flex items-center py-2">
              <img src="./assets/lfp-logo-cropped.jpg" alt="LFP Photography Logo" class="h-12 w-auto object-contain" />
            </a>
          </div>
        </div>
        
        <!-- Desktop Menu -->
        <div class="hidden md:flex items-center space-x-12 font-rock">
          <a href="#about" class="py-4 px-2 text-gray-300 hover:text-white transition duration-300">About</a>
          <a href="#photos" class="py-4 px-2 text-gray-300 hover:text-white transition duration-300">Photos</a>
          <a href="#contact" class="py-4 px-2 text-gray-300 hover:text-white transition duration-300">Contact</a>
          <a href="https://www.facebook.com/lateforpickup" 
             target="_blank" 
             rel="noopener noreferrer" 
             class="text-gray-300 hover:text-white transition duration-300"
             aria-label="Visit our Facebook page">
            <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24">
              <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
            </svg>
          </a>
        </div>

        <!-- Mobile Menu Button -->
        <button 
          class="md:hidden text-gray-300 hover:text-white focus:outline-none z-50"
          @click="toggleMenu"
          aria-label="Toggle menu"
        >
          <svg 
            class="h-8 w-8" 
            fill="none" 
            viewBox="0 0 24 24" 
            stroke="currentColor"
          >
            <path 
              v-if="!isMenuOpen" 
              stroke-linecap="round" 
              stroke-linejoin="round" 
              stroke-width="2" 
              d="M4 6h16M4 12h16M4 18h16"
            />
            <path 
              v-else 
              stroke-linecap="round" 
              stroke-linejoin="round" 
              stroke-width="2" 
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>
    </nav>

    <!-- Mobile Menu -->
    <transition
      enter-active-class="transition-opacity duration-300 ease-out"
      enter-from-class="opacity-0"
      enter-to-class="opacity-100"
      leave-active-class="transition-opacity duration-200 ease-in"
      leave-from-class="opacity-100"
      leave-to-class="opacity-0"
    >
      <div 
        v-show="isMenuOpen" 
        class="md:hidden fixed inset-0 w-full h-full bg-black bg-opacity-95 z-40 flex items-center justify-center"
      >
        <div class="flex flex-col items-center justify-center h-full space-y-8 font-rock text-2xl">
          <a 
            href="#about" 
            @click="closeMenu"
            class="py-3 px-6 text-gray-300 hover:text-white transition duration-300 hover:scale-110"
          >
            About
          </a>
          <a 
            href="#photos" 
            @click="closeMenu"
            class="py-3 px-6 text-gray-300 hover:text-white transition duration-300 hover:scale-110"
          >
            Photos
          </a>
          <a 
            href="#contact" 
            @click="closeMenu"
            class="py-3 px-6 text-gray-300 hover:text-white transition duration-300 hover:scale-110"
          >
            Contact
          </a>
          <a 
            href="https://www.facebook.com/lateforpickup"
            target="_blank"
            rel="noopener noreferrer"
            class="text-gray-300 hover:text-white transition duration-300 hover:scale-110"
            aria-label="Visit our Facebook page"
          >
            <svg class="w-8 h-8 fill-current" viewBox="0 0 24 24">
              <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
            </svg>
          </a>
        </div>
      </div>
    </transition>

    <!-- Hero Section -->
    <div class="relative h-screen w-full overflow-hidden bg-gradient-to-br from-stone-900 via-gray-900 to-black">
      <!-- Noise texture overlay -->
      <div class="absolute inset-0 opacity-50 mix-blend-overlay">
        <div class="absolute inset-0 animate-subtle-shift" style="background-image: url('data:image/svg+xml,%3Csvg viewBox=\'0 0 200 200\' xmlns=\'http://www.w3.org/2000/svg\'%3E%3Cfilter id=\'noiseFilter\'%3E%3CfeTurbulence type=\'fractalNoise\' baseFrequency=\'0.65\' numOctaves=\'3\' stitchTiles=\'stitch\'/%3E%3C/filter%3E%3Crect width=\'100%25\' height=\'100%25\' filter=\'url(%23noiseFilter)\'/%3E%3C/svg%3E')"></div>
      </div>

      <!-- Scratched/worn texture overlay -->
      <div class="absolute inset-0 opacity-20" style="background-image: url('data:image/svg+xml,%3Csvg viewBox=\'0 0 100 100\' xmlns=\'http://www.w3.org/2000/svg\'%3E%3Cline x1=\'0\' y1=\'50\' x2=\'100\' y2=\'50\' stroke=\'%23ffffff\' stroke-width=\'0.5\' stroke-dasharray=\'1,4\'/%3E%3Cline x1=\'50\' y1=\'0\' x2=\'50\' y2=\'100\' stroke=\'%23ffffff\' stroke-width=\'0.5\' stroke-dasharray=\'1,4\'/%3E%3C/svg%3E')"></div>

      <!-- Main content -->
      <div class="absolute inset-0 flex flex-col items-center justify-center text-white">
        <!-- Band name with distressed effect -->
        <h1 class="font-rock text-7xl md:text-9xl text-center mb-4 relative transform hover:scale-105 transition-transform duration-300" 
            style="text-shadow: 
              2px 2px 0px #660000,
              -2px -2px 0px #000000,
              4px 4px 8px rgba(0,0,0,0.8);
              letter-spacing: -0.05em;
              filter: contrast(150%) brightness(110%);">
          Late for Pickup
        </h1>
        
        <!-- Tagline with scratched effect -->
        <p class="font-rock text-2xl md:text-4xl text-center mb-12 relative tracking-widest opacity-90 transform -rotate-1" 
           style="text-shadow: 
             1px 1px 2px #000,
             -1px -1px 2px #000;
             letter-spacing: 0.15em;">
          <span class="inline-block transform hover:translate-x-1 transition-transform duration-200">90's</span>
          <span class="inline-block transform hover:-translate-y-1 transition-transform duration-200 mx-2">ROCK</span>
          <span class="inline-block transform hover:translate-x-1 transition-transform duration-200">UNLEASHED</span>
        </p>

        <!-- YouTube Video Container with grungy border -->
        <div class="w-full max-w-4xl aspect-video px-4 relative">
          <div class="absolute inset-0 bg-gradient-to-br from-red-900/20 to-stone-900/20 -m-1"></div>
          <iframe
            class="w-full h-full relative shadow-xl"
            style="box-shadow: 0 0 0 1px rgba(255,255,255,0.1), 0 0 15px rgba(0,0,0,0.5);"
            src="https://www.youtube.com/embed/McOiAf8mJwA?si=s9UWoIzS89t0bx50"
            title="YouTube video"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          ></iframe>
        </div>
      </div>
    </div>

    <!-- Content Sections -->
    <About class="bg-black text-white border-b border-gray-800" />
    <Photos class="bg-black border-b border-gray-800" />
    <Contact class="bg-black text-white" />
  </div>
</template>

<style>
@keyframes subtle-shift {
  0% {
    transform: translate(0, 0) scale(1.5);
  }
  50% {
    transform: translate(-1%, 1%) scale(1.5);
  }
  100% {
    transform: translate(0, 0) scale(1.5);
  }
}

.animate-subtle-shift {
  animation: subtle-shift 8s ease-in-out infinite;
}
</style>

