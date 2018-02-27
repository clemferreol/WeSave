<template>
<div class="chat">
    <p>
        Welcome {{user.firstname}}
    </p>
</div>
</template>

<script>
export default {
    props : {
        user : { type: Object, required : true }
    },
}
</script>
