<template>
  <div id="app">

    <h1 id="topHeader">Would you rather ...</h1>
   <div class="indivQuestion">
    <WouldYouRatherQuestion v-for="question in questions"

      v-bind:key="question.id"    
            v-bind:id= "question.id" 
            v-bind:question= "question.question"  
            v-bind:answer1= "question.answer1"
            v-bind:answer2= "question.answer2"
            v-on:answer-changed= "answerChanged">
    </WouldYouRatherQuestion>
    
    </div>
<br>
    <div id="answers">
    
    <Answers v-for="answer in answers"

      v-bind:key="answer.id"
      v-bind:answer="answer">
   </Answers>
    
    </div>

  </div>
  
  
</template>

<script>
import WouldYouRatherQuestion from './components/WouldYouRatherQuestion.vue'
import Answers from './components/Answers.vue'

export default {
  name: 'App',
  data() {
    return {
      questions: [
       {
          id: 0,
          question: '...be a master at drawing or be an amazing singer?',
          answer1: 'Be a master at drawing',
          answer2: 'Be an amazing singer',
        },
        {
          id: 1,
          question: '...be a famous inventor or a famous writer?',
          answer1: 'Be a famous inventor',
          answer2: 'Be a famous writer',
        },
        {
          id: 2,
          question: '...be able to type/text very fast or be able to read really quickly?',
          answer1: 'Be able to type/text very fast',
          answer2: 'Be able to read really quickly'
        }
      ],
      answers: []  //array of answers
    }
  },
  components: {
    WouldYouRatherQuestion,
    Answers
    
  },
  methods: {
   answerChanged(answer)  { //what does this do?  similar method in WYRQ which emits answer back to parent
      this.anwer = id.answer
      this.answer.push(answers) //add answer to the answers array
    }  
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#answers{
  background-color:palegreen
  
}
.indivQuestion{
  background-color: lightblue
}
#topHeader {
  font-style: italic
}
</style>
