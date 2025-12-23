<template>
  <footer class="bg-gray-800 text-white py-12">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex flex-col md:flex-row justify-between items-center">
        <div class="mb-6 md:mb-0">
          <span class="text-xl font-semibold green-accent">Portfolio</span>
          <p class="text-gray-400 mt-2">Building digital experiences that matter</p>
        </div>
        <div class="flex space-x-6">
          <a href="#about" class="text-gray-400 hover:text-white transition" @click.prevent="scrollTo('about')">About</a>
          <a href="#roadmap" class="text-gray-400 hover:text-white transition" @click.prevent="scrollTo('roadmap')">Roadmap</a>
          <a href="#projects" class="text-gray-400 hover:text-white transition" @click.prevent="scrollTo('projects')">Projects</a>
          <a href="#contact" class="text-gray-400 hover:text-white transition" @click.prevent="scrollTo('contact')">Contact</a>
        </div>
      </div>
      <div class="mt-8 pt-8 border-t border-gray-700 text-center text-gray-400">
        <p>© {{ currentYear }} Developer Portfolio. All rights reserved.</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  computed: {
    currentYear() {
      return new Date().getFullYear()
    }
  },
  methods: {
    scrollTo(id) {
      const element = document.getElementById(id)
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' })
      }
    }
  }
}
</script>