<script setup>
// Importera dag 3 övningskomponenter
import Dag3X1 from './exercises/dag-3-x1.vue'
import Dag3X2 from './exercises/dag-3-x2.vue'
import Dag3X3 from './exercises/dag-3-x3.vue'
</script>

<template>
  <div class="app-container">
    <h1>Dag 3 Övningar</h1>
    
    <!-- v-for övning -->
    <section>
      <h2>Övning 1 - v-for</h2>
      <Dag3X1 />
    </section>

    <!-- Data fetching övning -->
    <section>
      <h2>Övning 2 - Data Fetching</h2>
      <Dag3X2 />
    </section>

    <!-- Composable övning -->
    <section>
      <h2>Övning 3 - Counter Composable</h2>
      <Dag3X3 />
    </section>
  </div>
</template>

<style>
.app-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

section {
  margin-bottom: 40px;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
}

h1 {
  text-align: center;
  margin-bottom: 30px;
}

h2 {
  margin-bottom: 20px;
}
</style> 