<template>
   
   <div>
<h1>You would rather...</h1>
<ul >
    <li>{{answer}} </li>
</ul>
    </div>
</template>

<script>


export default {
  name: 'Answers',
  props:{
      answers: Array
  },

}
</script>

<style>

</style>