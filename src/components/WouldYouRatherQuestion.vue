<template>
    <div>
        <!-- template goes here -->
 <h1> Would you rather...</h1>
  
        <h2>{{ question }}</h2>
        
        <!--v-on change means when either radio button is changed, the event is emitted to the parent-->
        <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="$emit('answer-changed', choice)">
        <label>{{answer1}}</label>
        <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change="$emit('answer-changed', choice)">
        <label>{{answer2}}</label>
   

    </div>
</template>


<script>
export default {
    //create and export component here
    name: 'WouldYouRatherQuestion',
    data() { //data is  a function, and returns an object w/ data in it
        return {   //data is for internal use - belong to this component
            choice: ''
           // idAndAnswer: '' //not sure about this
        }
    },
    props: {  //props are for data pass IN from parent component (App.vue)
        id: Number,  
        question: String,
        answer1: String,
        answer2: String
    },
    methods: {
        answerChanged(id, answer) { //sending data from child to parent; object of question Id and answer
        let idAndAnswer = {id: this.id, answer: this.answer}
            console.log('event emitted from child')
            this.$emit('idAndAnswer', idAndAnswer)
            //this.$emit('answer', answer)
            
        }
    }
}
</script>

<style>

</style>