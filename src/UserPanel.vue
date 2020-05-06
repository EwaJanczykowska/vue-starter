<template>
    <div>
        <h3>Witaj {{ authenticatedUserName }}!</h3>
        <a href="#" @click="logMeOut()">Wyloguj</a>
    </div>
</template>

<script>
    export default {
        props: ['authenticatedUserName'],
        methods: {
            logMeOut() {
                this.$emit('logout');
            }
        }

    }
</script>

<style scoped>

</style>