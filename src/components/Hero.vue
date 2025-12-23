<template>
  <section id="about" class="py-20 bg-white">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex flex-col md:flex-row items-center">
        <div class="md:w-1/2 mb-10 md:mb-0" data-aos="fade-right">
          <h1 class="text-4xl md:text-5xl font-bold mb-4">
            Hi, I'm <span class="green-accent">Isaiah</span>
          </h1>
          <h2 class="text-2xl md:text-3xl font-semibold mb-6">UX/UI Developer</h2>
          <p class="text-gray-600 mb-8 text-lg">
            I build exceptional digital experiences that are fast, accessible, and visually appealing. 
            I specialize in creating responsive, user-friendly applications using modern technologies.
          </p>
          <div class="flex space-x-4">
            <a href="#projects" class="bg-green-500 hover:bg-green-600 text-white px-6 py-3 rounded-lg font-medium transition" @click.prevent="scrollTo('projects')">
              View Projects
            </a>
            <a href="#contact" class="border border-green-500 text-green-500 hover:bg-green-50 px-6 py-3 rounded-lg font-medium transition" @click.prevent="scrollTo('contact')">
              Contact Me
            </a>
          </div>
        </div>
        <div class="md:w-1/2 flex justify-center" data-aos="fade-left">
          <div class="relative">
            <div class="w-64 h-64 md:w-80 md:h-80 rounded-full bg-green-100 flex items-center justify-center overflow-hidden">
              <img src="http://static.photos/technology/640x360/42" alt="Developer" class="w-full h-full object-cover">
            </div>
            <div class="absolute -bottom-4 -right-4 bg-green-500 text-white px-6 py-3 rounded-lg font-medium shadow-lg">
              <i class="fas fa-code mr-2"></i> Available for Hire
            </div>
          </div>
        </div>
      </div>
      
      <div class="mt-20 grid grid-cols-1 md:grid-cols-3 gap-8">
        <div class="text-center p-6 bg-gray-50 rounded-lg" data-aos="fade-up" data-aos-delay="100">
          <div class="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4">
            <i class="fas fa-laptop-code text-2xl text-green-500"></i>
          </div>
          <h3 class="text-xl font-semibold mb-2">Web Development</h3>
          <p class="text-gray-600">Building responsive and performant web applications with modern frameworks</p>
        </div>
        
        <div class="text-center p-6 bg-gray-50 rounded-lg" data-aos="fade-up" data-aos-delay="200">
          <div class="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4">
            <i class="fas fa-palette text-2xl text-green-500"></i>
          </div>
          <h3 class="text-xl font-semibold mb-2">UI/UX Design</h3>
          <p class="text-gray-600">Creating intuitive and beautiful user interfaces that enhance user experience</p>
        </div>
        
        <div class="text-center p-6 bg-gray-50 rounded-lg" data-aos="fade-up" data-aos-delay="300">
          <div class="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4">
            <i class="fas fa-rocket text-2xl text-green-500"></i>
          </div>
          <h3 class="text-xl font-semibold mb-2">Performance</h3>
          <p class="text-gray-600">Optimizing applications for speed, accessibility, and best practices</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Hero',
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