<template>
  <div class="login">
    <div v-for="(user, i) in users" :key="i" class="user-list">
         <UserCard :user="user" v-if="user"  @login="loginUser"/>
       </div>
  </div>
</template>

<script>
import users from '../datas/users.json'
import UserCard from './UserCard.vue'

export default {
  components: {UserCard},
  name: 'Login',
  data () {
         return {
             users : users,
         }
     },
    methods:{
          loginUser(user){
                this.$emit("login", user)
            },
          }
}
</script>

<style scoped>

a {
  color: #42b983;
}

.login{
  text-align: center;
}

.user-list{
  display: inline-block;
  margin:50px;
}
</style>
