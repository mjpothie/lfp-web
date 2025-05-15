<script setup lang="ts">
import photo1 from '../assets/photos/469528033_470813206033009_2733136312715004689_n.jpg'
import photo2 from '../assets/photos/470183671_474569605657369_189162060557416753_n.jpg'
import photo3 from '../assets/photos/473814008_497709586676704_4221957726168515336_n.jpg'
import photo4 from '../assets/photos/477664638_518735514574111_7413671037468325620_n.jpg'
import photo5 from '../assets/photos/478115000_518735921240737_6203683904853730722_n.jpg'
import photo6 from '../assets/photos/480164625_521064154341247_8542784989500175394_n.jpg'
import photo7 from '../assets/photos/480249237_518747181239611_579585532979415552_n.jpg'
import photo8 from '../assets/photos/480457374_521064114341251_397681042044126080_n.jpg'
import photo9 from '../assets/photos/IMG_2880.jpg'

const photos = [
  { id: 1, src: photo1, alt: 'LFP Band Performance' },
  { id: 2, src: photo2, alt: 'LFP Band Performance' },
  { id: 3, src: photo3, alt: 'LFP Band Performance' },
  { id: 4, src: photo4, alt: 'LFP Band Performance' },
  { id: 5, src: photo5, alt: 'LFP Band Performance' },
  { id: 6, src: photo6, alt: 'LFP Band Performance' },
  { id: 7, src: photo7, alt: 'LFP Band Performance' },
  { id: 8, src: photo8, alt: 'LFP Band Performance' },
  { id: 9, src: photo9, alt: 'LFP Band Performance' }
]
</script>

<template>
  <section id="photos" class="py-24 bg-black">
    <h2 class="text-5xl font-rock text-white mb-12 text-center tracking-wide px-8">Photo Gallery</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 2xl:grid-cols-6 gap-8 px-8">
      <div v-for="photo in photos" :key="photo.id" 
           class="aspect-square overflow-hidden rounded-lg shadow-lg hover:shadow-xl transition-shadow duration-300">
        <img :src="photo.src" :alt="photo.alt" 
             class="w-full h-full object-cover transform hover:scale-105 transition-transform duration-300" />
      </div>
    </div>
  </section>
</template>
