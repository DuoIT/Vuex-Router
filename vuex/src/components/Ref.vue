<template>
    <div class="demo-ref">
    <h1>Demo-Ref</h1>
    <button
          v-on:click="handleClickInput"
          class="avatar">
          Change Avatar
    </button>
    <input
          ref="fileInputAvatar"
          type="file"
          style="display: none">
    </div>
</template>

<script>
export default {
  name: "demo-ref",
  data() {
    return {

    }
  },
  methods: {
    handleClickInput() {
      console.log(this.$refs.fileInputAvatar.click())
    }
  },
}
</script>


<style>
.demo-ref{
  margin-top: 100px;
  padding: 100px 30px;
  border: 1px solid black;
}
.avatar{
  padding: 12px 15px;
  color: white;
  border: 2px solid black;
  background-color: black;
  transition: all .3s ease;
}
.avatar:hover {
  color: #333;
  background-color: white;
}
</style>
