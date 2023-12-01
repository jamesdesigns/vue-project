<template>
  <div class="test-container">
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
    <p class="white-text" v-if="submitted">
      Your answer is <strong>{{ isCorrect ? 'correct' : 'incorrect' }}</strong>!
    </p>
  </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      question: "What is UX design?",
      choices: [
        "User Experience Design",
        "User eXperience Design",
        "Universal Experience Design",
        "User Exploration Design",
        "User Express Design"
      ],
      correctAnswerIndex: 0,
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
.test-container { display: flex; justify-content: center; margin: 10% auto 0; height: 100vh; }
ul {
  list-style-type: none;
  padding: 0;
  margin-bottom: 30px; 
}
h2 { color: white; font-size: 2rem;margin-bottom: 30px;  }
li {
  margin-bottom: 10px;
  color: white; 
  font-size: 1.5rem;
}
.white-text { color: white; }
</style>
