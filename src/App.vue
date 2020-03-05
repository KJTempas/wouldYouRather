<template>
  <div id="app">
    <WouldYouRatherQuestion>v-for="question in questions</WouldYouRatherQuestion>

    
  </div>
</template>

<script>
import WouldYouRatherQuestion from './components/WouldYouRatherQuestion.vue'

export default {
  name: 'App',
  data() {
    return {
      questions: [
        {
          id: 0,
          question: 'be a master at drawing or be an amazing singer?',
          answer1: 'Be a master at drawing',
          answer2: 'Be an amazing singer',
        },
        {
          id: 1,
          question: 'be a famous inventor or a famous writewr?',
          answer1: 'Be a famous inventor',
          answe2: 'Be a famous writer',
        },
        {
          id: 2,
          question: 'be able to type/text very fast or be able to read really quickly?',
          answer1: 'Be able to type/text very fast',
          answer2: 'Be able to read really quickly'
        }
      ]
    }
  },
  components: {
    WouldYouRatherQuestion
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
</style>
