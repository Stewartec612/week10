<template>
  <div class="wyr">

    <h2>Would you rather?:</h2>
    <!--    incredibly funny or incredibly smart?-->
    <!--load each question in the questions array -->
    <ul id="question-list" class="wyr-list">
      <li v-for="(id, question, answer1, answer2) in questions">
        {{ id }} {{ question }} {{ answer1 }} {{ answer2 }}
      </li>


  </ul>
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
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
.wyr{
  border: 2px black solid;
}

</style>
