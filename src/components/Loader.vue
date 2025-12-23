<template>
  <div class="loader">
    <div class="loader-circle"></div>
  </div>
</template>

<script>
export default {
  name: 'Loader'
}
</script>

<style scoped>
.loader {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100vw;
  height: 100vh;
  background-color: #f5f5f5;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
  transition: opacity 0.5s ease;
}

.loader-circle {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  border: 5px solid rgba(16, 185, 129, 0.2);
  border-top-color: #10b981;
  animation: spin 1s linear infinite;
  /* Extra centering insurance */
  margin: auto;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}
</style>