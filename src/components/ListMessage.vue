<template>
    <div class="list-message">
        <div class="nav"><p class="title">Messenger <i class="fas fa-edit text"></i></p></div>
        <div class="list-group">
          <a href="#" class="list-group-item list-group-item-action flex-column align-items-start ">
            <div class="d-flex w-100 justify-content-between">
              <p class="mb-1">{{user.firstname}}</p>
              <small>11h</small>

            </div>
            <small>Debut du message...</small>
          </a>
          <a href="#" class="list-group-item list-group-item-action flex-column align-items-start">
            <div class="d-flex w-100 justify-content-between">
              <p class="mb-1">{{user.firstname}}</p>
              <small>11h</small>
            </div>
            <small>Debut du message...</small>
          </a>
          <a href="#" class="list-group-item list-group-item-action flex-column align-items-start">
            <div class="d-flex w-100 justify-content-between">
              <p class="mb-1">{{user.firstname}}</p>
              <small>11h</small>
            </div>
            <small>Debut du message...</small>
          </a>
    </div>
    </div>
</template>

<script>
export default {
    name: 'ListMessage',
    props : {
        user : { type: Object, required : true }
    },
}
</script>
<style scoped>

.list-message{
    width: 30%;
    border-style: solid;
    border-width: 1px;
    border-color: gray;
    height: 800px;
    display: inline-block;
}

.nav{
    height: 50px;
    width: 100%;
    border-bottom: gray solid 1px;
}

.title {
    height: 50px;
    width: 100%;
    padding: 10px;
    text-align: center;
}

.text{
    float: right;
    padding: 3px;
    color:#1998e6;
    font-size: 20px;
}

ul{
    list-style-type: none;
    width: 100%;
    /*border-bottom: gray solid 1px;*/
}

li {
    padding: 5px;
    width: 100%;
    margin-left: -40px;
    height: 60px;
    border-bottom: gray solid 1px;
}

.list-group{
  width: 100%;
  background-color: white;
}

.list-group p {

}

</style>
