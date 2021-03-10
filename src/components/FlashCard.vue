<template>
  <div>
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

<style scoped></style>
