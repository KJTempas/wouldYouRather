<template>
   
   <div id="answerList">
<h1>You would rather...</h1>
<ul>
    <li>{{idAndanswer}} </li>
</ul>
    </div>
</template>

<script>


export default {
  name: 'Answers',
  props:{ //props are data passed in from the parent component
      idAndAnswer: Array
  },

}
</script>

<style>

</style>