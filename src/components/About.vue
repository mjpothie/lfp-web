<script setup lang="ts">
</script>

<template>
  <section id="about" class="py-24 bg-black">
    <h2 class="text-5xl font-rock text-white mb-12 text-center tracking-wide px-8">About LFP</h2>
    <div class="prose prose-lg prose-invert px-8 mb-16">
      <p class="text-gray-300 text-center text-xl mx-auto font-sans max-w-3xl">
        Late For Pickup is a local alternative rock band serving a mix of high-energy and acoustic favorites from the 90s and 2000s - with guaranteed good vibes for all!
      </p>
    </div>

    <!-- YouTube Video Container -->
    <div class="max-w-4xl mx-auto px-8">
      <div class="aspect-video w-full relative shadow-2xl rounded-lg overflow-hidden" 
           style="box-shadow: 0 0 20px rgba(0,0,0,0.5);">
        <iframe
          class="w-full h-full absolute inset-0"
          src="https://www.youtube.com/embed/mLuH5jV-scA"   
          title="Late for Pickup - Promo Video"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
      </div>
    </div>
  </section>
</template>

