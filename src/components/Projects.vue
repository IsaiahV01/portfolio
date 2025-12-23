<template>
  <section id="projects" class="py-20 bg-white">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16" data-aos="fade-up">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">Featured Projects</h2>
        <p class="text-gray-600 text-lg">Some of my recent work that I'm proud of</p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(project, index) in projects" 
             :key="index" 
             class="project-card bg-white rounded-lg shadow-sm overflow-hidden hover:shadow-xl transition-shadow"
             data-aos="fade-up"
             :data-aos-delay="index * 100">
          <div class="h-48 bg-gradient-to-br overflow-hidden relative" :style="{ backgroundImage: `linear-gradient(to bottom right, ${project.gradient[0]}, ${project.gradient[1]})` }">
            <div class="w-full h-full flex items-center justify-center">
              <i :class="project.icon" class="text-6xl text-white opacity-20"></i>
            </div>
            <!-- Featured badge for live projects -->
            <div v-if="project.liveUrl && project.title !== 'Portfolio Website'" class="absolute top-4 right-4 bg-white/90 backdrop-blur-sm px-3 py-1 rounded-full text-xs font-medium text-green-600 flex items-center gap-1">
              <div class="w-2 h-2 bg-green-500 rounded-full animate-pulse"></div>
              Live
            </div>
            <!-- Special badge for portfolio -->
            <div v-if="project.title === 'Portfolio Website'" class="absolute top-4 right-4 bg-white/90 backdrop-blur-sm px-3 py-1 rounded-full text-xs font-medium text-blue-600 flex items-center gap-1">
              <i class="fas fa-location-dot text-xs"></i>
              You're here!
            </div>
          </div>
          
          <div class="p-6">
            <h3 class="text-xl font-semibold mb-2">{{ project.title }}</h3>
            <p class="text-gray-600 mb-4 text-sm">{{ project.description }}</p>
            
            <div class="flex flex-wrap gap-2 mb-4">
              <span v-for="(tech, techIndex) in project.technologies" 
                    :key="techIndex" 
                    class="bg-gray-100 text-gray-700 text-xs px-2 py-1 rounded">
                {{ tech }}
              </span>
            </div>
            
            <div class="flex space-x-4">
              <!-- Special case for Portfolio project -->
              <template v-if="project.title === 'Portfolio Website'">
                <span class="text-gray-500 italic inline-flex items-center text-sm">
                  <i class="fas fa-map-marker-alt mr-1"></i> You're already here!
                </span>
              </template>
              
              <!-- Normal links for other projects -->
              <template v-else>
                <a v-if="project.liveUrl" 
                   :href="project.liveUrl" 
                   target="_blank"
                   rel="noopener noreferrer"
                   class="text-green-500 hover:text-green-600 transition inline-flex items-center">
                  <i class="fas fa-external-link-alt mr-1"></i> Live Demo
                </a>
                <a v-if="project.videoUrl" 
                   :href="project.videoUrl" 
                   target="_blank"
                   rel="noopener noreferrer"
                   class="text-green-500 hover:text-green-600 transition inline-flex items-center">
                  <i class="fab fa-youtube mr-1"></i> Video
                </a>
              </template>
              
              <!-- GitHub link shows for all projects -->
              <a :href="project.githubUrl" 
                 target="_blank"
                 rel="noopener noreferrer"
                 class="text-green-500 hover:text-green-600 transition inline-flex items-center">
                <i class="fab fa-github mr-1"></i> Code
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Projects',
  data() {
    return {
      projects: [
        {
          title: 'Bring The Rain',
          description: 'Custom website built for a client, featuring modern design and responsive layout for optimal user experience.',
          technologies: ['HTML', 'CSS', 'JavaScript', 'Responsive Design'],
          icon: 'fas fa-cloud-rain',
          gradient: ['#3b82f6', '#60a5fa'],
          liveUrl: 'https://isaiahv01.github.io/bringTheRain/',
          githubUrl: 'https://github.com/IsaiahV01/bringTheRain'
        },
        {
          title: 'Portfolio Website',
          description: 'Modern portfolio website built with Vue.js, featuring smooth animations, responsive design, and gooey navigation.',
          technologies: ['Vue.js', 'Vite', 'Tailwind CSS', 'GitHub Pages'],
          icon: 'fas fa-briefcase',
          gradient: ['#06b6d4', '#22d3ee'],
          liveUrl: 'https://isaiahv01.github.io/portfolio/',
          githubUrl: 'https://github.com/IsaiahV01/portfolio'
        },
        {
          title: 'Equip 4 Destiny',
          description: 'Mockup website designed for Equip 4 Destiny church, featuring modern design, community information, and ministry resources.',
          technologies: ['HTML', 'CSS', 'JavaScript', 'Responsive Design'],
          icon: 'fas fa-church',
          gradient: ['#8b5cf6', '#a78bfa'],
          liveUrl: 'https://isaiahv01.github.io/equip4destiny/',
          githubUrl: 'https://github.com/IsaiahV01/equip4destiny'
        },
        {
          title: 'API Meal Tracker',
          description: 'Meal tracking application leveraging external APIs to provide nutritional information and meal planning features.',
          technologies: ['JavaScript', 'API Integration', 'HTML', 'CSS'],
          icon: 'fas fa-utensils',
          gradient: ['#10b981', '#34d399'],
          videoUrl: 'https://youtu.be/9lDL6M4wO_E',
          githubUrl: 'https://github.com/IsaiahV01/API-Meal-Tracker'
        },
        {
          title: "Mars' Webpage",
          description: 'Website Project for an event hosting business, customized for a unique and engaging user experience.',
          technologies: ['HTML', 'CSS', 'JavaScript', 'Web Design', 'Full Stack Development'],
          icon: 'fas fa-globe-americas',
          gradient: ['#dc2626', '#f87171'],
          videoUrl: 'https://youtu.be/GGuOpn2tGSY',
          githubUrl: 'https://github.com/IsaiahV01/Mars-Webpage'
        },
        {
          title: 'More Projects Coming',
          description: 'Currently working on exciting new projects. Check back soon or visit my GitHub to see what I\'m building!',
          technologies: ['Vue.js', 'React', 'Node.js', 'TypeScript'],
          icon: 'fas fa-code',
          gradient: ['#f59e0b', '#fbbf24'],
          githubUrl: 'https://github.com/IsaiahV01'
        }
      ]
    }
  }
}
</script>

<style scoped>
.project-card {
  transition: all 0.3s ease;
}

.project-card:hover {
  transform: translateY(-5px);
}
</style>