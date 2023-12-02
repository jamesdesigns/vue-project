<template>
  <div class="test-container">
    <div>
      <h1>Test your knowledge</h1>
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
    <p class="white-text result" v-if="submitted">
      Your answer is <strong>{{ isCorrect ? 'correct' : 'incorrect' }}</strong>! <br/><br/> <strong>The correct answer is: </strong> <i>{{ choices[3] }}</i>
    </p>
  </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      question: "What is the primary purpose of wireframing in the UX/UI design process?",
      choices: [
        "To create a visually appealing final design",
        "To test the functionality of the website or application",
        "To provide a high-fidelity representation of the user interface",
        "To outline the structure and layout of a design before visual elements are added",
        "To gather user feedback on color schemes and typography"
      ],
      correctAnswerIndex: 3,
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

h1 { color: white; font-size: 3rem; font-weight: bold; margin-bottom: 30px; text-align: center; line-height: 1 !important;}
h2 { color: white; font-size: 2rem;margin-bottom: 30px;  }
li {
  margin-bottom: 10px;
  color: white; 
  font-size: 1.5rem;
}

input { margin-left: 3%; }
.result { margin-top: 5%; font-size: 1.15rem; }

.submit-btn { 
  margin-top: 2%;
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
  box-shadow: none;
}
.white-text { color: white; }
</style>
