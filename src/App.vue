<template>
  <div id="app">
    <h1>Would you rather...</h1>
    <would-you-rather v-bind:question="wyrQuestion"
    v-bind:answer1="wyrAnswer1"
    v-bind:answer2="wyrAnswer2"
    v-on:answer-changed="answerChanged">
    </would-you-rather>
    <p>{{userSelectionMessage}}</p>
    <!---reference to a template-->
  </div>
  
</template>

<script>

import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data(){
    return{
      wyrQuestion:'Would you rather be able to text/type very fast or read very quickly?',
      wyrAnswer1:'Type',
      wyrAnswer2:'Read',
      userSelectionMessage:' '
    }
  },
  methods:{
    answerChanged(choice){
      this.userSelectionMessage=`Thanks! You chose ${choice}`
    }
  }
}
</script>

<style>
body{
  background: wheat;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
