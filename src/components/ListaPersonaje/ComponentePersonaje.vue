<script>
import Personaje from './personaje.vue';
import Lista from './lista.vue';

export default {
    data() {
        return {
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
           this.$options.personaje =  personaje
        },
    }
}
</script>

<template>
    <header>
        <div>
            <Personaje @obtener-personaje="obtener" :id=id />
            <Lista :personaje="this.$options.personaje" />
        </div>
    </header>

    <main>

    </main>
</template>