<script>
import Personaje from './personaje.vue';
import Lista from './lista.vue';

export default {
    data() {
        return {
            idPersonaje: null,
            personaje: {},
        }
    },
    props: {
        id: {
            type: Number
        }
    },
    components: { Personaje, Lista },
    methods: {
        obtener(personaje) {
            this.personaje = personaje
        },
        bindearId() {
            this.$props.id = this.$attrs.idPersonaje
            console.log(this.$attrs.idPersonaje)
        }
    }
}
</script>

<template>
    <header>
        <div>{{bindearId()}}
            <Personaje @obtener-personaje="obtener" :id=id />
            <Lista :personaje="this.personaje" />
        </div>
    </header>

    <main>

    </main>
</template>