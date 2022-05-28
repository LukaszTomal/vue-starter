<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcie</h1>
    <div v-if="authenticatedUsername ==''">
      <login-form @login="logMeIn($event)" button-label="Wejdź"></login-form>
    </div>
    <div v-else>
      <log-out-form @logOut="logOut" :email="authenticatedUsername"></log-out-form>
    </div>
  </div>
</template>

<script>
import "milligram"
import LoginForm from "./LoginForm";
import LogOutForm from "./LogOutForm";
export default {
  components: {LoginForm, LogOutForm},
  data()  {
    return {
      authenticatedUsername: '',

    };
  },
  methods: {
    logMeIn(username){
      this.authenticatedUsername = username;
    },
    logOut(){
      this.authenticatedUsername = '';
    }
  }
}
</script>

<style>
.toLong{
  color: red;
}

</style>
