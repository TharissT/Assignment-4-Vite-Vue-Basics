<script> 

</script> 

<template>
<form action="/action_page.php">
        <h1>Gregory-Leibniz Pi Approximation</h1>
        <label for="nValue">nValue:</label><br>
        <input type="text" id="nValue" name="nValue" value="0"><br>
        <label for="PiApproximation">PiApproximation (Result):</label><br>
        <input type="text" id="piApproximation" name="piApproximation" value="0" readonly> <br>
        <input type="button" onclick="calculatePi()" value="Calculate">
    </form>
</template>

<style>



</style>