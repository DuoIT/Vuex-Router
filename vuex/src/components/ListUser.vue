<template>
  <div class="list-user">
    <User v-for="user in listUser"
    v-bind:key="user.id"
    v-bind:user="user"
    v-on:deleteUser="deleteUser"
    v-on:changeUser="changeUser"
    v-on:backUser="backUser"
    ></User>
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
  },
  methods: {
    deleteUser(data) {
      console.log('Delete listUser',data)
      this.$emit('mainDelete',data)
    },
    changeUser(data) {
      console.log('change User', data);
      this.$emit('mainChange', data)
    },
    backUser(data) {
      console.log('back listUser', data);
      this.$emit('mainBack', data)
    }
  },
}
</script>

<style>
.list-user{
  display: flex;
  justify-content: center;
}
</style>
