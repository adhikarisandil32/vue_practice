<template>
  <!--
    1. :class="{darkmode: true}" would activate the class darkmode and vice versa
    2. darkmodeBoolean contains the value true and false.
    3. Now we want to toggle dark mode on the click of a button. onclick, darkmodeBooleans's value is switched from true to false and vice versa
    4. And the button component's mode is opposite to that of <main> 
  -->
  <main :class="{darkmode: darkmodeBoolean}">
    <HomeComponent></HomeComponent>
    <BodyComponent></BodyComponent>
    <button :class="{darkmode: !darkmodeBoolean}" @click="darkmodeBoolean=!darkmodeBoolean">
      {{toggle()}} Darkmode
    </button>
  </main>
</template>

<script setup>
/*eslint-disable*/
import HomeComponent from './components/HomeComponent.vue'
import BodyComponent from './components/BodyComponent.vue'
import { ref } from 'vue'

//using compositionAPI
let darkmodeBoolean = ref(false)

const toggle = () => {
  return darkmodeBoolean.value? "Disable":"Enable"
}

  //using optionAPI
  /* 
    components: {HomeComponent, BodyComponent},
    data() {
      return{
        darkmodeBoolean: false
      }
    },
    methods: {
      toggle(){
        return this.darkmodeBoolean? "Disable":"Enable"
      }
    }
  */
</script>

<style scoped>
*,
*::after,
*::before {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

main {
  margin: 0 auto;
  width: min(700px, 100%);
  height: 80vh;
  border: 2px solid black;
  padding: 10px;
}

.darkmode {
  background-color: rgb(0, 0, 51);
  color: rgb(202, 202, 202);
}

button{
  position: relative;
  left: 50%;
  transform: translateX(-50%);
  padding: 10px 20px;
  border-radius: 100px;
  cursor: pointer;
}

</style>
