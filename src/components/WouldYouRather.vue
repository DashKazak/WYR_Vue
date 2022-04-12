<template>
  <div class="wyr">
    <h2>Please enter your choice!</h2>
    <h3>{{question}}</h3>
   
    <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="ChoiceMade"><label>{{answer1}}</label>
    <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change="ChoiceMade"><label>{{answer2}}</label>
  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    question: String, 
    answer1: String, 
    answer2: String,
  },
  emits:['answer-changed'],
  data(){
    return{
      choice:''
    }
  },
  methods:{
    ChoiceMade(){
      this.$emit('answer-changed', this.choice,this.id)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
.wyr{
  border: 2px darkblue solid;
  background: lightskyblue;
  margin:10px
}
</style>
