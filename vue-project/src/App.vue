<script setup>
import CosLaw from './components/CosineLaw.vue';
import AsymptoteFinder from './components/AsymptoteFinder.Vue';
import GregoryLeibnizPi from './components/GregoryLeibnizPi.vue';
</script>

<template>
  <div class="app-container">
    <CosLaw />
    <AsymptoteFinder />
    <GregoryLeibnizPi />
  </div>
</template>

<style scoped>
 .calculator-container {
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
  
  button {
    background-color: #00bfff;
    color: #fff;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #009acd;
  }
</style>