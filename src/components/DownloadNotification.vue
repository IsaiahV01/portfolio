<template>
  <Transition name="slide">
    <div v-if="show" class="download-notification rounded-lg shadow-lg flex items-center" :class="notificationClass">
      <i :class="iconClass" class="mr-3"></i>
      <div>
        <p class="font-semibold">{{ title }}</p>
        <p class="text-sm opacity-90">{{ message }}</p>
      </div>
    </div>
  </Transition>
</template>

<script>
export default {
  name: 'DownloadNotification',
  props: {
    show: {
      type: Boolean,
      default: false
    },
    type: {
      type: String,
      default: 'success', // 'success' or 'error'
      validator: (value) => ['success', 'error'].includes(value)
    }
  },
  computed: {
    notificationClass() {
      return this.type === 'success' 
        ? 'bg-green-500 text-white' 
        : 'bg-red-500 text-white'
    },
    iconClass() {
      return this.type === 'success'
        ? 'fas fa-check-circle text-2xl'
        : 'fas fa-exclamation-circle text-2xl'
    },
    title() {
      return this.type === 'success'
        ? 'Resume Downloaded!'
        : 'Download Failed'
    },
    message() {
      return this.type === 'success'
        ? 'Check your downloads folder'
        : 'Please try again or contact me'
    }
  }
}
</script>

<style scoped>
.download-notification {
  position: fixed;
  top: 20px;
  right: 20px;
  z-index: 1000;
  padding: 1rem 1.5rem;
  min-width: 300px;
}

.slide-enter-active,
.slide-leave-active {
  transition: all 0.5s ease;
}

.slide-enter-from {
  transform: translateX(400px);
  opacity: 0;
}

.slide-leave-to {
  transform: translateX(400px);
  opacity: 0;
}
</style>