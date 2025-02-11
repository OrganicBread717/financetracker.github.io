<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Finance Tracker</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: auto;
            padding: 20px;
            text-align: center;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        th, td {
            border: 1px solid black;
            padding: 8px;
            text-align: left;
        }
    </style>
</head>
<body>
    <h2>Student Finance Tracker</h2>
    <p>Current Balance: $<span id="balance">0.00</span></p>
    
    <h3>Add Transaction</h3>
    <form id="transaction-form">
        <input type="text" id="desc" placeholder="Description" required>
        <input type="number" id="amount" placeholder="Amount" required>
        <select id="type">
            <option value="income">Income</option>
            <option value="expense">Expense</option>
        </select>
        <button type="submit">Add</button>
    </form>
    
    <h3>Transactions</h3>
    <table>
        <thead>
            <tr>
                <th>Description</th>
                <th>Amount</th>
                <th>Type</th>
                <th>Action</th>
            </tr>
        </thead>
        <tbody id="transaction-list"></tbody>
    </table>
    
    <script>
        let balance = 0;
        const balanceEl = document.getElementById("balance");
        const transactionForm = document.getElementById("transaction-form");
        const transactionList = document.getElementById("transaction-list");

        transactionForm.addEventListener("submit", function(event) {
            event.preventDefault();
            const desc = document.getElementById("desc").value;
            const amount = parseFloat(document.getElementById("amount").value);
            const type = document.getElementById("type").value;
            
            if (isNaN(amount) || amount <= 0) {
                alert("Please enter a valid amount.");
                return;
            }
            
            const row = document.createElement("tr");
            row.innerHTML = `
                <td>${desc}</td>
                <td>${amount.toFixed(2)}</td>
                <td>${type}</td>
                <td><button onclick="removeTransaction(this, ${amount}, '${type}')">Delete</button></td>
            `;
            transactionList.appendChild(row);
            
            balance += type === "income" ? amount : -amount;
            balanceEl.textContent = balance.toFixed(2);
            
            transactionForm.reset();
        });

        function removeTransaction(button, amount, type) {
            button.parentElement.parentElement.remove();
            balance -= type === "income" ? amount : -amount;
            balanceEl.textContent = balance.toFixed(2);
        }
    </script>
</body>
</html>
