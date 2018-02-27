<template>
  <div class="panel">
    <ListMessage :user="user" />
    <Message :user="user" />

</div>
</template>

<script>
import Message from './Message.vue'
import ListMessage from './ListMessage.vue'

export default {
    components: {Message, ListMessage},
    props : {
        user : { type: Object, required : true }
    },
  
}
</script>
<style scoped>

.panel{
  display: flex;
  flex-direction: row;
}

</style>
