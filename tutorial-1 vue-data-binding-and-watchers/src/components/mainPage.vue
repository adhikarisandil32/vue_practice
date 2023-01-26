<template>
    <main>
        <div class="image">
            <h1>Welcome to VueJS</h1>
            <img src="../assets/logo.png" alt="vue_logo">
        </div>
        <h3>Get Input Field</h3>
        <input type="checkbox" value="php" id="php" v-model="language">
        <label for="php">PHP</label>

        <input type="checkbox" value="javascript" id="javascript" v-model="language">
        <label for="javascript">JavaScript</label>

        <input type="checkbox" value="python" id="python" v-model="language">
        <label for="python">Python</label>

        <input type="checkbox" value="flutter" id="flutter" v-model="language">
        <label for="flutter">Flutter</label>

        <br><br>

        <input type="radio" value="developer" name="profession" id="developer" v-model="profession">
        <label for="developer">Developer</label>

        <input type="radio" value="student" name="profession" id="student" v-model="profession">
        <label for="student">Student</label>

        <br><br>

        <h4>I'm a {{ lastCheckedLanguage }} {{ profession }}</h4>
    </main>
</template>

<script>
export default {
    name: "mainPage",
    data() {
        return {
            language: [],
            profession: null,
            lastCheckedLanguage: '' 
        };
    },
    //method inside watch property (of the same name inside data() property) watches that property inside data() for change. If seen, it executes the code inside that method.
    //language() inside watch watches the language property above. If change occours, it executes lastElement() method.
    watch: {
        language() {
            this.lastElement();
        }
    },
    methods: {
        lastElement() {
            // this.x = this.language.toString(); //to convert the whole array of language to string 
            this.lastCheckedLanguage = this.language.slice(-1).toString(); //to convert last checked element of language array
        }
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans&display=swap');

*,
*::after,
*::before {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Open Sans', sans-serif;
}

main {
    border: 1px solid black;
    width: 800px;
    margin: 0 auto;
    padding: 12px;
}

.image {
    position: relative;
    width: fit-content;
    height: fit-content;
    left: 50%;
    transform: translate(-50%);
}

.image>img {
    width: 100%;
}
</style>
