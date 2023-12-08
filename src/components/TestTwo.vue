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
        <button class="next-btn" v-if="answered && currentQuestionIndex < questions.length - 1" @click="nextQuestion">Next Question</button>

        <div>

      <p class="result">Total Score: {{ totalScore }} / 100</p>
    </div>
        <div v-if="answered">
          <p class="result">You selected: {{ questions[currentQuestionIndex].options[selectedOptions[currentQuestionIndex]] }}</p>
          <p class="result">Points earned: +{{ accumulatedScore[currentQuestionIndex] }}</p>
        </div>
        <div id="answer-question"></div>
      </div>
    </div>

  </div>

</template>

<script>
export default {
  data() {
    return {
      questions: [
        {
          text: "1. What is the primary purpose of wireframing in UI/UX design?",
          options: ["To create a detailed visual design", "To showcase the final product", "To plan the layout and structure", "To add colors and images"],
          correctAnswer: 2,
        },
        {
          text: "2. Which usability testing method involves observing and analyzing users interacting with a product in their natural environment?",
          options: ["A/B Testing", "Remote Usability Testing", "Guerrilla Testing", "Field Studies"],
          correctAnswer: 3,
        },
        {
          text: "3. What does the term 'affordance' refer to in UI design?",
          options: [
            "The visual appeal of a design",
            "The perceived functionality of an object",
            "The alignment of elements on the screen",
            "The overall user experience",
          ],
          correctAnswer: 1,
        },
        {
          text: "4. Which design principle focuses on creating a visual hierarchy to guide users through content?",
          options: [
            "Proximity",
            "Contrast",
            "Alignment",
            "Repetition",
          ],
          correctAnswer: 1,
        },
        {
          text: "5. What does the term 'cognitive load' refer to in UX design?",
          options: [
            "The visual complexity of a design",
            "The amount of information a user can process",
            "The emotional impact of a design",
            "The time it takes for a user to complete a task",
          ],
          correctAnswer: 1,
        },
        {
          text: "6. In the context of UI design, what does the acronym 'CTA' stand for?",
          options: [
            "Creative Typography Approach",
            "Centralized Text Alignment",
            "Call to Action",
            "Color Theory Application",
          ],
          correctAnswer: 2,
        },
        {
          text: "7. What is the purpose of conducting a heuristic evaluation in UX design?",
          options: [
            "To analyze user behavior through analytics",
            "To identify and fix usability issues based on expert reviews",
            "To perform user testing on a prototype",
            "To gather user feedback through surveys",
          ],
          correctAnswer: 1,
        },
        {
          text: "8. Which UX research method is best suited for exploring user needs, behaviors, and motivations?",
          options: [
            "Surveys",
            "Card Sorting",
            "In-depth Interviews",
            "Usability Testing",
          ],
          correctAnswer: 2,
        },
        {
          text: "9. What is the purpose of a personas in UX design?",
          options: [
            "To represent fictional characters for storytelling",
            "To identify and understand the target audience",
            "To create engaging visual elements",
            "To define the color palette for a design",
          ],
          correctAnswer: 1,
        },
        {
          text: "10. Which color scheme uses colors that are adjacent to each other on the color wheel and share a common base color?",
          options: [
            "Analogous",
            "Complementary",
            "Triadic",
            "Monochromatic",
          ],
          correctAnswer: 0,
        },
      ],
      currentQuestionIndex: 0,
      selectedOptions: [null, null, null], // Array to store user-selected options for each question
      answered: false, 
      accumulatedScore: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    };
  },
  computed: {
    totalScore() {
      return this.accumulatedScore.reduce((acc, curr) => acc + curr, 0);
    },
    bestScore() {
      return this.accumulatedScore `Congrats! Well done.`;
    }
  },
  methods: {
    submitAnswer() {
      // Check if an option is selected
      if (this.selectedOptions[this.currentQuestionIndex] !== null) {
        // Check if the selected option is correct
        const isCorrect =
          this.selectedOptions[this.currentQuestionIndex] === this.questions[this.currentQuestionIndex].correctAnswer;

        // Update accumulated score
        if (isCorrect) {
          this.accumulatedScore[this.currentQuestionIndex] += 10 + this.accumulatedScore[this.currentQuestionIndex] * 0.1;
        } else {
          // Reset the accumulated score for consecutive correct answers
          this.accumulatedScore[this.currentQuestionIndex] = 0;
        }

        this.answered = true;
      } else {
        alert("Please select an option before submitting your answer.");
        // Output this text in the page
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
/* Add your component styles here */
.test-container { 
  display: flex; 
  justify-content: center; 
  width: 70%;
  margin: 10% auto 0; 
  height: 100vh; 
}
ul {
  list-style-type: none;
  padding: 0;
  margin-bottom: 30px; 
}

h1 { color: #090909; font-size: 3rem; font-weight: bold; margin-bottom: 60px; text-align: center; line-height: 1 !important;}
h2 { color: #090909; font-size: 2rem;font-weight: bold;margin-bottom: 30px;line-height: 1.4;  }
li {
  margin-bottom: 10px;
  color: #090909; 
  font-size: 1.5rem;
}
p { margin: 5px 0; }

input { margin-left: 3%; }
.result { margin-top: 2%; font-size: 1.15rem; }

.submit-btn { 
  /* margin-top: 2%;
  margin-bottom: 2%;
  padding: 15px 45px; 
  border-radius: 45px; 
  background-color: white; 
  font-size: 1.15rem;
  border: none; 
  cursor: pointer;
    -webkit-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    -moz-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43); */

    color: #090909;
    padding: 0.7em 1.7em;
    font-size: 18px;
    border-radius: 35px;
    background: #e8e8e8;
    border: 1px solid #e8e8e8;
    transition: all .3s;
    box-shadow: 6px 6px 12px #c5c5c5, -6px -6px 12px #ffffff;
}

.next-btn {
  margin-top: 2%;
  margin-left: 1%;
  padding: 15px 45px; 
  border-radius: 45px; 
  background-color: orange; 
  font-size: 1.15rem;
  border: none; 
  cursor: pointer;
    -webkit-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    -moz-box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
    box-shadow: 10px 10px 15px -3px rgba(0,0,0,0.43);
}

.submit-btn:hover {
 background-color: #1488CC;
   /* color: white;
  box-shadow: none; */
  border: 1px solid white;
  color: white;
}
.white-text { color: white; }

@media only screen and (max-width: 768px) {
  .test-container { width: 100%; }
  h2 { line-height: 1.25;}
  }
  .submit-btn {margin-bottom: 20px; margin-right: 10px;}
</style>

