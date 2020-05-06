<template>
    <div id="user-panel">
        <h3>Witaj {{ authenticatedUserName }}!</h3>
        <button class="button button-outline" @click="logMeOut()">Wyloguj</button>
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
    h3 {
        display: inline;
    }

    button {
        float: right;
    }

    #user-panel {
        padding-bottom: 30px;
    }
</style>