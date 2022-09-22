<script setup>
    export default
import personaje from './components/ListaPersonaje/personaje.vue'
import lista from './components/ListaPersonaje/lista.vue'


</script>

<template>
    <header>
        <div class="wrapper">
            <personaje :id="1"></personaje>
            <lista :personaje="jedi" />
            <personaje :id="2" />
        </div>
    </header>

    <main>

    </main>
</template>