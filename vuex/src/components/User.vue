<template>
  <div>{{ user.name }}</div>
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
  }
}
</script>

<style>

</style>
