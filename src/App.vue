<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>

    <div v-if="authenticatedUserName">
      <h3>Witaj {{ authenticatedUserName }}!</h3>
      <a href="#" @click="logMeOut()">Wyloguj</a>
    </div>
    <div v-else>
      Zaloguj się e-mailem
      <input type="email" v-model="email"/>
      <button @click="logMeIn()">Wchodzę</button>
    </div>

  </div>
</template>

<script>
  import "milligram";
  export default {
    data() {
      return {
        email: '',
        authenticatedUserName: ''
      };
    },

    methods: {
      logMeIn() {
        this.authenticatedUserName = this.email;
        this.email = '';
      },
      logMeOut() {
        this.authenticatedUserName = '';
      }
    }
}
</script>

<style>

</style>
