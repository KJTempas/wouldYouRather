<template>
   
   <div id="answerList">
<h1>You would rather...</h1>
<ul>
    <!--<li>{{idAndAnswer.answer}} </li>-->
     <li>{{answers.answer}} </li>
</ul>
    </div>
</template>

<script>
export default {
    //create and export component here
  name: 'Answers',
  
  props:{ //props are data passed in from the parent component
      //idAndAnswer: Object
      //answers: Array
      answer: String
      //answers: Object
      //idAndAnswer: Object
  },

}
</script>

<style>

</style>