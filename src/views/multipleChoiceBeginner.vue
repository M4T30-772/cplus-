<template>
  <div class="question-form">

    <template v-if="currentQuestion">
      <h2>{{ currentQuestion.text }}</h2>

      <form @submit.prevent="submitAnswer">
        <label v-for="(option, key) in ['A', 'B', 'C']" :key="key">
          <input type="radio" v-model="selectedOption" :value="option">
          {{ option }}. {{ currentQuestion['option' + option] }}
        </label>
        <button type="submit">Odgovori</button>
      </form>

    </template>

    <template v-else>
      <div v-if="showResults">
        <h2>Rezultat</h2>
        <p>Točno: {{ correctCount }} / {{ questions.length }}</p>
        <p>Postotak točnosti: {{ (correctCount / questions.length * 100).toFixed(2) }}%</p>
        <button @click="tryAgain">Pokušaj ponovno</button>
      </div>
      <template v-else>

        <p>Nema više pitanja.</p>
      </template>
    </template>
  </div>
</template>

<script>
export default {
  
  data() {
    return {


      currentQuestionIndex: 0,
      selectedOption: null,
      correctCount: 0,
      showResults: false,

/*dodaj jos pitanja, same za drugi oblik */

      questions: [
        {
          text: 'Koji loop koristimo u programskom jeziku C++?',
          optionA: 'until loop',
          optionB: 'do loop',
          optionC: 'for loop',
          correctOption: 'C',
        },
        {
          text: 'Koji ćemo rezultat dobiti ako računamo 5 % 2 u C++?',
          optionA: '2',
          optionB: '1',
          optionC: '3',
          correctOption: 'B',
        },
        {
          text: 'Kako pišemo komentare u C++',
          optionA: '// Comment',
          optionB: ' /* Comment */',
          optionC: '# Comment',
          correctOption: 'C',
        }
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
      if (this.selectedOption !== null) {
        if (this.selectedOption === this.currentQuestion.correctOption) {
          this.correctCount += 1;
        }

        
        this.selectedOption = null;
        this.currentQuestionIndex += 1;

        if (this.currentQuestionIndex === this.questions.length) {
          
          this.showResults = true;
        }
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
