<template>
  <Transition name="slide">
    <div v-if="show" class="download-notification bg-white p-4 rounded-lg shadow-lg flex items-center">
      <i class="fas fa-download green-accent mr-2"></i>
      <span>Resume downloaded successfully!</span>
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
}

.slide-enter-active,
.slide-leave-active {
  transition: all 0.5s ease;
}

.slide-enter-from {
  transform: translateX(300px);
}

.slide-leave-to {
  transform: translateX(300px);
  opacity: 0;
}
</style>