<script setup>
// Importera och använd counter composable
import { useCounter } from './composables/useCounter'

const { count, increment, decrement, reset } = useCounter(0)
</script>

<template>
  <div class="counter">
    <!-- Visa räknarvärde -->
    <h2>Counter: {{ count }}</h2>
    <!-- Knappar för att kontrollera räknaren -->
    <div class="buttons">
      <button @click="decrement">-</button>
      <button @click="increment">+</button>
      <button @click="reset">Reset</button>
    </div>
  </div>
</template>

<style scoped>
.counter {
  text-align: center;
  padding: 2rem;
}

.buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
  margin-top: 1rem;
}

button {
  padding: 0.5rem 1rem;
  font-size: 1.2rem;
  cursor: pointer;
}
</style> 