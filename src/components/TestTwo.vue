<template>
  <div class="test-container">
    <div v-if="currentQuestionIndex < questions.length">
      <h1>Test your knowledge</h1>
      <div class="slide">
        <h2>{{ questions[currentQuestionIndex].text }}</h2>
        <ul>
          <li v-for="(option, optionIndex) in questions[currentQuestionIndex].options" :key="optionIndex">
            <label>
              <input
                type="radio"
                :name="'question_' + currentQuestionIndex"
                :value="optionIndex"
                v-model="selectedOptions[currentQuestionIndex]"
                :disabled="answered"
              />
              {{ option }}
            </label>
          </li>
        </ul>
        <button class="submit-btn" @click="submitAnswer" :disabled="answered">Submit Answer</button>
        <div v-if="answered">
          <p  class="white-text result">You selected: {{ questions[currentQuestionIndex].options[selectedOptions[currentQuestionIndex]] }}</p>
          <p  class="white-text result">Points earned: {{ accumulatedScore[currentQuestionIndex] }}</p>
        </div>
      </div>
      <button class="submit-btn" v-if="answered && currentQuestionIndex < questions.length - 1" @click="nextQuestion">Next Question</button>
    </div>
    <div v-else>
      <h2>Quiz Results</h2>
      <p  class="white-text result">You scored {{ totalScore }} points!</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      questions: [
        {
          text: "What does UX stand for?",
          options: ["User Experience", "User Experiment", "User Xperience", "Universal Experience"],
          correctAnswer: 0,
        },
        {
          text: "Which design principle focuses on simplicity and clarity?",
          options: ["Balance", "Contrast", "Emphasis", "Simplicity"],
          correctAnswer: 3,
        },
        {
          text: "What is the purpose of wireframing in UI/UX design?",
          options: [
            "To create a detailed visual design",
            "To showcase the final product",
            "To plan the layout and structure",
            "To add colors and images",
          ],
          correctAnswer: 2,
        },
      ],
      currentQuestionIndex: 0,
      selectedOptions: [null, null, null], // Array to store user-selected options for each question
      answered: false,
      accumulatedScore: [0, 0, 0],
    };
  },
  computed: {
    totalScore() {
      return this.accumulatedScore.reduce((acc, curr) => acc + curr, 0);
    },
  },
  methods: {
    submitAnswer() {
      // Check if an option is selected
      if (this.selectedOptions[this.currentQuestionIndex] !== null) {
        // Check if the selected option is correct
        const isCorrect =
          this.selectedOptions[this.currentQuestionIndex] === this.questions[this.currentQuestionIndex].correctAnswer;

        // Update accumulated score
        this.accumulatedScore[this.currentQuestionIndex] = isCorrect
          ? this.accumulatedScore[this.currentQuestionIndex] + 10
          : this.accumulatedScore[this.currentQuestionIndex];

        this.answered = true;
      } else {
        alert("Please select an option before submitting your answer.");
      }
    },
    nextQuestion() {
      this.currentQuestionIndex++;
      this.answered = false;
    },
  },
};
</script>

<style scoped>
.slide {
  margin-bottom: 20px;
}
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
