<template>
  <h1>{{ header }}</h1>
  <Modal />
</template>
<script>
import Modal from "./components/Modal.vue";
export default {
  data() {
    return {
      header: "This is our header ",
    };
  },
  methods: {},
  components: {
    Modal,
  },
};
</script>
<style>


h1 {
  font-size: 40px;
}
</style>
