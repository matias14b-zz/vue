<script>
import ComponentePersonaje from '../ListaPersonaje/ComponentePersonaje.vue';
export default {
    data() {
        return {
            id: null,
        };
    },
    components: { ComponentePersonaje }
    ,
    methods: {
        obtenerId(id) {
            this.id = id.target.value
        },
    }
}
</script>
<template>
    <div class="d-flex flex-row">
        <div class="p-2">
            <input type="text" @input="obtenerId">
        </div>
        <div class="p-2">
            <button class="btn btn-primary" @click="add">Buscar Personaje</button>
        </div>
    </div>
    <ComponentePersonaje :id="this.id"></ComponentePersonaje>
</template>