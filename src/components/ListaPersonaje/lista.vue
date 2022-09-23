<script>
import Personaje from './personaje.vue';
export default {
    data() {
        return {};
    },
    props: {
        personaje: {
            type: Object
        }
    },
    methods: {
        obtener() {
            console.log(Personaje)
        }
    },
    components: { Personaje }
}
</script>

<template>
    <ul>
        <Personaje @hola="obtener"></Personaje>
        <li v-for="(value, key) in personaje">
            {{key}}: {{ value }}
        </li>
    </ul>
</template>