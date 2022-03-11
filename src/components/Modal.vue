<template>
  <div class="backdrop">
    <div class="overlay">
      <div class="box_header">
        <div><span>Alert</span></div>
        <div><span>X</span></div>
      </div>
      <div class="box_body">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus
        quaerat iure labore corrupti, fugiat beatae nihil reiciendis! Aliquam
        ratione natus architecto id. Distinctio, dolore quae blanditiis aliquid
        repudiandae fugiat rerum.
      </div>
      <div class="box_footer">
        <div><button>Confirm</button></div>
      </div>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.backdrop {
  width: 100vw;
  height: 100vh;
  background: gray;
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
}
.overlay {
  position: absolute;
  width: 500px;
  height: max-content;
  padding: 20px;
  background: white;
  border-radius: 10px;
  z-index: 5555;
}
.box_header {
  display: flex;
  justify-content: space-between;
  font-size: 21px;
  font-weight: bold;
}
.box_body {
  text-align: justify;
  padding-bottom: 10px;
}
.box_footer {
  display: flex;
  flex-direction: row-reverse;
}
.box_foote button {
  padding: 15px;
  font-size: 24px;
  background: wheat;
}
</style>
