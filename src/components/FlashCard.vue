<template>
  <div class="triviaCard">
    <h4>{{ card.question }}</h4>
    <button @click="showAnswer">Show Answer</button>
  </div>
</template>

<script>
export default {
  props: ["card"],
  methods: {
    showAnswer() {
      this.$emit("flip-card", this.card);
    }
  }
};
</script>

<style scoped>
/* .triviaCard {
  border: 2px solid #bc9b8e;
  margin: 20px;
  padding: 15px;
  flex: 1;
} */
</style>
