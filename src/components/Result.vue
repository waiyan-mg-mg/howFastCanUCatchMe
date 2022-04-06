<template>
  <p class="result">
    You have caught within <span>{{ score }} </span> seconds.
  </p>
  <div v-if="score < 1"><p>you're fast</p></div>
  <div v-else-if="score > 1 && score < 2"><p>you're normal</p></div>
  <div v-else><p>you're slow</p></div>
</template>
<script>
export default {
  name: "resultBox",
  props: ["score"],
};
</script>

<style scoped>
p {
  color: rgb(0, 255, 255);
  margin-top: 10px;
  text-align: center;
  font-size: 1.5rem;
}
.result {
  color: rgb(21, 255, 0);
}
span {
  color: orange;
}
</style>
