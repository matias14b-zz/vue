<script>
export default {
    data() {
        return {}
    },
    props:
    {
        personaje: {
            type: Object
        }
    }
}
</script>

<template>
    <ul>
        <li v-for="(value, key) in personaje">
            {{key}}: {{ value }}
        </li>
    </ul>
</template>