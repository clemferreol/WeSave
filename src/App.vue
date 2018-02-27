<template>
  <div id="app">
    <Login v-if="!user" @login="login"/>
    <Chat :user="user" v-if="user"/>
  </div>
</template>

<script>
import Login from './components/Login'
import Chat from './components/Chat'

export default {
  name: 'App',
  components: {
    Login,
    Chat
  },
  data(){
    return{
      user:null
    }
  },
  methods:{
    login(user){
      this.user = user
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
