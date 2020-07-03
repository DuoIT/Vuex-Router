<template>
  <div id="app">
    <ComHeader v-bind:title="title"/>

    <ListUser v-bind:listUser="listUser"/>

    <ComFooter v-bind:title="title"/>
  </div>
</template>

<script>
import ComHeader from './components/ComHeader'
import ComFooter from './components/ComFooter'
import ListUser from './components/ListUser'
export default {
  name: 'app',
  data () {
    return {
      title: "This is title",
      listUser:
      [
        {id:1, name:'Duong', isActive:true},
        {id:2, name:'Duong', isActive:false},
        {id:3, name:'Duong', isActive:true},
        {id:4, name:'Duong', isActive:false},
      ]
    }
  },
  components: {
    ComHeader,
    ComFooter,
    ListUser
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
