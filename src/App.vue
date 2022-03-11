<template>
  <h1>Hello</h1>
  <input type="text" /> <button @click="clickHandler">Click</button>
</template>
<script>
export default {
  data() {
    return {
      header: "This is our header ",
    };
  },
};
</script>
<style>
h1 {
  font-size: 40px;
}
</style>
