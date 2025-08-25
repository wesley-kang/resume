<script setup lang="ts">
import Resume from './components/Resume.vue'
</script>

<template>
  <div id="app">
    <Resume />
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  line-height: 1.6;
  color: #333;
  background-color: #f5f5f5;
}

html {
  scroll-behavior: smooth;
}

#app {
  min-height: 100vh;
}

/* 打印样式 */
@media print {
  body {
    background: white;
  }
  
  .resume-container {
    box-shadow: none !important;
    max-width: none !important;
  }
  
  .header {
    background: #667eea !important;
    -webkit-print-color-adjust: exact;
  }
}
</style>