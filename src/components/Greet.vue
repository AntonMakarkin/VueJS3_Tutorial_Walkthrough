<template>
    <h2>
        Hello {{ name }} {{ surname }}
    </h2>
</template>

<script>
    export default {
        name: 'GreetComponent',
        props: ['name', 'surname']
    }
</script>

<style scoped>

</style>