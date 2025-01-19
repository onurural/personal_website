<script setup lang="ts">
import { ref, onMounted } from 'vue'

const pdfUrl = '/resume.pdf'
const pdfLoaded = ref(false)
const pdfObject = ref<HTMLObjectElement | null>(null)

onMounted(() => {
  if (pdfObject.value) {
    pdfObject.value.onload = () => {
      pdfLoaded.value = true
    }
    // Force reload the PDF
    pdfObject.value.data = pdfUrl
  }
})
</script>

<template>
  <div class="resume">
    <div class="resume-header">
      <a :href="pdfUrl" download class="download-button">Download PDF</a>
    </div>

    <div class="pdf-container">
      <iframe :src="pdfUrl" frameborder="0"></iframe>
    </div>
  </div>
</template>

<style scoped>
.resume {
  width: 100vw;
  height: 100vh;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  position: relative;
  left: 50%;
  right: 50%;
  margin-left: -50vw;
  margin-right: -50vw;
}

.resume-header {
  display: flex;
  justify-content: flex-start;
  padding: 2rem;
  width: 100%;
  max-width: 1600px;
  margin: 0 auto;
}

.download-button {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  background-color: #000000;
  color: white;
  text-decoration: none;
  border-radius: 4px;
  font-size: 1.2rem;
  font-weight: 500;
  transition: background-color 0.2s;
  margin-left: 0;
}

.download-button:hover {
  background-color: #333333;
}

.pdf-container {
  flex: 1;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #f5f5f5;
  padding: 0;
  overflow: hidden;
}

iframe {
  width: 100%;
  height: 100%;
  border: none;
}

@media (max-width: 1400px) {
  .resume-header {
    max-width: 1200px;
  }
}

@media (max-width: 768px) {
  .resume-header {
    padding: 1rem;
  }
}
</style>
