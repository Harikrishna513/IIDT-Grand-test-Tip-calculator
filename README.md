<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tip Calculator</title>
    <style>
        .container {
    max-width: 400px;
    margin: 50px auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

.input-group {
    margin-bottom: 15px;
}

.input-group label {
    display: inline-block;
    width: 150px;
    font-weight: bold;
}

.input-group input {
    width: 200px;
    padding: 5px;
    border: 1px solid #ccc;
    border-radius: 3px;
}

button {
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}

    </style>
    <script>
        function calculateTip() {
    var billAmount = parseFloat(document.getElementById("billAmount").value);
    var serviceQuality = parseFloat(document.getElementById("serviceQuality").value);
    var numPeople = parseInt(document.getElementById("numPeople").value);
    
    if (isNaN(billAmount) || isNaN(serviceQuality) || isNaN(numPeople) || billAmount <= 0 || serviceQuality < 1 || serviceQuality > 5 || numPeople <= 0) {
        document.getElementById("result").innerHTML = "Please enter valid inputs.";
        return;
    }
    
    var tipPerPerson = (billAmount * (serviceQuality / 100)) / numPeople;
    
    document.getElementById("result").innerHTML = "Tip per person: " + tipPerPerson.toFixed(2);
}

    </script>
</head>
<body>
    <div class="container">
        <h1>Tip Calculator</h1>
        <div class="input-group">
            <label for="billAmount">Bill Amount:</label>
            <input type="number" id="billAmount">
        </div>
        <div class="input-group">
            <label for="serviceQuality">Service Quality:</label>
            <input type="number" id="serviceQuality" min="1" max="5">
        </div>
        <div class="input-group">
            <label for="numPeople">Number of People:</label>
            <input type="number" id="numPeople">
        </div>
        <button onclick="calculateTip()">Calculate Tip</button>
        <div id="result"></div>
    </div>
    
</body>
</html>
# IIDT-Grand-test-Tip-calculator
