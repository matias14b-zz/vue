<script setup>
import componentePersonaje from './components/ListaPersonaje/ComponentePersonaje.vue'
import lista from './components/ListaPersonaje/lista.vue'
import BuscadorPersonaje from './components/buscadorPersonaje/buscadorPersonaje.vue';
import 'bootstrap'; 
import '../node_modules/bootstrap/dist/css/bootstrap.css'

</script>

<template>
  <header>
    <buscador-personaje></buscador-personaje>
  </header>

  <main>

  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
