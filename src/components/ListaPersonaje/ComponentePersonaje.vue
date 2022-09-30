<script>
import Personaje from './personaje.vue';
import Lista from './lista.vue';

export default {
    data() {
        return {
            item: {}
        }
    },
    personaje: {
        type: Object
    },
    props: {
        id: {
            type: Text
        }
    },
    components: { Personaje, Lista },
    methods: {
        async obtener(personaje) {
            this.item = personaje
        },
    }
}
</script>

<template>
    <header>
        <div>
            <Personaje @obtener-personaje="obtener" :id=id />
            <Lista :personaje="this.item" />
        </div>
    </header>

    <main>

    </main>
</template>