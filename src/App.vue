<template>
  <div>
    <h1>System do zapisów na zajęcia</h1>

    <div v-if="authenticatedUserName">
      <user-panel :authenticated-user-name="authenticatedUserName" @logout="logMeOut()"></user-panel>
    </div>
    <div v-else>
      <login-form @login="logMeIn($event)"></login-form>
    </div>
    <meetings-page v-show="authenticatedUserName"></meetings-page>
  </div>
</template>

<script>
  import "milligram";
  import LoginForm from "./LoginForm";
  import UserPanel from "./UserPanel";
  import MeetingsPage from "./MeetingsPage";

  export default {
    components: {UserPanel, LoginForm, MeetingsPage},

    data() {
      return {
        authenticatedUserName: ''
      };
    },

    methods: {
      logMeIn(username) {
        this.authenticatedUserName = username;
      },
      logMeOut() {
        this.authenticatedUserName = '';
      }
    }
}
</script>

<style>

</style>
