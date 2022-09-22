<script setup>
import personaje from './components/ListaPersonaje/personaje.vue'
import lista from './components/ListaPersonaje/lista.vue'


</script>

<template>
  <header>
    <!-- <div class="wrapper">
      <personaje :id="1"></personaje>
      <lista :personaje="jedi" />
      <personaje :id="2" />
    </div> -->
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
