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
    <div>
        <div class="card">
            <ul class=card-body>
                <li v-for="(value, key) in personaje" :key="key">
                    {{key}}: {{ value }}
                </li>
            </ul>
        </div>
    </div>
</template>