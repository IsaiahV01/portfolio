<template>
  <section id="about" class="py-20 bg-gradient-to-br from-white to-gray-50">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex flex-col md:flex-row items-center gap-12">
        <!-- Left side - Text content -->
        <div class="md:w-1/2" data-aos="fade-right">
          <div class="inline-block mb-4">
            <span class="bg-green-100 text-green-800 px-4 py-2 rounded-full text-sm font-medium">
              <i class="fas fa-circle text-green-500 text-xs mr-2 animate-pulse"></i>
              Available for Hire
            </span>
          </div>
          
          <h1 class="text-5xl md:text-6xl font-bold mb-4">
            Hi, I'm <span class="green-accent">Isaiah</span>
          </h1>
          <h2 class="text-2xl md:text-3xl font-semibold mb-6 text-gray-700">
            UX/UI Developer
          </h2>
          <p class="text-gray-600 mb-8 text-lg leading-relaxed">
            I build exceptional digital experiences that are fast, accessible, and visually appealing. 
            I specialize in creating responsive, user-friendly applications using modern technologies 
            like Vue.js and React.
          </p>
          
          <!-- Tech Stack Pills -->
          <div class="flex flex-wrap gap-2 mb-8">
            <span class="bg-white border border-green-200 text-gray-700 px-4 py-2 rounded-lg text-sm font-medium shadow-sm">
              <i class="fab fa-vuejs text-green-500 mr-2"></i>Vue.js
            </span>
            <span class="bg-white border border-green-200 text-gray-700 px-4 py-2 rounded-lg text-sm font-medium shadow-sm">
              <i class="fab fa-react text-green-500 mr-2"></i>React
            </span>
            <span class="bg-white border border-green-200 text-gray-700 px-4 py-2 rounded-lg text-sm font-medium shadow-sm">
              <i class="fab fa-js text-green-500 mr-2"></i>JavaScript
            </span>
            <span class="bg-white border border-green-200 text-gray-700 px-4 py-2 rounded-lg text-sm font-medium shadow-sm">
              <i class="fab fa-html5 text-green-500 mr-2"></i>HTML/CSS
            </span>
          </div>
          
          <!-- Buttons -->
          <div class="flex flex-col sm:flex-row gap-4">
            <a href="#projects" class="bg-green-500 hover:bg-green-600 text-white px-8 py-4 rounded-lg font-medium transition shadow-lg hover:shadow-xl inline-flex items-center justify-center" @click.prevent="scrollTo('projects')">
              <i class="fas fa-briefcase mr-2"></i>
              View Projects
            </a>
            <a href="#contact" class="border-2 border-green-500 text-green-500 hover:bg-green-50 px-8 py-4 rounded-lg font-medium transition inline-flex items-center justify-center" @click.prevent="scrollTo('contact')">
              <i class="fas fa-envelope mr-2"></i>
              Contact Me
            </a>
          </div>
        </div>

        <!-- Right side - Decorative element -->
        <div class="md:w-1/2 flex justify-center" data-aos="fade-left">
          <div class="relative w-full max-w-md">
            <!-- Code window mockup -->
            <div class="bg-gray-900 rounded-lg shadow-2xl overflow-hidden">
              <!-- Window header -->
              <div class="bg-gray-800 px-4 py-3 flex items-center gap-2">
                <div class="w-3 h-3 bg-red-500 rounded-full"></div>
                <div class="w-3 h-3 bg-yellow-500 rounded-full"></div>
                <div class="w-3 h-3 bg-green-500 rounded-full"></div>
                <span class="text-gray-400 text-sm ml-4">portfolio.vue</span>
              </div>
              
              <!-- Code content -->
              <div class="p-6 font-mono text-sm">
                <div class="text-purple-400">&lt;template&gt;</div>
                <div class="text-gray-300 ml-4">&lt;<span class="text-green-400">section</span> <span class="text-yellow-400">class</span>=<span class="text-orange-400">"hero"</span>&gt;</div>
                <div class="text-gray-300 ml-8">&lt;<span class="text-green-400">h1</span>&gt;</div>
                <div class="text-blue-400 ml-12">Hi, I'm Isaiah</div>
                <div class="text-gray-300 ml-8">&lt;/<span class="text-green-400">h1</span>&gt;</div>
                <div class="text-gray-300 ml-8">&lt;<span class="text-green-400">p</span>&gt;</div>
                <div class="text-blue-400 ml-12">UX/UI Developer</div>
                <div class="text-gray-300 ml-8">&lt;/<span class="text-green-400">p</span>&gt;</div>
                <div class="text-gray-300 ml-4">&lt;/<span class="text-green-400">section</span>&gt;</div>
                <div class="text-purple-400">&lt;/template&gt;</div>
              </div>
            </div>

            <!-- Floating icons -->
            <div class="absolute -top-6 -right-6 w-16 h-16 bg-green-500 rounded-lg shadow-lg flex items-center justify-center animate-bounce" style="animation: bounce 3s infinite 0.5s;">
              <i class="fas fa-code text-white text-2xl"></i>
            </div>
            <div class="absolute -bottom-6 -left-6 w-16 h-16 bg-green-400 rounded-lg shadow-lg flex items-center justify-center">
              <i class="fas fa-palette text-white text-2xl"></i>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Skills Grid -->
      <div class="mt-20 grid grid-cols-1 md:grid-cols-3 gap-8">
        <div class="text-center p-6 bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow" data-aos="fade-up" data-aos-delay="100">
          <div class="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4">
            <i class="fas fa-laptop-code text-2xl text-green-500"></i>
          </div>
          <h3 class="text-xl font-semibold mb-2">Web Development</h3>
          <p class="text-gray-600">Building responsive and performant web applications with modern frameworks</p>
        </div>
        
        <div class="text-center p-6 bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow" data-aos="fade-up" data-aos-delay="200">
          <div class="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4">
            <i class="fas fa-palette text-2xl text-green-500"></i>
          </div>
          <h3 class="text-xl font-semibold mb-2">UI/UX Design</h3>
          <p class="text-gray-600">Creating intuitive and beautiful user interfaces that enhance user experience</p>
        </div>
        
        <div class="text-center p-6 bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow" data-aos="fade-up" data-aos-delay="300">
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

<style scoped>
@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}
</style>