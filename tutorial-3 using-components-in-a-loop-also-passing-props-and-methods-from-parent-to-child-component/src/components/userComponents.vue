<template>
    <div>
        <h4>{{ eachUserData.name }}</h4>
        <h4>{{ eachUserData.email }}</h4>
        <h4>
            <button v-on:click="alertUserName(eachUserData.name)">Alert Name</button>
            <button v-on:click="alertUserEmail(eachUserData.email)">Alert Email</button>
        </h4>
    </div>
</template>

<script>

    export default{
        
        props:{
            eachUserData: Object,
            alertUserName: Function,
            alertUserEmail: Function
        }
    }
</script>

<style scoped>
    div{
        border-bottom: 2px solid black;
        background: lightgreen;
        box-sizing: border-box;
        padding: 0.5rem 2rem 0.5rem;
    }
</style>