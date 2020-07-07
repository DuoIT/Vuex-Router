<template>
  <div id="app">

    <button v-on:click="title='Dora'">Change</button>
    <ComHeader v-bind:title="title"
    v-on:changeTitleEvent="changeTitleHeader"/>
  <div class="container">
    <ListUser v-bind:listUser="listUser"
    v-on:mainDelete="mainDelete"
    v-on:mainChange="mainChange"
    v-on:mainBack="mainBack"/>
<br/>
    <DemoRef/>
<br/>
    <ListTab/>
    </div>
    <ComFooter v-bind:title="title"/>
  </div>
</template>

<script>
import ComHeader from './components/ComHeader'
import ComFooter from './components/ComFooter'
import ListUser from './components/ListUser'
import DemoRef from './components/Ref'
import ListTab from './components/ListTab'
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
    ListUser,
    DemoRef,
    ListTab
  },
  methods: {
    changeTitleHeader(data){
      this.title = data.title
      console.log('change success', data);
    },
    mainDelete(data){
      var indexDelete = -1
      this.listUser.forEach((u, idx) => {
        console.log(u.id, idx, data.id);
          if(u.id === data.id)
          {
            indexDelete = idx
          }
        console.log(u);
      });
      if(indexDelete != -1){
        this.listUser.splice(indexDelete, 1)
      }
      console.log('delete trong app.vue', data);
    },
    mainChange(data) {
      var indexChange = -1
      this.listUser.forEach((c, idx) => {
          console.log(c.id, idx, data.id);
          if(c.id === data.id)
          {
              indexChange = idx
          }
      })
      if(indexChange != -1)
      {
          this.listUser.name = data.name
      }
      console.log('day la app.vue', data);
    },
    mainBack(data) {
      var indexBack = -1
      this.listUser.forEach((b, idx) => {
        console.log(b.id, idx, indexBack.id);
        if(b.id === indexBack)
        {
              indexBack = idx
        }
      })
      if(indexBack != -1)
      {
          this.listUser.name = data.name
      }
      console.log('day la app.vue', data);

    }
  },
  beforeCreate() {
    console.log('beforaCreate', this.title, document.querySelector('.container'))
  },
  created() {
    // goi API
    console.log('created', this.title, document.querySelector('.container'))
  },
  beforeMount() {
    console.log('beforeMount', this.title, document.querySelector('.container'))
  },
  mounted() {
    console.log('mounted', this.title, document.querySelector('.container'))
  },
  beforeDestroy() {
    console.log('beforeDestroy', this.title, document.querySelector('.container'))
  },

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
