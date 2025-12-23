<template>
  <div>
    <!-- Loader Animation -->
    <Loader v-if="isLoading" />
    
    <!-- Download Notification -->
    <DownloadNotification :show="showNotification" />
    
    <!-- Navigation -->
    <Navigation />
    
    <!-- Hero Section -->
    <Hero />
    
    <!-- Roadmap Section -->
    <Roadmap />
    
    <!-- Projects Section -->
    <Projects />
    
    <!-- Contact Section -->
    <Contact @download-resume="handleDownload" />
    
    <!-- Footer -->
    <Footer />
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'
import Loader from './components/Loader.vue'
import DownloadNotification from './components/DownloadNotification.vue'
import Navigation from './components/Navigation.vue'
import Hero from './components/Hero.vue'
import Roadmap from './components/Roadmap.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Loader,
    DownloadNotification,
    Navigation,
    Hero,
    Roadmap,
    Projects,
    Contact,
    Footer
  },
  setup() {
    const isLoading = ref(true)
    const showNotification = ref(false)

    onMounted(() => {
      setTimeout(() => {
        isLoading.value = false
      }, 1500)
    })

    const handleDownload = () => {
      showNotification.value = true
      setTimeout(() => {
        showNotification.value = false
      }, 3000)
    }

    return {
      isLoading,
      showNotification,
      handleDownload
    }
  }
}
</script>

<style>
.green-accent {
  color: #10b981;
}

.bg-green-accent {
  background-color: #10b981;
}

.border-green-accent {
  border-color: #10b981;
}

.roadmap-item:hover .roadmap-details {
  opacity: 1;
  transform: translateY(0);
}

.roadmap-details {
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.3s ease;
}

.project-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
}

.project-card {
  transition: all 0.3s ease;
}

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

@keyframes spin {
  to { transform: rotate(360deg); }
}

:root {
  /* Solid green for all particles - no gradient! */
  --color-1: #22c55e;
  --color-2: #22c55e;
  --color-3: #22c55e;
  --color-4: #22c55e;
}
</style>