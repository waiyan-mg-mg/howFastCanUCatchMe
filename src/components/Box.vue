<template>
  <div v-if="show" class="container" v-on:click="hide">Click Here</div>
</template>

<script>
export default {
  name: "FooterBox",
  props: ["delay"],
  data() {
    return {
      show: false,
      timerScore: 0,
      timerRun: undefined,
    };
  },
  methods: {
    hide() {
      this.$emit("hideBox", this.timerScore);
      clearInterval(this.timerRun);
    },
  },
  mounted() {
    console.log("mounted");
    setTimeout(() => {
      this.show = true;
      this.timerRun = setInterval(() => {
        this.timerScore += 50;
      }, 50);
    }, this.delay);
  },
  updated() {
    console.log("update");
  },
  unmounted() {
    console.log("unmounted");
  },
};
</script>

<style scoped>
* {
  color: white;
}
.container {
  width: 600px;
  height: 300px;
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
  font-size: 1.5rem;
  background-color: rgb(103, 109, 107);
  border-radius: 10px;
  margin: 40px auto 0;
  padding: 20px;
  line-height: 1.5em;
}
</style>
