<script>
import Lista from './lista.vue';

export default {
    data() {
        return {
            dolar: {},
        };
    },
    props: {
        id: {
            type: Number
        },
    },
    emits: ["obtenerDolarHoy"],
    methods: {
        obtenerDolarHoy() {
            fetch(`https://www.dolarsi.com/api/api.php?type=dolar`)
                .then(response => response.json())
                .then(data => this.dolar = data);
        },
    },
    components: { Lista }
}
</script>
    
<template>
    <span>
        {{obtenerDolarHoy()}}
        <Lista :lista="dolar"></Lista>
    </span>
</template>