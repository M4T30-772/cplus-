<template>

  <div class="question-form">
    <template v-if="currentQuestion">
      
      <h2>{{ currentQuestion.text }}</h2>
      <form @submit.prevent="submitAnswer">
        <label>
          Tvoj odgovor: <input type="text" v-model="userAnswer">
        </label>
        <button type="submit">Odgovori</button>
      </form>
    </template>

    <template v-else>

      <div v-if="showResults">
        <h2>Rezultat</h2>
        <p>Točnost: {{ correctCount }} / {{ questions.length }}</p>
        <p>Postotak točnosti: {{ (correctCount / questions.length * 100).toFixed(2) }}%</p>
        <button @click="tryAgain">Pokušaj ponovno</button>
      </div>
      <template v-else>
        <p>No more questions.</p>

      </template>

    </template>
  </div>

</template>

<script>
export default {

  data() {
    return {

      currentQuestionIndex: 0,
      userAnswer: '',
      correctCount: 0,
      showResults: false,
      questions: [
        {
          text: 'Što znači akronim C++?',
          correctAnswer: 'C Plus Plus',
        },
        {
          text: 'Koja je naredba za ispis teksta u programskom jeziku C++?',
          correctAnswer: 'cout',
        },
        {
          text: 'Kako definiramo constantu u C++',
          correctAnswer: 'const',
        },
        
        
      ],
    };
  },
  computed: {
    currentQuestion() {
      return this.questions[this.currentQuestionIndex];
    },
  },
  methods: {
    submitAnswer() {
      const userAnswerLowerCase = this.userAnswer.toLowerCase().trim();
      const correctAnswerLowerCase = this.currentQuestion.correctAnswer.toLowerCase().trim();

      if (userAnswerLowerCase === correctAnswerLowerCase) {
        this.correctCount += 1;
      }

      
      this.userAnswer = '';
      this.currentQuestionIndex += 1;

      if (this.currentQuestionIndex === this.questions.length) {
        
        this.showResults = true;
      }
    },
    tryAgain() {
      this.currentQuestionIndex = 0;
      this.correctCount = 0;
      this.showResults = false;
    },
  },
};
</script>

<style scoped>

.question-form {
  background-color: #b3e0f2; 
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  text-align: center;
}

h2 {
  color: #333;
}

form {
  margin-top: 20px;
}

label {
  display: block;
  margin-bottom: 10px;
}

input {
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
}

button {
  background-color: #3498db;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #2980b9;
}
</style>
