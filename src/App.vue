<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Solid Vue Components Demo"/>
    <LoginButton v-on:onSuccess="handleLogin" v-if="!session" />
    <LogoutButton v-on:onSuccess="handleLogout" v-if="session" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import { LoginButton, LogoutButton } from 'solid-vue-components'

export default {
  name: 'app',
  components: {
    HelloWorld, LoginButton, LogoutButton
  },
  data() {
    return {
      session: false
    }
  },
  methods: {
    handleLogin(session) {
      console.log("logged in!")
      this.session = session
    },
    handleLogout() {
      this.session = false
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

button {
  font-weight: bold;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  border-radius: 10px ;
  padding: 15px 30px;
  color: #42b983
}
button:hover {
  cursor: pointer;
  transform: scale(1.1)
}
</style>
