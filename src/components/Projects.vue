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
             class="project-card bg-white rounded-lg shadow-sm overflow-hidden"
             data-aos="fade-up"
             :data-aos-delay="index * 100">
          <div class="h-48 bg-gradient-to-br overflow-hidden" :style="{ backgroundImage: `linear-gradient(to bottom right, ${project.gradient[0]}, ${project.gradient[1]})` }">
            <div class="w-full h-full flex items-center justify-center">
              <i :class="project.icon" class="text-6xl text-white opacity-20"></i>
            </div>
          </div>
          
          <div class="p-6">
            <h3 class="text-xl font-semibold mb-2">{{ project.title }}</h3>
            <p class="text-gray-600 mb-4">{{ project.description }}</p>
            
            <div class="flex flex-wrap gap-2 mb-4">
              <span v-for="(tech, techIndex) in project.technologies" 
                    :key="techIndex" 
                    class="bg-gray-100 text-gray-700 text-xs px-2 py-1 rounded">
                {{ tech }}
              </span>
            </div>
            
            <div class="flex space-x-4">
              <a href="#" class="text-green-500 hover:text-green-600 transition">
                <i class="fas fa-external-link-alt mr-1"></i> Live Demo
              </a>
              <a href="#" class="text-green-500 hover:text-green-600 transition">
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
          title: 'E-Commerce Platform',
          description: 'A full-featured online shopping platform with payment integration and admin dashboard.',
          technologies: ['Vue.js', 'Node.js', 'MongoDB', 'Stripe'],
          icon: 'fas fa-shopping-cart',
          gradient: ['#10b981', '#34d399']
        },
        {
          title: 'Task Management App',
          description: 'Collaborative project management tool with real-time updates and team features.',
          technologies: ['React', 'Firebase', 'Material-UI', 'WebSocket'],
          icon: 'fas fa-tasks',
          gradient: ['#3b82f6', '#60a5fa']
        },
        {
          title: 'Portfolio Website',
          description: 'Modern portfolio template with animations and responsive design.',
          technologies: ['HTML', 'CSS', 'JavaScript', 'AOS'],
          icon: 'fas fa-briefcase',
          gradient: ['#8b5cf6', '#a78bfa']
        },
        {
          title: 'Weather Dashboard',
          description: 'Real-time weather application with beautiful UI and location-based forecasts.',
          technologies: ['Vue.js', 'OpenWeather API', 'Chart.js'],
          icon: 'fas fa-cloud-sun',
          gradient: ['#f59e0b', '#fbbf24']
        },
        {
          title: 'Social Media App',
          description: 'Social networking platform with posts, comments, and user profiles.',
          technologies: ['React Native', 'Express', 'PostgreSQL'],
          icon: 'fas fa-users',
          gradient: ['#ec4899', '#f472b6']
        },
        {
          title: 'Blog Platform',
          description: 'Content management system for bloggers with markdown support.',
          technologies: ['Next.js', 'MDX', 'Tailwind CSS'],
          icon: 'fas fa-blog',
          gradient: ['#06b6d4', '#22d3ee']
        }
      ]
    }
  }
}
</script>