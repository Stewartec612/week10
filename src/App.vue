<template>
  <div id="app">

    <h1>Would You Rather...</h1>

    <would-you-rather v-bind:question="questions.question"
    v-bind:answer1="questions.answer1"
    v-bind:answer2="questions.answer2"
    v-on:answer-changed="answerChanged"></would-you-rather>

    <p>{{ userSelectionMessage }}</p>

  </div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data(){
    return {
      questions: [
        {
          id: 1,
          question: 'be incredibly funny or incredibly smart?',
          answer1: 'incredibly funny',
          answer2: 'incredibly smart',
        },
        {
          id: 2,
          question:'have super strength or super speed?',
          answer1: 'super strength',
          answer2: 'super speed'
        },
        {
          id: 3,
          question: 'live in the past or the future?',
          answer1: 'the past',
          answer2: 'the future'
        }
        ]
      }
    },
  methods:{

    answerChanged(choice){
      this.userSelectionMessage = `You chose: ${choice}`
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
</style>
