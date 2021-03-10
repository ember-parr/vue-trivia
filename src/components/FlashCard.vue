<template>
  <div>
    <h4>{{ card.question }}</h4>
    <span v-if="card.answerShown === true">
      <p>{{ card.answer }}</p>
    </span>
    <button @click="showAnswer">
      {{ card.answerShown ? "Hide Answer" : "Show Answer" }}
    </button>
  </div>
</template>

<script>
export default {
  props: ["card"],
  data() {
    return {};
  },
  methods: {
    showAnswer() {
      this.$emit("flip-card", this.card);
    }
  }
};
</script>

<style scoped></style>
