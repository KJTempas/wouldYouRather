<template>
    <div>
        <!-- template goes here -->
 <h1> Would you rather...</h1>

        <would-you-rather-question
            
            v-bind:question= "question"
            v-bind:answer1= "answer1"
            v-bind:answer2= "answer2"
            v-on:answer-changed= "answerChanged"><!--this links the method to event in child component-->
        <!-- when child emits the answer-changed event, this method is called-->
        <!--v-binding question and answers from parent data to child props-->
        </would-you-rather-question>


<!--note: component name is generated from the component, but lowercase w/ hyphens; or camelCase-->
   <div>
        <h2>{{ question }}</h2>
        <!--v-on change means when either radio button is changed, the event is emitted to the parent-->
        <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="$emit('answer-changed', choice)">
        <label>{{answer1}}</label>
        <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change="$emit('answer-changed', choice)">
        <label>{{answer2}}</label>
    </div>



    </div>
</template>


<script>
export default {
    //create and export component here
    name: 'WouldYouRatherQuestion',
    data() { //data is  a function, and returns an object w/ data in it
        return {
            choice: ''
        }
    },
    props: {
        //id: Number,  //not needed?
        question: String,
        answer1: String,
        answer2: String
    },
    methods: {
        answerChanged() {
            console.log('event emitted from child')
            this.$emit('answer', answer)
            
        }
    }
}
</script>

<style>

</style>