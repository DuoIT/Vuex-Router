<template>
  <div class="user">
  <h3 class="user1">{{ user.name }}</h3>
   <button
          v-on:click="handleDelete"
          class="delete">
          Delete
    </button>
    <button
          v-on:click="handleChange"
          class="change">
          Change
    </button>
    <button
          v-on:click="handleBack"
          class="back">
          Back
    </button>
  </div>
</template>

<script>
export default {
  name : "user",
  props: {
    user : {
      type: Object,
      default: null
    }
  },
  data() {
    return {

    }
  },
  methods: {
    handleDelete(e){
      var data = {
          id: this.user.id
      }
        console.log('trong user.vue')
        this.$emit('deleteUser', data)
    },
    handleChange() {
      var data = {
        name: this.user.name = "Dora"
      }
      console.log('trong user.vue',data);

      this.$emit('changeUser', data)
    },
    handleBack() {
      var data = {
        name: this.user.name = "Duong"
      }
      console.log('day la use.vue');
      this.$emit('backUser')
    }
  },
}
</script>

<style>

.user1{
  margin: 30px;
  padding: 30px;
  border: 2px solid black;
}
.delete{
  margin-left: 40px;
}
.change{
  margin-right: 40px;
}
.back{
  margin-right: 40px;
}
</style>
