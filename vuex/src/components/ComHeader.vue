<template>
  <div class="com-header">
    <h1>{{ title }}</h1>
    <br/>
    <button v-on:click="changeTitle">Change title</button>
  </div>
</template>

<script>
export default {
  name: "com-header",
  props: {
    title: String
  },
  data() {
    return {

    }
  },
  methods: {
    changeTitle(){
      var data = {
          title : "Dora"
      }
      console.log('title chua change');
      this.$emit('changeTitleEvent',data)
    }

  },
}
</script>

<style>

</style>
