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
