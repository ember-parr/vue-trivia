<template>
  <div>
    <button class="difficultyBtn">Easy</button>
    <button class="difficultyBtn">Medium</button>
    <button class="difficultyBtn">Hard</button>
    <button class="difficultyBtn">Show All</button>
    <div class="triviaGame">
      <div v-for="triviaQ in TriviaData" :key="triviaQ.answer" class="triviaCardz">
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
      TriviaData: [...TriviaData]
    };
  },
  methods: {
    flipCard(card) {
      card.answerShown = !card.answerShown;
      console.log("card flipped");
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
</style>
