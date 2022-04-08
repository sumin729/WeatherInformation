<template>
  <div>
    <header class="header">
      <h2>Weather Information</h2>
    </header>
  </div>
</template>

<script>
export default {
  name: "HeaderDisplay",
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap");
.header {
  display: flex;
  justify-content: center;
  align-content: center;
  background: linear-gradient(15deg, #1a2980, #26d0ce);
  padding: 2rem;
  color: aliceblue;
  font-family: "Dancing Script", cursive;
  font-size: 25px;
}
</style>
