<template>
  <nav class="bg-white shadow-sm sticky top-0 z-50">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16">
        <div class="flex items-center">
          <span class="text-xl pr-1">Isaiah</span><span class="text-xl font-semibold green-accent">Velarde</span>
        </div>
        <div class="hidden md:flex items-center space-x-8">
          <a href="#about" class="text-gray-700 hover:text-green-500 transition" @click.prevent="scrollTo('about')">About</a>
          <a href="#roadmap" class="text-gray-700 hover:text-green-500 transition" @click.prevent="scrollTo('roadmap')">Roadmap</a>
          <a href="#projects" class="text-gray-700 hover:text-green-500 transition" @click.prevent="scrollTo('projects')">Projects</a>
          <a href="#contact" class="text-gray-700 hover:text-green-500 transition" @click.prevent="scrollTo('contact')">Contact</a>
        </div>
        <div class="md:hidden flex items-center">
          <button @click="toggleMobileMenu" class="text-gray-700 text-xl">
            <i :class="mobileMenuOpen ? 'fas fa-times' : 'fas fa-bars'"></i>
          </button>
        </div>
      </div>
    </div>
    <!-- Mobile menu - NOW WITH OVERLAY! -->
    <Transition name="slide-fade">
      <div v-if="mobileMenuOpen" class="mobile-menu-overlay md:hidden">
        <div class="mobile-menu-content bg-white shadow-lg">
          <div class="px-4 pt-4 pb-6 space-y-2">
            <a href="#about" class="block px-4 py-3 rounded-md text-base font-medium text-gray-700 hover:bg-green-50 hover:text-green-500 transition" @click="scrollToAndClose('about')">About</a>
            <a href="#roadmap" class="block px-4 py-3 rounded-md text-base font-medium text-gray-700 hover:bg-green-50 hover:text-green-500 transition" @click="scrollToAndClose('roadmap')">Roadmap</a>
            <a href="#projects" class="block px-4 py-3 rounded-md text-base font-medium text-gray-700 hover:bg-green-50 hover:text-green-500 transition" @click="scrollToAndClose('projects')">Projects</a>
            <a href="#contact" class="block px-4 py-3 rounded-md text-base font-medium text-gray-700 hover:bg-green-50 hover:text-green-500 transition" @click="scrollToAndClose('contact')">Contact</a>
          </div>
        </div>
      </div>
    </Transition>
  </nav>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'Navigation',
  setup() {
    const mobileMenuOpen = ref(false)

    const toggleMobileMenu = () => {
      mobileMenuOpen.value = !mobileMenuOpen.value
    }

    const scrollTo = (id) => {
      const element = document.getElementById(id)
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' })
      }
    }

    const scrollToAndClose = (id) => {
      scrollTo(id)
      mobileMenuOpen.value = false
    }

    return {
      mobileMenuOpen,
      toggleMobileMenu,
      scrollTo,
      scrollToAndClose
    }
  }
}
</script>

<style scoped>
/* Mobile menu overlay - positioned absolutely so it doesn't push content */
.mobile-menu-overlay {
  position: absolute;
  top: 100%;
  left: 0;
  right: 0;
  width: 100%;
  z-index: 40;
}

.mobile-menu-content {
  border-top: 1px solid #e5e7eb;
}

/* Smooth slide and fade animation */
.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.2s ease-in;
}

.slide-fade-enter-from {
  transform: translateY(-10px);
  opacity: 0;
}

.slide-fade-leave-to {
  transform: translateY(-10px);
  opacity: 0;
}
</style>