<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Click to Earn</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 50px;
        }
        #balance {
            font-size: 2em;
            margin-bottom: 20px;
        }
        button {
            padding: 15px 30px;
            font-size: 1em;
            margin: 10px;
        }
    </style>
</head>
<body>
    <h1>Earn Money by Clicking!</h1>

    <!-- Display current balance -->
    <div id="balance">£0.00</div>

    <!-- Main button for adding 50p -->
    <button id="mainButton">Add 50p</button>

    <!-- X2 button for doubling each click -->
    <button id="doubleButton">X2</button>

    <!-- X100 button for adding crazy amounts -->
    <button id="crazyButton">X100</button>

    <!-- Cashout button (this will be linked to PayPal later) -->
    <button id="cashoutButton">Cashout</button>

    <script>
        let balance = 0;
        let multiplier = 1;

        const balanceDisplay = document.getElementById('balance');
        const mainButton = document.getElementById('mainButton');
        const doubleButton = document.getElementById('doubleButton');
        const crazyButton = document.getElementById('crazyButton');
        const cashoutButton = document.getElementById('cashoutButton');

        // Function to update the displayed balance
        function updateBalance() {
            balanceDisplay.innerText = `£${balance.toFixed(2)}`;
        }

        // Add 50p on each click, multiplied by the current multiplier
        mainButton.addEventListener('click', () => {
            balance += 0.50 * multiplier;
            updateBalance();
        });

        // Double the multiplier
        doubleButton.addEventListener('click', () => {
            multiplier = 2;
        });

        // Multiply by 100 for crazy mode
        crazyButton.addEventListener('click', () => {
            multiplier = 100;
        });

        // Cashout button (this will interact with PayPal later)
        cashoutButton.addEventListener('click', () => {
            alert('Cashout feature coming soon!');
        });
    </script>
</body>
</html>
