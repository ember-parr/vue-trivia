<template>
  <div>
    <button class="difficultyBtn" @click="filter('easy')">Easy</button>
    <button class="difficultyBtn" @click="filter('medium')">Medium</button>
    <button class="difficultyBtn" @click="filter('hard')">Hard</button>
    <button class="difficultyBtn" @click="filter('')">Show All</button>
    <p class="resetLink" @click="resetCards">Hide all answers</p>
    <div class="triviaGame">
      <div
        v-for="triviaQ in filteredTrivia"
        :key="triviaQ.answer"
        class="triviaCardz"
      >
        <flash-card :card="triviaQ" @flip-card="flipCard" />
      </div>
    </div>
  </div>
</template>

<script>
import { TriviaData } from "../assets/trivia.js";
import FlashCard from "./FlashCard.vue";

export default {
  components: { FlashCard },
  data() {
    return {
      TriviaData: [...TriviaData],
      filteredTrivia: TriviaData
    };
  },
  methods: {
    flipCard(card) {
      card.answerShown = !card.answerShown;
    },
    filter(difficulty) {
      if (!difficulty) {
        console.log("all trivia show now... ");
        this.filteredTrivia = this.TriviaData;
      } else {
        console.log("difficulty is: " + difficulty);
        console.table(this.filteredTrivia);
        this.filteredTrivia = this.TriviaData.filter(
          t => t.difficulty === `${difficulty}`
        );
      }
      return this.filteredTrivia;
    },
    resetCards() {
      this.filteredTrivia.forEach(triviaCard => {
        triviaCard.answerShown = false;
      });
    }
  }
};
</script>

<style>
.triviaCardz {
  border: 2px solid #bc9b8e;
  margin: 20px;
  padding: 15px;
  min-width: 250px;
  flex: 1;
}
.triviaGame {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.difficultyBtn {
  padding: 20px;
  margin: 20px;
  background-color: #bc9b8e;
  border: none;
  border-radius: 20px;
}
.resetLink {
    text-decoration: underline;
}
</style>
