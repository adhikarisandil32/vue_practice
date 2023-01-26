<template>
  <userComponent2></userComponent2>
  <ul>
    <li v-for="eachUserData in userData" :key="eachUserData.name">
      <userComponent :eachUserData="eachUserData" :alertUserName="alertUserName" :alertUserEmail="alertUserEmail"/>
    </li>
  </ul>
  <!-- 
    <userComponent :userData="userData"/>
  -->
</template>

<script>
  /* eslint-disable */

import userComponent from './components/userComponents.vue'
import userComponent2 from './components/userComponent2.vue'

  export default{
    components: {
      userComponent,
      userComponent2
    },
    methods:{
      alertUserName(name){
        alert(name);
      },
      alertUserEmail(email){
        alert(email);
      }
    },
    data(){
      return{
        userData:[{
          name: "Ross",
          email: "ross@friends.com"
        },
        {
          name: "Rachel",
          email: "rachel@friends.com"
        },
        {
          name: "Phoebie",
          email: "phoebie@friends.com"
        },
        {
          name: "Chandler",
          email: "chandler@friends.com"
        },
        {
          name: "Monica",
          email: "monica@friends.com"
        },
        {
          name: "Joey",
          email: "joey@friends.com"
        }]
      }
    }
  }

</script>

<style scoped>
  li{
    list-style-type: none;
  }
</style>
