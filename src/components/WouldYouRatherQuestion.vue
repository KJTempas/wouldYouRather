<template>
    <div class="question">
        <!-- template goes here -->
          
 <h1> Would you rather...</h1>
  
        <h2>{{ question }}</h2>
        
        <!--v-on change means when either radio button is changed, the method below is called-->
    <!--on change, call method below and send it id and choice -->
        <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change= 'answerChanged(id, choice)'>
        <label>{{answer1}}</label>

        <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change= 'answerChanged(id, choice)'>
        <label>{{answer2}}</label>
   

    </div>
    
</template>


<script>
export default {
    //create and export component here
    name: 'WouldYouRatherQuestion',
    data() { //data is  a function, and returns an object w/ data in it
        return {   //data is for internal use - belong to this component
            choice: '',
           
        }
    },
    props: {  //props are for data pass IN from parent component (App.vue)
        id: Number,   
        question: String,
        answer1: String,
        answer2: String
    },
    methods: {
        answerChanged(id, choice) { //sending data from child to parent; object of question Id and answer
        let idAndAnswer = {id: this.id, answer: this.choice} //create the data object
            this.$emit('answer-changed', idAndAnswer) //emit (send) it to the parent
        
            
        }
    }
}
</script>

<style>

.question{
    background-color: lightblue
    
}

</style>