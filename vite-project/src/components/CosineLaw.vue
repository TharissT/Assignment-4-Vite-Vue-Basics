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
    <form @submit.prevent="calculateCosineLaw">
      <div class="calculator-container">
        <h1>Cosine Law</h1>
        <label >Side A:</label>
        <input v-model="sideA" type="number"  />
        <label >Side B:</label>
        <input v-model="sideB" type="number"  />
        <label >Angle C (in degrees):</label>
        <input v-model="angleC" type="number"  />
        <label> Side C (Result):</label>
        <input v-model="sideC" type="text" readonly />
        <input type="submit" value="Calculate" />
      </div>
    </form>
  </template>

<style> 
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  

  body {
    font-family: Arial, sans-serif;
    background-color: #1a1a1a;
    color: #f0f0f0;
    text-align: center;
    margin: 0;
    padding: 0;
    height: 100vh;
    display: flex;
    justify-content: flex-start;
    align-items: flex-start;
  }
  
  .calculator-container {
    background-color: #2a2a2a;
    padding: 30px;
    border-radius: 10px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
    width: 100%;
    max-width: 450px;
    text-align: center;
  }
  
  h1 {
    font-size: 36px;
    margin-bottom: 20px;
    color: #00bfff;
    font-weight: 700;
  }
  
  label {
    display: block;
    font-size: 16px;
    font-weight: bold;
    color: #00bfff;
    margin: 10px 0 5px;
  }

  input[type="number"],
  input[type="text"] {
    width: 100%;
    padding: 14px;
    margin-bottom: 20px;
    border: 2px solid #00bfff;
    border-radius: 6px;
    background-color: #333;
    color: #fff;
    font-size: 16px;
  }
  
  input[type="number"]:focus,
  input[type="text"]:focus {
    outline: none;
    border-color: #00d4ff;
    box-shadow: 0 0 10px rgba(0, 212, 255, 0.5);
  }
  
  input[type="submit"] {
    width: 100%;
    padding: 14px;
    background-color: #00bfff;
    color: white;
    border: none;
    border-radius: 6px;
    font-size: 18px;
    font-weight: bold;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
 
  input[type="submit"]:hover {
    background-color: #009acd;
    transform: scale(1.05);
  }
  
  input[type="submit"]:active {
    background-color: #007b8f;
  }
  
  input[readonly] {
    background-color: #e0e0e0;
    cursor: not-allowed;
  }
  
  @media (max-width: 600px) {
    .calculator-container {
      padding: 20px;
      max-width: 90%;
    }
  
    h1 {
      font-size: 28px;
    }
  
    input[type="number"],
    input[type="text"] {
      padding: 12px;
      font-size: 14px;
    }
  
    input[type="submit"] {
      font-size: 16px;
      padding: 12px;
    }
  }

</style>