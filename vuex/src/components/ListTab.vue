<template>
  <div class="list-tab">
  <ComTab title="This is tab title">
  <ul class="tabs-header">
    <li
      v-for="(e, index) in tabHeader"
      v-bind:key="index"
      v-on:click="setActiveTab(index)"
      v-bind:class="{ active:tabActive == index}"
    >{{ e.text }}</li>
  </ul>
  <div class="list-tab-contenttab1" v-if="tabActive === 0">
  <p>Tab1 - Take some control of the image that's displayed.
  Include a lock query string parameter and give it a
  value that's a positive integer. While our cache is not updated,
  and sometimes for longer, the same image will be returned by our server.</p>
  </div>
  <div class="list-tab-contenttab2" v-if="tabActive === 1"><p>Tab2 - Take some control of the image that's displayed.
  Include a lock query string parameter and give it a
  value that's a positive integer. While our cache is not updated,
  and sometimes for longer, the same image will be returned by our server.
  When using icons in Ionic Framework you can specify different icons per platform.
   Use the md and ios attributes and provide the platform specific icon/variant name.
   When using icons in Ionic Framework you can specify different icons per platform.
   Use the md and ios attributes and provide the platform specific icon/variant name.</p>
  </div>
  <div class="list-tab-contenttab3" v-if="tabActive === 2"><p>Tab3 - Take some control of the image that's displayed.
  Include a lock query string parameter and give it a
  value that's a positive integer. While our cache is not updated,
  and sometimes for longer, the same image will be returned by our server.</p>
  </div>
  <div class="list-tab-contenttab4" v-if="tabActive === 3"><p>Tab4 - Take some control of the image that's displayed.
  Include a lock query string parameter and give it a
  value that's a positive integer.</p>
  </div>
  </ComTab>
  </div>
</template>

<script>
import ComTab from './ComTab'
export default {
  name: "list-tab",
  data() {
    return {
      tabHeader:[
        {text: "Tab1"},
        {text: "Tab2"},
        {text: "Tab3"},
        {text: "Tab4"}
        ],
        tabActive:0
    }
  },
  components:{
    ComTab
  },
  methods: {
    setActiveTab(index) {
      console.log('setActive', index);

      this.tabActive = index
    }
  },
}
</script>

<style>
.list-tab{
  margin-top: 100px;
  padding: 100px 30px;
  border: 1px solid #000;
}
</style>



