<template>
  <div class="test-container">
    <div>
      <h1>Test your knowledge.</h1>
    <h2>{{ question }}</h2>
    <ul>
      <li v-for="(choice, index) in choices" :key="index">
        <label>
          <input type="radio" v-model="selectedChoice" :value="index" :disabled="submitted" />
          {{ choice }}
        </label>
      </li>
    </ul>
    <button class="submit-btn" @click="submitAnswer" :disabled="submitted">Submit Answer</button>
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
h1 { color: white; font-size: 3rem; margin-bottom: 30px;}
h2 { color: white; font-size: 2rem;margin-bottom: 30px;  }
li {
  margin-bottom: 10px;
  color: white; 
  font-size: 1.5rem;
}

.submit-btn { 
  padding: 15px 45px; 
  border-radius: 45px; 
  background-color: white; 
  font-size: 1.15rem;
  border: none; 
  cursor: pointer;
    -webkit-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    -moz-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
}

.submit-btn:hover {
  background-color: #1488CC;
  color: white;
}
.white-text { color: white; }
</style>
