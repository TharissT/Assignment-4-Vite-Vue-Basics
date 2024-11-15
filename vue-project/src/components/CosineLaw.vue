<script setup>
import { ref } from 'vue';

const sideA = ref(0);
const sideB = ref(0);
const angleC = ref(0);
const sideC = ref(0);

function calculateCosineLaw() {
  const angleInRadians = (angleC.value * Math.PI) / 180; 
  sideC.value = Math.sqrt(
    sideA.value ** 2 + sideB.value ** 2 - 2 * sideA.value * sideB.value * Math.cos(angleInRadians)
  );
}
</script>

<template>
  <div class="calculator-container">
   
    <form @submit.prevent="calculateCosineLaw" class="cosine-law">
      <h1>Cosine Law</h1>
      <label for="side-a">Side A:</label>
      <input id="side-a" v-model.number="sideA" type="number" />

      <label for="side-b">Side B:</label>
      <input id="side-b" v-model.number="sideB" type="number" />

      <label for="angle-c">Angle C (in degrees):</label>
      <input id="angle-c" v-model.number="angleC" type="number" />

      <label for="side-c">Side C (Result):</label>
      <input id="side-c" v-model="sideC" type="text" readonly />

      <input type="submit" value="Calculate" />
    </form>
  </div>
</template>

<style scoped>
form {
  position: absolute; /* Set position to absolute */
  top: 0px; /* Distance from the top of the screen */
  left: 20px; /* Distance from the left of the screen */
  max-width: 400px;
  margin: 0; /* Remove any auto margins */
  padding: 20px;
  background-color: #1a1a1a;
  color: #f0f0f0;
  border-radius: 10px;
  text-align: center;
}

h1 {
  color: #00bfff;
  margin-bottom: 20px;
}

label {
  display: block;
  margin-top: 10px;
  margin-bottom: 5px;
  color: #00bfff;
}

input[type="number"],
input[type="text"] {
  width: 100%;
  padding: 10px;
  margin-bottom: 15px;
  border: 2px solid #00bfff;
  border-radius: 5px;
  background-color: #333;
  color: #fff;
}

input[type="text"] {
  cursor: not-allowed;
}

input[type="submit"] {
  background-color: #00bfff;
  color: #fff;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
}

input[type="submit"]:hover {
  background-color: black;
}

form.cosine-law {
  top: 20px;
  left: 20px;
  z-index: 3; /* Make sure it appears above the others */
}

</style>
