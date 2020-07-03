<template>
  <div class="list-user">
    <User v-for="user in listUser"
    v-bind:key="user"
    v-bind:user="user"></User>
  </div>
</template>

<script>
import User from './User'
export default {
  name : "list-user",
  props : {
       listUser :{
        type: Array,
        default : []
      }
  },
  data() {
    return {

    }
  },
  components: {
    User
  }
}
</script>

<style>

</style>
