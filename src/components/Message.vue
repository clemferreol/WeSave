<template>
<div class="message">
	<div class="nav-message"><p class="title-message">Prénom</p></div>
    <ul>
      <li class="him">By Other User</li>
      <li class="me">By this User, first message</li>
      <li class="me">By this User, secondmessage</li>
      <li class="me">By this User, third message</li>
      <li class="me">By this User, fourth message</li>
      <li class="him">By Other User</li>
      <li class="me">By this User, first message</li>
      <li class="me">By this User, secondmessage</li>
      <li class="me">By this User, third message</li>
      <li class="me">By this User, fourth message</li>
      <li class="him">By Other User</li>
      <li class="me">By this User, first message</li>
      <li class="me">By this User, secondmessage</li>
      <li class="me">By this User, third message</li>
      <li class="me">By this User, fourth message</li>
    </ul>
    <input type="text" placeholder="Écrivez un message..." />
</div>
</template>

<script>
export default {
	name: 'Message',
    props : {
        user : { type: Object, required : true }
    },
}
</script>
<style scoped>
.message{
    width:100%;
    border: 1px solid gray;
    height: 800px;
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
    margin-bottom: 0;
    float: left;
    width: 100%;
    height: 50px;
}

</style>
