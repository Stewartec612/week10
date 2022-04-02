<template>
  <div class="wyr">

<!--    <h2>Please make your choice</h2>-->
<!--    incredibly funny or incredibly smart?-->
    <h3>{{ question }}</h3>

    <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="choice">
    <label>{{ answer1 }}</label>

    <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change="choice">
    <label>{{ answer2 }}</label>

  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    question: String,
    answer1: String,
    answer2: String,

  },
  data() {
    return{
      choice: ''
    }
  },
  methods: {
    choiceMade() {
      this.$emit('answer-changed', this.choice)
    },
    questions(){}
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

</style>
