<script setup>
  import { ref } from 'vue';
  
  const nValue = ref(0);
  const piApproximation = ref(0);
  
  const calculatePi = () => {
    let sum = 0;
    for (let i = 0; i < nValue.value; i++) {
      sum += (4 * ((-1) ** i) / (2 * i + 1));
    }
    piApproximation.value = sum;
};
  </script>
  
  <template>
  <div class="calculator-container">
  <form @submit.prevent="calculatePi" class="gregory-pi">
      <h1>Gregory-Leibniz Pi Approximation</h1>
      <label for="n-value">n Value:</label>
      <input v-model.number="nValue" type="number" id="n-value" />

      <label for="pi-approximation">Pi Approximation (Result):</label>
      <input v-model="piApproximation" type="text" id="pi-approximation" readonly />

      <input type="submit" value="Calculate" />
    </form>
    </div>
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

form:nth-of-type(2) {
  position: absolute;
  top: 0;
  left: 420px; 
}

form.gregory-pi {
  position: absolute;
  top: 200px; 
  left: 20px;  
  z-index: 1; 
}
</style>