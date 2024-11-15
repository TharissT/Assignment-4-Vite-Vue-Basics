<script setup>
import { ref } from 'vue';

const mValue = ref(0);
const nValue = ref(0);
const asymptoteType = ref('');

function calculateAsymptote() {
  const m = parseInt(mValue.value);
  const n = parseInt(nValue.value);

  if (isNaN(m) || isNaN(n)) {
    asymptoteType.value = 'Please enter valid numbers for m and n.';
  } else if (m === n) {
    asymptoteType.value = 'The asymptote is horizontal';
  } else if (n > m) {
    asymptoteType.value = 'The asymptote is the x-axis';
  } else {
    const difference = m - n;
    switch (difference) {
      case 1:
        asymptoteType.value = 'The asymptote is Linear';
        break;
      case 2:
        asymptoteType.value = 'The asymptote is Quadratic';
        break;
      case 3:
        asymptoteType.value = 'The asymptote is Cubic';
        break;
      case 4:
        asymptoteType.value = 'The asymptote is Quartic';
        break;
      case 5:
        asymptoteType.value = 'The asymptote is Quintic';
        break;
      case 6:
        asymptoteType.value = 'The asymptote is Sextic';
        break;
      case 7:
        asymptoteType.value = 'The asymptote is Septic';
        break;
      case 8:
        asymptoteType.value = 'The asymptote is Octic';
        break;
      case 9:
        asymptoteType.value = 'The asymptote is Nonic';
        break;
      case 10:
        asymptoteType.value = 'The asymptote is Decic';
        break;
      default:
        asymptoteType.value = 'The asymptote is a higher degree polynomial';
    }
  }
}
</script>

<template>
    <form @submit.prevent="calculateAsymptote" class="asymptote">
      <h1>Asymptote Finder</h1>
      <label for="m-value">m:</label>
      <input v-model="mValue" type="number" id="m-value" name="m" />

      <label for="n-value">n:</label>
      <input v-model="nValue" type="number" id="n-value" name="n" />

      <label for="asymptote-type">Asymptote Type (Result):</label>
      <input v-model="asymptoteType" type="text" id="asymptote-type" name="asymptoteType" readonly />

      <input type="submit" value="Calculate" />
    </form>

</template>

<style scoped>
form {
  max-width: 400px;
  margin: auto;
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

form:nth-of-type(1) {
  position: absolute;
  top: 0;
  left: 420px; /* Adjust this value based on the width of the second form */
}


form.asymptote {
  top: 20px; /* Position it below the Cosine Law form */
  left: 500px;
  z-index: 2; /* Behind Cosine Law */
}
</style>