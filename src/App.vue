<template>
  <div id="app">

    <h1 id="topHeader">Would you rather ...</h1>
    <WouldYouRatherQuestion v-for="question in questions"

      v-bind:key="question.id"    
            v-bind:id= "question.id" 
            v-bind:question= "question.question"  
            v-bind:answer1= "question.answer1"
            v-bind:answer2= "question.answer2"
            v-on:answer-changed= "answerChanged">
    </WouldYouRatherQuestion>
    

    <h2 id="answerHeader">You would rather...</h2>
    <ul class="answers" v-for="answer in answers" v-bind:key="answer"><li> {{answer.answer}}</li> </ul>  
<!--<ul class="answers" v-for="answer in answers" v-bind:key="answer.id"><li> {{answer.answer}}</li> </ul>  -->

  </div>
</template>

<script>//importing components
import WouldYouRatherQuestion from './components/WouldYouRatherQuestion.vue'


export default {
  name: 'App',
  data() { //data is a function 
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
      answers: []  //array of answers and ids
    }
  },
  components: {
    WouldYouRatherQuestion,
  },
  methods: {
answerChanged(idAndAnswer)  { //this method is fed idAndAnswer from the child component
//perhaps this is where you make sure that id is already in answers
      
      this.answers.push(idAndAnswer) //add answer to the answers array -original
//console.log('answers and length', answers, answers.length) //original
       return answers //original

    } //original
    //trying to catch duplicates
    //for (let i=0; i<answers.length; i++) {
     // console.log(answers[i].id)
    //  if (answers[i].id === idAndAnswer.id) {
     //   alert('You have already answered that question')
     // } else {
     //   this.answers.push(idAndAnswer)
    //  return answers  
    //  }

      }
    }
    


  //}
//}
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
