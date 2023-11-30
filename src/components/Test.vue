<template>
  <div>
    <h2>{{ question }}</h2>
    <ul>
      <li v-for="(choice, index) in choices" :key="index">
        <label>
          <input type="radio" v-model="selectedChoice" :value="index" :disabled="submitted" />
          {{ choice }}
        </label>
      </li>
    </ul>
    <button @click="submitAnswer" :disabled="submitted">Submit Answer</button>
    <p v-if="submitted">Your answer is {{ isCorrect ? 'correct' : 'incorrect' }}!</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      question: "What is the capital of France?",
      choices: ["Berlin", "London", "Paris", "Madrid"],
      correctAnswerIndex: 2,
      selectedChoice: null,
      submitted: false,
      isCorrect: false,
    };
  },
  methods: {
    submitAnswer() {
      if (this.selectedChoice !== null) {
        this.isCorrect = this.selectedChoice === this.correctAnswerIndex;
        this.submitted = true;
      }
    },
  },
};
</script>

<style scoped>
/* Add your component styles here */
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin-bottom: 10px;
}
</style>
