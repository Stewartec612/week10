<template>
  <div id="app">

    <h1>Would You Rather...</h1>

    <would-you-rather

      v-for="question in questions"
      v-bind:question="questions.question"
      v-bind:answer1="questions.answer1"
      v-bind:answer2="questions.answer2"
      v-on:answer-changed="answerChanged"
    ></would-you-rather>

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
      questions:[
        {
          id: 0,
          question: 'would you rather be incredibly funny or incredibly smart?',
          answer1: 'incredibly funny',
          answer2: 'incredibly smart',
        },
        {
          id: 1,
          question: 'Would you rather have super speed or be able to go invisible?',
          answer1: 'super speed',
          answer2: 'go invisible'
        },
        {
          id: 3,
          question: 'Would you rather brush your teeth with soap or drink sour milk?',
          answer1: 'brush teeth with soap',
          answer2: 'drink sour milk'
        }

      ],
      userSelectionMessage: ''
    }
  },
  methods: {
    
    answerChanged(choice) {
      this.userSelectionMessage = `Thanks! you chose ${ choice }`
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
