<script setup>
// Exempel på listor för v-for demonstration
const simpleList = ['Äpple', 'Banan', 'Citron']
const objectList = [
  { id: 1, name: 'Produkt 1', price: 99 },
  { id: 2, name: 'Produkt 2', price: 149 },
  { id: 3, name: 'Produkt 3', price: 199 }
]
</script>

<template>
  <div class="lists">
    <!-- Enkel lista med strängar -->
    <h2>Fruktlista</h2>
    <ul>
      <li v-for="(fruit, index) in simpleList" :key="index">
        {{ fruit }}
      </li>
    </ul>

    <!-- Lista med objekt visad som kort -->
    <h2>Produkter</h2>
    <div class="cards">
      <div 
        v-for="product in objectList" 
        :key="product.id" 
        class="card"
      >
        <h3>{{ product.name }}</h3>
        <p>Pris: {{ product.price }} kr</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 1rem;
}

.card {
  border: 1px solid #ddd;
  padding: 1rem;
  border-radius: 8px;
}
</style> 