<template>
<form action="/action_page.php">
    <h1> Asymptote Finder </h1>
    <label for="m_value">m Value:</label><br>
    <input type="text" id="m" name="m" value="0"><br>
    <label for="n_value">n Value:</label><br>
    <input type="text" id="n" name="n" value="0"><br>
    <label for="AsymptoteType">Asymptote Type (Result):</label><br>
    <input type="text" id="AsymptoteType" name="AsymptoteType" value="0" readonly> <br>
    <input type="button" onclick="calculateAsymptote()" value="Calculate">
</form>
</template>

<style> 

</style> 