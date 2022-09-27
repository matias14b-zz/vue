<script>
import Personaje from './personaje.vue';
import Lista from './lista.vue';

export default {
    data() {
        return {
            idPersonaje: null,
            personaje: {},
            listaPersonaje: []
        }
    },
    personaje: {
        type: Object
    },
    props: {
        id: {
            type: Number
        }
    },
    components: { Personaje, Lista },
    methods: {
        obtener(personaje) {
            this.$options.personaje = personaje
        },
        bindearId() {
            this.$props.id = this.$attrs.idPersonaje
            console.log(this.$attrs.idPersonaje)
        },
        agregarALista(personaje){
            this.listaPersonaje.push(personaje);
        }
    }
}
</script>

<template>
    <header>
        <div> {{bindearId()}}
            <Personaje @obtener-personaje="obtener" :id=id />
            <Lista :personaje="this.$options.personaje" />
        </div>
    </header>

    <main>

    </main>
</template>