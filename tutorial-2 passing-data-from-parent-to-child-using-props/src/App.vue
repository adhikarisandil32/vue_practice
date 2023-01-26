<template>
  <Child :msg="msg" :user="user" :getData="getData"/>
</template>

<script>
/*eslint-disable*/

import Child from './components/childComponent.vue'

export default {
  components: {Child},
  data(){
    return {
      user: ["john", "peter", "megan", "stewie", "brian", "brooke", "brian", "quagmire", "cleveland"],
      msg: "This is the child"
    }
  },
  methods:{
    getData(){
      alert("button clicked");
      console.log("button clicked");
    }
  }
}
</script>

<style>

</style>
