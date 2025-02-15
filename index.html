<!DOCTYPE html>
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
        <input type="number" step="0.01" min="0.01" id="amount" placeholder="Amount" required>
        <input type="date" id="date" required>
        <select id="type">
            <option value="income">Income</option>
            <option value="expense">Expense</option>
        </select>
        <button type="submit">Add</button>
    </form>
    
    <h3>Filter Transactions</h3>
    <input type="text" id="filter-desc" placeholder="Search by description">
    <button onclick="filterTransactions()">Filter</button>
    
    <h3>Transactions</h3>
    <table>
        <thead>
            <tr>
                <th>Description</th>
                <th>Amount</th>
                <th>Type</th>
                <th>Date</th>
                <th>Action</th>
            </tr>
        </thead>
        <tbody id="transaction-list"></tbody>
    </table>
    
    <h3>Summary</h3>
    <p>Total Income: $<span id="total-income">0.00</span></p>
    <p>Total Expenses: $<span id="total-expense">0.00</span></p>
    <p>Net Total: $<span id="net-total">0.00</span></p>
    
    <script>
        let balance = 0;
        let totalIncome = 0;
        let totalExpense = 0;
        const balanceEl = document.getElementById("balance");
        const totalIncomeEl = document.getElementById("total-income");
        const totalExpenseEl = document.getElementById("total-expense");
        const netTotalEl = document.getElementById("net-total");
        const transactionForm = document.getElementById("transaction-form");
        const transactionList = document.getElementById("transaction-list");
        const filterDescInput = document.getElementById("filter-desc");

        transactionForm.addEventListener("submit", function(event) {
            event.preventDefault();
            const desc = document.getElementById("desc").value;
            const amount = parseFloat(document.getElementById("amount").value).toFixed(2);
            const date = document.getElementById("date").value;
            const type = document.getElementById("type").value;
            
            if (isNaN(amount) || amount <= 0) {
                alert("Please enter a valid amount.");
                return;
            }
            
            const row = document.createElement("tr");
            row.innerHTML = `
                <td>${desc}</td>
                <td>${parseFloat(amount).toFixed(2)}</td>
                <td>${type}</td>
                <td>${date}</td>
                <td><button onclick="removeTransaction(this, ${amount}, '${type}')">Delete</button></td>
            `;
            transactionList.appendChild(row);
            
            balance += type === "income" ? parseFloat(amount) : -parseFloat(amount);
            if (type === "income") {
                totalIncome += parseFloat(amount);
            } else {
                totalExpense += parseFloat(amount);
            }
            
            updateDisplay();
            transactionForm.reset();
        });

        function removeTransaction(button, amount, type) {
            button.parentElement.parentElement.remove();
            balance -= type === "income" ? parseFloat(amount) : -parseFloat(amount);
            if (type === "income") {
                totalIncome -= parseFloat(amount);
            } else {
                totalExpense -= parseFloat(amount);
            }
            updateDisplay();
        }

        function updateDisplay() {
            balanceEl.textContent = balance.toFixed(2);
            totalIncomeEl.textContent = totalIncome.toFixed(2);
            totalExpenseEl.textContent = totalExpense.toFixed(2);
            netTotalEl.textContent = (totalIncome - totalExpense).toFixed(2);
        }

        function filterTransactions() {
            const filterText = filterDescInput.value.toLowerCase();
            const rows = transactionList.getElementsByTagName("tr");
            for (let row of rows) {
                const descCell = row.getElementsByTagName("td")[0];
                if (descCell) {
                    const textValue = descCell.textContent.toLowerCase();
                    row.style.display = textValue.includes(filterText) ? "" : "none";
                }
            }
        }
    </script>
</body>
</html>

