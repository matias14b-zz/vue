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
    <div class="card">
        <div class=card-body>
            <ul class="list-group">
                <li class="list-group-item" v-for="(value, key) in personaje" :key="key">
                    {{key}}: {{ value }}
                </li>
            </ul>
        </div>
    </div>
</template>