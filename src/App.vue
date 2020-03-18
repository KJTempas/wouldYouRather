<template>
  <div id="app">

    <h1 id="topHeader">Would you rather ...</h1>
   <!--<div class="indivQuestion">-->
    <WouldYouRatherQuestion v-for="question in questions"

      v-bind:key="question.id"    
            v-bind:id= "question.id" 
            v-bind:question= "question.question"  
            v-bind:answer1= "question.answer1"
            v-bind:answer2= "question.answer2"
            v-on:answer-changed= "answerChanged">
    </WouldYouRatherQuestion>
    
    <h2 id="answerHeader">You would rather...</h2>
   <!-- <p v-for="answer in answers" v-bind:key="answer"> {{answer.answer}} </p> this works but below gives list w/ bullets; bullets on L and text centered-->  
<ul class="answers" v-for="answer in answers" v-bind:key="answer"><li> {{answer.answer}}</li> </ul>  

<!--<Answers v-for="answer in answers" 
    v-bind:key="answer.id"
    v-bind:answer="answers.answer"> <!--binding data in parent to prop in child -->
    

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
      answers: []  //array of answers(and ids?)
    }
  },
  components: {
    WouldYouRatherQuestion,
    Answers
  },
  methods: {
answerChanged(idAndAnswer)  { 
//unpack the object and add it to answers array ?
      //this.answer = idAndAnswer.answer
      //console.log(this.answer) //not getting here
      //this.answers.push(answer) //add answer to the answers array
      this.answers.push(idAndAnswer) //add answer to the answers array
        return answers

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


#topHeader {
  font-style: italic
}
#answerHeader {
  background-color: lightgreen
}
ul {
  list-style-type:square;
  list-style-position: inside
}
.answers {
  color: red;
  font-size: 20px

}

</style>
