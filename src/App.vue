<template>
  <div id="app">
    <h1>Would you rather...</h1>
    
    <would-you-rather
    
    v-for="question in questions" v-bind:key="question"
    v-bind:question="question.wyrQuestion"
    v-bind:answer1="question.wyrAnswer1"
    v-bind:answer2="question.wyrAnswer2"
    v-bind:id="question.id"
    v-on:answer-changed="answerChanged">
    </would-you-rather>
    <div class="userSelection">
      <h3>Your answers:</h3>
      <ul>
        <li v-bind="id">{{userSelectionMessage}}</li>
      </ul>
    </div>

    <!---using v-for to iterate through the questions. There are 3 objects in the array of questions (3 questions in array named question) and I binded each object to its app.-->
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
      //array of questions and answers
      questions:[
        {
        id:0,
        wyrQuestion:'Would you rather be able to text/type very fast or read very quickly?',
        wyrAnswer1:'Type',
        wyrAnswer2:'Read',
        //userSelectionMessage1:''
        },
        {
        id:1,
        wyrQuestion:'Would you rather be able to travel full-time or have a really comfortable house?',
        wyrAnswer1:'Travel',
        wyrAnswer2:'House',
        //userSelectionMessage2:''
        },
        {
        id:2,
        wyrQuestion:'Would you rather find your perfect times for sleep and always wake up rested or be able to always cook a delicious meal quickly?',
        wyrAnswer1:'Optimal Sleeping',
        wyrAnswer2:'Delicious meal each time',
        //userSelectionMessage3:' '
        }
      ],
      userSelectionMessage:[]
    }
  },
  methods:{
    answerChanged(choice,id){
      this.id=id
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
