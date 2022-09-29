<script>
import ComponentePersonaje from '../ListaPersonaje/ComponentePersonaje.vue';
export default {
    data() {
        return {
            idElementosBuscados: []
        };
    },
    components: { ComponentePersonaje },
    methods: {
        obtenerId() {
            let textoInput = document.querySelector(".textoInput").value;
            this.idElementosBuscados.push({ id: textoInput });
        },
    }
}
</script>
<template>
    <div class="d-flex flex-row">
        <div class="p-2">
            <input type="text" class="textoInput">
            <button class="btn btn-primary" @click="obtenerId">Buscar Personaje</button>
        </div>
    </div>
    <div v-for="idElemento in idElementosBuscados" :key="idElemento.id">
        <ComponentePersonaje :id="idElemento.id"></ComponentePersonaje>
    </div>
</template>