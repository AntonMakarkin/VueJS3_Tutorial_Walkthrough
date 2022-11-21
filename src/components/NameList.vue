<template>
    <h3 v-for="name in names" :key="name.firstName">
        <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
    </h3>
</template>

<script>
    export default {
        name: 'NameList',
        data() {
            return {
                names: [
                    {
                        firstName: 'Anton',
                        lastName: 'Makarkin'
                    },
                    {
                        firstName: 'Vika',
                        lastName: 'Shipko'
                    },
                    {
                        firstName: 'Vova',
                        lastName: 'Maksin'
                    }
                ]
            }
        }
    }
</script>

<style scoped>

</style>