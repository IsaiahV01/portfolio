<template>
  <section id="contact" class="py-20 bg-gray-50">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16" data-aos="fade-up">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">Get In Touch</h2>
        <p class="text-gray-600 text-lg">Have a project in mind? Let's work together!</p>
      </div>
      
      <div class="flex flex-col md:flex-row gap-8">
        <div class="md:w-1/2" data-aos="fade-right">
          <div class="bg-white p-8 rounded-lg shadow-sm">
            <h3 class="text-xl font-semibold mb-6">Contact Information</h3>
            
            <div class="space-y-6">
              <div class="flex items-start">
                <div class="w-10 h-10 rounded-full bg-green-100 flex items-center justify-center mr-4">
                  <i class="fas fa-envelope text-green-500"></i>
                </div>
                <div>
                  <p class="text-sm text-gray-500">Email</p>
                  <p class="font-medium">isaiah.velarde01@gmail.com</p>
                </div>
              </div>
              
              <div class="flex items-start">
                <div class="w-10 h-10 rounded-full bg-green-100 flex items-center justify-center mr-4">
                  <i class="fas fa-phone text-green-500"></i>
                </div>
                <div>
                  <p class="text-sm text-gray-500">Phone</p>
                  <p class="font-medium">(507) 581-4117</p>
                </div>
              </div>
              
              <div class="flex items-start">
                <div class="w-10 h-10 rounded-full bg-green-100 flex items-center justify-center mr-4">
                  <i class="fas fa-map-marker-alt text-green-500"></i>
                </div>
                <div>
                  <p class="text-sm text-gray-500">Location</p>
                  <p class="font-medium">Minnesota</p>
                </div>
              </div>
            </div>
            
            <div class="mt-8">
              <h4 class="text-lg font-medium mb-4">Also find me on</h4>
              <div class="flex space-x-4">
                <a href="https://www.linkedin.com/in/isaiah-velarde-4656a530a/" target="_blank" class="w-10 h-10 rounded-full bg-gray-100 flex items-center justify-center hover:bg-green-100 transition">
                  <i class="fab fa-linkedin text-gray-700"></i>
                </a>
                <a href="https://github.com/IsaiahV01" target="_blank" class="w-10 h-10 rounded-full bg-gray-100 flex items-center justify-center hover:bg-green-100 transition">
                  <i class="fab fa-github text-gray-700"></i>
                </a>
              </div>
            </div>
          </div>
        </div>
        
        <div class="md:w-1/2" data-aos="fade-left">
          <div class="bg-white p-8 rounded-lg shadow-sm h-full">
            <h3 class="text-xl font-semibold mb-6">My Resume</h3>
            
            <div class="border border-gray-200 rounded-lg p-6 mb-6">
              <div class="flex items-start">
                <div class="w-12 h-12 rounded-full bg-green-100 flex items-center justify-center mr-4">
                  <i class="fas fa-file-alt text-green-500"></i>
                </div>
                <div>
                  <h4 class="font-medium mb-1">Isaiah Developer - Resume 2025</h4>
                  <p class="text-sm text-gray-500 mb-3">PDF • 72 KB</p>
                  <div class="flex space-x-2">
                    <span class="bg-green-100 text-green-800 text-xs px-2 py-1 rounded">Frontend</span>
                    <span class="bg-green-100 text-green-800 text-xs px-2 py-1 rounded">UX</span>
                    <span class="bg-green-100 text-green-800 text-xs px-2 py-1 rounded">UI</span>
                  </div>
                </div>
              </div>
            </div>
            
            <p class="text-gray-600 mb-6">
              Download my resume to learn more about my skills, experience, and education background.
            </p>
            
            <button @click="downloadResume" class="w-full bg-green-500 hover:bg-green-600 text-white py-3 rounded-lg font-medium transition flex items-center justify-center">
              <i class="fas fa-download mr-2"></i> Download Resume
            </button>
            
            <div class="mt-8">
              <h4 class="text-lg font-medium mb-4">Other platforms</h4>
              <div class="grid grid-cols-2 gap-4">
                <a href="https://profile.indeed.com/p/isaiahv-u5rk98q" target="_blank" class="flex items-center justify-center bg-gray-100 hover:bg-gray-200 py-3 px-4 rounded-lg transition">
                  <i class="fas fa-briefcase mr-2"></i> Indeed
                </a>
                <a href="https://www.linkedin.com/in/isaiah-velarde-4656a530a/" target="_blank" class="flex items-center justify-center bg-gray-100 hover:bg-gray-200 py-3 px-4 rounded-lg transition">
                  <i class="fab fa-linkedin mr-2"></i> LinkedIn
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contact',
  emits: ['download-resume'],
  methods: {
    downloadResume() {
      this.$emit('download-resume')
      // Actually download the file
      const link = document.createElement('a')
      link.href = '/Isaiah_Velarde_Resume.pdf'
      link.download = 'Isaiah_Velarde_Resume.pdf'
      document.body.appendChild(link)
      link.click()
      document.body.removeChild(link)
    }
  }
}
</script>