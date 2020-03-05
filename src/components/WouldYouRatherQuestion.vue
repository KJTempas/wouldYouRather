<template>
    <div>
        <!-- template goes here -->
 <h1> Would you rather...</h1>

        <would-you-rather-question
            v-bind:question="question"
            v-bind:answer1="answer1"
            v-bind:answer2="answer2"
            v-on:answer-changed="answerChanged">

        </would-you-rather-question>
<!--note: component name is generated from the component, but lowercase w/ hyphens; or camelCase-->
    <div>
        {{ userSelectionMessage }}
    </div>



        </div>
</template>


<script>
export default {
    //create and export component here
    name: 'WouldYouRatherQuestion',
    date() {
        return {

        }
    }
}
</script>

<style>

</style>