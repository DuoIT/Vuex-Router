<template>
<div class="com-tab">
    <div class="tabs-title">
      <span>{{ title }}</span>
      <ion-icon name="heart"></ion-icon>
    </div>
  <div class="list-content">
    <slot></slot>
  </div>
</div>

</template>

<script>
export default {
  name: "com-tab",
  props: {
    title: String
  },
  data() {
    return {

    }
  },
  methods: {

  },
}
</script>

<style>
.tabs-title{
  padding: 15px 30px;
  display: flex;
  justify-content: space-between;
  border: 2px solid #000;
}
.tabs-header{
  margin: 0;
  padding: 0;
  display: flex;
  list-style-type: none;
}
.tabs-header li{
  padding: 8px 15px;
  background-color: #ccc;
}
.tabs-header li:hover {
  color: #fff;
  background-color: #333;
}

.list-content {
  padding: 15px;
  border: 2px solid green;
  text-align: left;
}
</style>
