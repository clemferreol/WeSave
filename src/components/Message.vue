<template>
<div class="message">
	<div class="nav-message"><p class="title-message">Prénom</p></div>
    <ul >
        <li v-for="(message, index) in messages" :class="(currentUser.firstname === message.name ? 'me':'him')">{{message.msg }}</li>
    </ul>
    <form v-on:submit.prevent="sendMessage()">
      <input v-model="newMessage" type="text" placeholder="Écrivez un message..." />
      <button class="waves-effect waves-light btn">Envoyer</i></button>
    </form>
</div>
</template>

<script>
export default {

	name: 'Message',
  props : {
      user : { type: Object, required : true }
  },
  data () {
    return{
      messages : [],
      newMessage:'',
      currentUser: this.user
    }
  },

    methods : {
        sendMessage : function() {
        let text = this.newMessage.trim();
        this.messages.push({name: this.currentUser.firstname, msg: text});
        sessionStorage.setItem('messages',JSON.stringify(this.messages));
        },
     },
     created() {
        this.messages =  JSON.parse(sessionStorage.getItem('messages'));
      },
      watch: {
      getMessage: function () {
        this.messages =  JSON.parse(sessionStorage.getItem('messages'));
      }
    }

}
</script>
<style scoped>
.message{
    width:100%;
    border: 1px solid gray;
    height: 800px;
    min-height: 800px;
    display: inline-block;
    overflow:auto;
}
.nav-message{
    height: 50px;
    width: 100%;
    border-bottom: gray solid 1px;
    position: fixed;
    background-color: white;
}

.title-message{
    text-align: center;
}
ul{
  list-style: none;
  margin: 0;
  padding: 0;
}

ul li{
  display:inline-block;
  clear: both;
  padding: 20px;
  border-radius: 30px;
  margin-bottom: 2px;
  font-family: Helvetica, Arial, sans-serif;
}

li:first-child{
  margin-top: 60px;
}

li:last-child{
  margin-bottom: 60px;
}

.him{
  background: #eee;
  float: left;
}

.me{
  float: right;
  background: #0084ff;
  color: #fff;
}

.him + .me{
  border-bottom-right-radius: 5px;
}

.me + .me{
  border-top-right-radius: 5px;
  border-bottom-right-radius: 5px;
}

.me:last-of-type {
  border-bottom-right-radius: 30px;
}

input{
    display: inline-block;
    /*margin-top: 620px;*/
    position: fixed;
    bottom: 0;
    border-top: 1px gray solid;
    border-right: none;
    border-left: none;
    width: 60%;
    height: 50px;

}

.btn{
  display: inline-block;
  margin-bottom: 2px;
  margin-left: -50px;
  height: 50px;
  width: 8%;
  color:#0283FF;

}

</style>
