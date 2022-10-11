<script>
export default {
    props: {
        lista: {
            type: Object
        }
    },
}
</script>

<template>
    <div>
        <ul class="list-group">
            <li class="list-group-item" v-for="(value, key) in lista" :key="key">
                {{key}}: {{ value }}
            </li>
        </ul>
    </div>
</template>