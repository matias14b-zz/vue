<script>
import ComponentePersonaje from '../ListaPersonaje/ComponentePersonaje.vue';
export default {
    data() {
        return {
        };
    },
    components: { ComponentePersonaje },
    methods: {
    }
}
</script>
<template>
    <div v-for="idElemento in idElementosBuscados" :key="idElemento.id">
        <ComponentePersonaje :id="idElemento.id"></ComponentePersonaje>
    </div>
</template>