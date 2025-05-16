<script setup lang="ts">
</script>

<template>
  <section id="contact" class="py-24 bg-black">
    <h2 class="text-5xl font-rock text-white mb-12 text-center tracking-wide px-8">Contact Us</h2>
    <div class="max-w-2xl mx-auto px-8 mb-12">
      <p class="text-gray-300 text-center">
        Send us a message on <a href="https://www.facebook.com/lateforpickup" target="_blank" rel="noopener noreferrer" class="text-blue-400 hover:text-blue-300 transition-colors duration-300">Facebook</a> or use the form below to get in touch!
      </p>
    </div>
    <div class="px-8">
      <form action="https://formspree.io/f/mgekzggg" method="POST" class="space-y-6 font-sans max-w-2xl mx-auto">
        <div>
          <label for="name" class="block text-sm font-medium text-gray-300">Name</label>
          <input type="text" id="name" name="name" required
                 class="mt-1 block w-full px-3 py-2 bg-gray-900 border border-gray-700 rounded-md shadow-sm text-white focus:outline-none focus:ring-indigo-500 focus:border-indigo-500" />
        </div>
        <div>
          <label for="email" class="block text-sm font-medium text-gray-300">Email</label>
          <input type="email" id="email" name="email" required
                 class="mt-1 block w-full px-3 py-2 bg-gray-900 border border-gray-700 rounded-md shadow-sm text-white focus:outline-none focus:ring-indigo-500 focus:border-indigo-500" />
        </div>
        <div>
          <label for="message" class="block text-sm font-medium text-gray-300">Message</label>
          <textarea id="message" name="message" rows="4" required
                    class="mt-1 block w-full px-3 py-2 bg-gray-900 border border-gray-700 rounded-md shadow-sm text-white focus:outline-none focus:ring-indigo-500 focus:border-indigo-500"></textarea>
        </div>
        <div>
          <button type="submit"
                  class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-gray-800 hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-gray-500">
            Send Message
          </button>
        </div>
      </form>
    </div>
  </section>
</template>
