<script>
import Personaje from './personaje.vue';
import Lista from './lista.vue';

export default {
    data() {
        return {}
    },
    props: {
        jedi: {
            type: Object
        },
        id: {
            type: Number
        }
    },
    components: { Personaje, Lista },
    methods: {
        started(){
           console.log("chau")
        }
    }
}
</script>

<template>
    <header>
        <div>
            <Personaje :sending-start="started" :id=id />

        </div>
    </header>

    <main>

    </main>
</template>