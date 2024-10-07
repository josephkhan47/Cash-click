<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cashout Feature</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        button {
            margin: 10px;
            padding: 10px 20px;
            font-size: 16px;
        }
        .coming-soon {
            color: red;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Cashout Feature</h1>
    <div>
        <button id="add50">Add £0.50</button>
        <button id="double">X2</button>
        <button id="hundred">X100</button>
    </div>
    <h2>Total: £<span id="total">0.00</span></h2>
    <hr>
    <h2>Cashout</h2>
    <p class="coming-soon">Cashout feature coming soon!</p>
    <input type="email" id="paypalEmail" placeholder="Enter your PayPal Email (for testing)" required>
    <input type="number" id="cashoutAmount" placeholder="Amount (for testing)" required>
    <button id="cashoutButton" disabled>Cashout</button>

    <script>
        let totalAmount = 0;

        // Button event handlers
        document.getElementById('add50').onclick = function() {
            totalAmount += 0.50;
            document.getElementById('total').innerText = totalAmount.toFixed(2);
        };

        document.getElementById('double').onclick = function() {
            totalAmount *= 2;
            document.getElementById('total').innerText = totalAmount.toFixed(2);
        };

        document.getElementById('hundred').onclick = function() {
            totalAmount += 100;
            document.getElementById('total').innerText = totalAmount.toFixed(2);
        };

        // Cashout button will be disabled until feature is active
        document.getElementById('cashoutButton').onclick = function() {
            const email = document.getElementById('paypalEmail').value;
            const amount = totalAmount; // Cashout the total amount

            // Show a message that the feature is coming soon
            alert('Cashout feature is coming soon! Please check back later.');

            // You can still handle cashout requests here if needed
            // Uncomment the following code to allow cashout for testing
            /*
            fetch('/cashout', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({ email: email, amount: amount })
            })
            .then(response => {
                if (!response.ok) {
                    throw new Error('Cashout failed');
                }
                return response.json();
            })
            .then(data => {
                alert('Cashout successful! Check​⬤
