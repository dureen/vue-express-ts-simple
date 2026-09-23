<script setup lang="ts">
import { ref, onMounted } from 'vue';

const message = ref('Loading...');
const health = ref('');

onMounted(async () => {
  try {
    const [helloRes, healthRes] = await Promise.all([
      fetch('/api/hello'),
      fetch('/api/health'),
    ]);
    const helloData = await helloRes.json();
    const healthData = await healthRes.json();
    message.value = helloData.message;
    health.value = healthData.status;
  } catch (err) {
    message.value = 'Failed to fetch from API';
    health.value = 'error';
  }
});
</script>

<template>
  <div class="container">
    <h1>Vue + Express + TypeScript</h1>
    <p class="message">{{ message }}</p>
    <p class="health">API Status: <span :class="health">{{ health }}</span></p>
  </div>
</template>

<style scoped>
.container {
  font-family: system-ui, sans-serif;
  max-width: 600px;
  margin: 4rem auto;
  text-align: center;
  padding: 2rem;
  border-radius: 12px;
  background: #f8fafc;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
}

h1 {
  color: #1e293b;
  margin-bottom: 1.5rem;
}

.message {
  font-size: 1.25rem;
  color: #334155;
  margin-bottom: 1rem;
}

.health {
  font-size: 0.95rem;
  color: #64748b;
}

.health .ok {
  color: #16a34a;
  font-weight: 600;
}

.health .error {
  color: #dc2626;
  font-weight: 600;
}
</style>
