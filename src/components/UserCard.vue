<template>
  <div class="user-card">
    <div :user="user" v-if="user" class="card" style="width: 18rem;">
        <img class="card-img-top" :src="user.photo" alt="Card image cap">
        <div class="card-body">
          <h5 class="card-title">{{user.firstname}}</h5>
          <p class="card-text">{{user.gender}}</p>
          <a href="#" class="btn btn-primary" @click.prevent="login">Login</a>
        </div>
    </div>
  </div>
</template>

<script>
import users from '../datas/users.json'

export default {
  name: 'UserCard',
  props : {
        user : { type: Object, required : true }
    },
  methods:{
            login(){
                this.$emit("login", this.user)
            }
          },
}
</script>

<style scoped>
h1, h2 {
  font-weight: normal;
}

a {
  color: #42b983;
}

.login{
  text-align: center;
}
</style>
