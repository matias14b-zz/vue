<script>
import Personaje from './personaje.vue';
import Lista from '../lista.vue';

export default {
    data() {
        return {
            item: {}
        }
    },
    props: {
        id: {
            type: Text
        }
    },
    components: { Personaje, Lista },
    methods: {
        async obtenerItem(itemObtenido) {
            this.item = itemObtenido
        },
    }
}
</script>

<template>
    <div class="card">
        <div class=card-body>
            <Personaje @obtener-personaje="obtenerItem" :id=id />
            <Lista :lista="this.item" />
        </div>
    </div>
</template>