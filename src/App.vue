<script setup lang="ts">
import About from './components/About.vue'
import Photos from './components/Photos.vue'
import Contact from './components/Contact.vue'
import Music from './components/Music.vue'
import { ref, onMounted, onBeforeUnmount } from 'vue'

import photo1 from './assets/photos/470183671_474569605657369_189162060557416753_n.jpg'
import photo2 from './assets/photos/IMG_2880.jpg'
import photo3 from './assets/photos/469528033_470813206033009_2733136312715004689_n.jpg'
import photo4 from './assets/photos/478115000_518735921240737_6203683904853730722_n.jpg'

const isMenuOpen = ref(false)
const currentImageIndex = ref(0)
const images = [
  photo1,
  photo2,
  photo3,
  photo4
]

let rotationInterval: number | undefined

const rotateImage = () => {
  if (rotationInterval) {
    clearInterval(rotationInterval)
  }
  currentImageIndex.value = (currentImageIndex.value + 1) % images.length
  // Set interval based on which image is showing
  const nextDuration = currentImageIndex.value === 0 ? 3000 : 3000
  rotationInterval = window.setInterval(rotateImage, nextDuration)
}

onMounted(() => {
  rotationInterval = window.setInterval(rotateImage, 5000) // Start with 5 seconds for first image
})

onBeforeUnmount(() => {
  if (rotationInterval) {
    clearInterval(rotationInterval)
  }
})

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
          <a href="#music" class="py-4 px-2 text-gray-300 hover:text-white transition duration-300">Music</a>
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
            href="#music" 
            @click="closeMenu"
            class="py-3 px-6 text-gray-300 hover:text-white transition duration-300 hover:scale-110"
          >
            Music
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
    <div class="relative max-w-7xl mx-auto overflow-hidden bg-gradient-to-br from-stone-900 via-gray-900 to-black">
      <!-- Background Images -->
      <div class="relative" style="padding-bottom: 66.67%"> <!-- 3:2 aspect ratio for photos -->
        <div class="absolute inset-0">
          <template v-for="(image, index) in images" :key="image">
            <img
              :src="image"
              :style="{
                opacity: currentImageIndex === index ? 1 : 0,
                transition: 'opacity 1s ease-in-out',
                position: 'absolute',
                top: 0,
                left: 0,
                width: '100%',
                height: '100%',
                objectFit: 'cover'
              }"
              :alt="'LFP Band Performance ' + (index + 1)"
            />
          </template>
        </div>

        <!-- Overlay -->
        <div class="absolute inset-0 bg-black bg-opacity-10"></div>

        <!-- Main content -->
        <div class="absolute inset-0 flex items-center justify-center">
          <div class="w-full flex items-center justify-center py-12 md:py-16 lg:py-20">
            <div class="w-full max-w-[80%] md:max-w-2xl lg:max-w-3xl px-4 md:px-8">
              <img 
                src="./assets/lfp-fulllogo-transparent.png" 
                alt="Late For Pickup" 
                class="w-full"
                :style="{
                  opacity: currentImageIndex === 0 ? 1 : 0,
                  transition: 'opacity 1s ease-in-out',
                  filter: `drop-shadow(0 0 10px rgba(255,255,255,0.4))
                          drop-shadow(0 0 20px rgba(255,255,255,0.2))
                          drop-shadow(0 0 30px rgba(0,0,0,0.8))
                          drop-shadow(2px 2px 3px rgba(0,0,0,0.9))`
                }"
              />
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Content Sections -->
    <About class="bg-black text-white border-b border-gray-800" />
    <Photos class="bg-black border-b border-gray-800" />
    <Music class="bg-black text-white border-b border-gray-800" />
    <Contact class="bg-black text-white" />
  </div>
</template>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-to,
.fade-leave-from {
  opacity: 1;
}

.fade-move {
  transition: transform 1s ease;
}


</style>

