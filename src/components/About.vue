<script setup lang="ts">
</script>

<template>
  <section id="about" class="py-24 bg-black">
    <h2 class="text-5xl font-rock text-white mb-12 text-center tracking-wide px-8">About LFP</h2>
    <div class="prose prose-lg prose-invert px-8 mb-16">
      <p class="text-gray-300 text-center text-xl mx-auto font-sans max-w-3xl">
        Late for Pickup delivers exactly what their name promises — three guys who might be rushing from school drop-offs, but never miss a beat when it comes to rocking out!
        <br><br>
        Born in Reading, Massachusetts, LFP shows up with the perfect blend of 90's and 2000's hits that'll make you quickly forget about any real-world responsibilities. 
      </p>
    </div>

    <!-- YouTube Video Container -->
    <div class="max-w-4xl mx-auto px-8">
      <div class="aspect-video w-full relative shadow-2xl rounded-lg overflow-hidden" 
           style="box-shadow: 0 0 20px rgba(0,0,0,0.5);">
        <iframe
          class="w-full h-full absolute inset-0"
          src="https://www.youtube.com/embed/McOiAf8mJwA"
          title="LFP Band Performance"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
      </div>
    </div>
  </section>
</template>

