<template>
  <section id="roadmap" class="py-20 bg-gray-50">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16" data-aos="fade-up">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">My Journey</h2>
        <p class="text-gray-600 text-lg">From learning the fundamentals to building real-world projects; Here's how my journey in web development continues to grow!</p>
      </div>
      
      <div class="relative timeline">
        <div v-for="(item, index) in roadmapItems" :key="index" 
             class="roadmap-item mb-12 flex flex-col md:flex-row items-center" 
             :class="index % 2 === 0 ? 'md:flex-row' : 'md:flex-row-reverse'"
             data-aos="fade-up"
             :data-aos-delay="index * 100">
          <div class="md:w-1/2 mb-4 md:mb-0" :class="index % 2 === 0 ? 'md:pr-8 md:text-right' : 'md:pl-8'">
            <div class="bg-white p-6 rounded-lg shadow-sm">
              <span class="text-green-500 font-medium">{{ item.year }}</span>
              <h3 class="text-xl font-semibold mt-2 mb-2">{{ item.title }}</h3>
              <p class="text-gray-600">{{ item.description }}</p>
              <div class="roadmap-details mt-4">
                <div class="flex flex-wrap gap-2" :class="index % 2 === 0 ? 'md:justify-end' : ''">
                  <span v-for="(tech, techIndex) in item.technologies" 
                        :key="techIndex" 
                        class="bg-green-100 text-green-800 text-xs px-2 py-1 rounded">
                    {{ tech }}
                  </span>
                </div>
              </div>
            </div>
          </div>
          
          <div class="w-12 h-12 bg-green-500 rounded-full flex items-center justify-center z-10 shadow-lg md:absolute md:left-1/2 md:transform md:-translate-x-1/2">
            <i :class="item.icon" class="text-white"></i>
          </div>
          
          <div class="md:w-1/2"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Roadmap',
  data() {
    return {
      roadmapItems: [
        {
          year: '2026',
          title: 'Next Step: Expanding and Growing Professionally',
          description: 'Continuing to refine my freelance work while pursuing opportunities to join a forward-thinking team. Focused on   deepening my frontend and UX expertise to build seamless, high-performing digital experiences.',
          technologies: ['Vue 3', 'React', 'UI/UX Design', 'Web Performance', 'Design Systems'],
          icon: 'fas fa-rocket'
        },
        {
          year: '2024 - Current',
          title: 'Freelance Frontend Developer',
          description: 'Currently designing and developing websites for freelance clients — blending clean design with modern, scalable frontend builds.',
          technologies: ['Vue.js', 'React', 'UI Libraries', 'Figma', 'LLM Tools'],
          icon: 'fas fa-code'
        },
        {
          year: '2024',
          title: 'Information Systems AAS Degree',
          description: 'Graduated specializing in web technologies and user experience design.',
          technologies: ['Web Developement', ' Web Design', 'PC Hardware / Software', 'Adobe Creative Clouds'],
          icon: 'fas fa-graduation-cap'
        },
        {
          year: '2021',
          title: 'Undergraduate',
          description: 'Started my journey in web development, learning modern frameworks and best practices.',
          technologies: ['HTML', 'CSS', 'JavaScript', 'Python', 'PHP'],
          icon: 'fas fa-user-graduate'
        }
      ]
    }
  }
}
</script>

<style scoped>
.timeline {
  position: relative;
}

@media (min-width: 768px) {
  .timeline::before {
    content: '';
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 2px;
    height: 100%;
    background-color: #10b981;
  }
}
</style>