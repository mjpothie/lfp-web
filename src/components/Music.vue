<script setup lang="ts">
const artists = [
  "Bush",
  "Van Halen",
  "Blink 182",
  "The Cure",
  "Pearl Jam",
  "Green Day",
  "Foo Fighters",
  "R.E.M.",
  "Creed",
  "Red Hot Chili Peppers",
  "Weezer",
  "The Killers",
  "Jimmy Eat World",
  "Rolling Stones",
  "Fountains of Wayne",
  "3rd Eye Blind",
  "Nirvana",
  "Stone Temple Pilots",
  "Smashing Pumpkins",
  "U2",
  "Ramones",
  "Metallica"
]
</script>

<template>
  <section id="music" class="py-24 bg-black">
    <h2 class="text-5xl font-rock text-white mb-12 text-center tracking-wide px-8">Music</h2>
    
    <!-- Band Description -->
    <div class="max-w-4xl mx-auto px-8">
      <div class="prose prose-lg prose-invert mx-auto text-center mb-12">
        <p class="text-gray-300 text-center text-xl mx-auto font-sans max-w-3xl">
        From grunge to pop-punk, classic rock to alternative, we cover rock favorites that span multiple decades!
        </p>
      </div>

      <!-- Artist List -->
      <div class="mt-12 max-w-2xl mx-auto">
        <h3 class="text-2xl font-rock text-white mb-6 text-center">Artists We Cover</h3>
        <div class="grid grid-cols-2 md:grid-cols-3 gap-y-3 gap-x-8 text-left">
          <div v-for="artist in artists" 
               :key="artist"
               class="text-gray-300">
            • {{ artist }}
          </div>
        </div>
      </div>
    </div>
    
  </section>
</template>
