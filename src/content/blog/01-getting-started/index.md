---
title: "Feriepenger Calculator"
description: "Calculate your Norwegian holiday pay based on annual salary and other factors."
---

<script>
function calculateFeriepenger() {
    const salary = parseFloat(document.getElementById('salary').value) || 0;
    const lastYearBonus = parseFloat(document.getElementById('lastYearBonus').value) || 0;
    const extraPayments = parseFloat(document.getElementById('extraPayments').value) || 0;
    const isSenior = document.getElementById('isSenior').checked;

    const percentage = 0.12;
    const seniorPercentage = isSenior ? 0.025 : 0;
    const totalPercentage = percentage + seniorPercentage;

    const feriepenger = (salary + lastYearBonus + extraPayments) * totalPercentage;
    document.getElementById('result').innerText = `Your feriepenger for this year is: ${feriepenger.toFixed(2)} NOK`;
}
</script>

<h1>Feriepenger Calculator</h1>
<p>Calculate your holiday pay based on your annual salary, bonus, and other relevant factors.</p>

<div>
    <label for="salary">Enter your annual salary in NOK:</label><br>
    <input type="number" id="salary" name="salary"><br><br>

    <label for="lastYearBonus">Enter your last year's bonus in NOK:</label><br>
    <input type="number" id="lastYearBonus" name="lastYearBonus"><br><br>

    <label for="extraPayments">Enter any extra payments that count towards feriepenger in NOK:</label><br>
    <input type="number" id="extraPayments" name="extraPayments"><br><br>

    <label for="isSenior">Are you 60 years or older?</label>
    <input type="checkbox" id="isSenior" name="isSenior"><br><br>

    <button onclick="calculateFeriepenger()">Calculate Feriepenger</button>

    <p id="result"></p>
</div>
