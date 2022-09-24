<script>
import ComponentePersonaje from '../ListaPersonaje/ComponentePersonaje.vue';
export default {
    data() {
        return {
            id: null,
            componentePersonaje: [ComponentePersonaje]
        };
    },
    components: { ComponentePersonaje }
    ,
    methods: {
        obtenerId(id) {
            console.log(id.target.value)
            this.id = id.target.value
        },
        add(e) {

            this.componentePersonaje.push({ type: ComponentePersonaje});
        }
    }
}
</script>
<template>
    <input type="text" @input="obtenerId">
    <button @click="add">aaaaaaaaaaaaaaaaaaaa</button>
    <component v-for="element in this.componentePersonaje" :is="element.type" :idPersonaje="this.id" :key="element.id">
    </component>
</template>