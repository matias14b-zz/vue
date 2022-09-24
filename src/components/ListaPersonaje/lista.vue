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
    components: { Personaje }
}
</script>

<template>
    <ul>
        <li v-for="(value, key) in personaje">
            {{key}}: {{ value }}
        </li>
    </ul>
</template>