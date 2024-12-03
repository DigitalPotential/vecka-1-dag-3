<script setup>
import { ref, onMounted } from 'vue'

// State för API-anrop
const data = ref(null)
const loading = ref(false)
const error = ref(null)

// Funktion för att hämta Pokemon-data från API
const fetchData = async () => {
  loading.value = true
  try {
    const response = await fetch('https://pokeapi.co/api/v2/pokemon?limit=10')
    const json = await response.json()
    data.value = json.results
  } catch (e) {
    error.value = 'Ett fel uppstod vid hämtning av data'
  } finally {
    loading.value = false
  }
}

// Hämta data när komponenten monteras
onMounted(() => {
  fetchData()
})
</script>

<template>
  <div class="data-fetching">
    <h2>Pokemon Lista</h2>
    
    <!-- Loading-indikator -->
    <div v-if="loading" class="loading">
      Laddar Pokemon...
    </div>

    <!-- Felmeddelande -->
    <div v-else-if="error" class="error">
      {{ error }}
    </div>

    <!-- Lista med Pokemon -->
    <div v-else class="pokemon-list">
      <div v-for="pokemon in data" :key="pokemon.name" class="pokemon-card">
        <h3>{{ pokemon.name }}</h3>
        <a :href="pokemon.url" target="_blank">Mer information</a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.pokemon-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 1rem;
}

.pokemon-card {
  border: 1px solid #ddd;
  padding: 1rem;
  border-radius: 8px;
}

.loading, .error {
  text-align: center;
  padding: 2rem;
}
</style> 