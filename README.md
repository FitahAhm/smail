<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Bank Management System</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #0f172a;
            color: #fff;
            padding: 20px;
        }
        h1 {
            text-align: center;
            color: #38bdf8;
        }
        .container {
            max-width: 500px;
            margin: auto;
            background: #1e293b;
            padding: 20px;
            border-radius: 10px;
        }
        input, button {
            width: 100%;
            padding: 10px;
            margin: 8px 0;
            border-radius: 5px;
            border: none;
        }
        button {
            background-color: #38bdf8;
            cursor: pointer;
            font-weight: bold;
        }
        button:hover {
            background-color: #0ea5e9;
        }
        .account {
            background: #334155;
            padding: 10px;
            margin-top: 15px;
            border-radius: 5px;
        }
        .danger {
            background-color: #ef4444;
        }
    </style>
</head>
<body>

<h1>Bank Management System</h1>

<div class="container">

    <h3>Create Account</h3>
    <input type="text" id="name" placeholder="Account Holder Name">
    <input type="number" id="balance" placeholder="Initial Balance">
    <button onclick="createAccount()">Create Account</button>

    <h3>Transactions</h3>
    <input type="number" id="amount" placeholder="Enter Amount">
    <button onclick="deposit()">Deposit</button>
    <button onclick="withdraw()">Withdraw</button>
    <button class="danger" onclick="deleteAccount()">Delete Account</button>

    <div id="output"></div>

</div>

<script>
    let account = null;

    function createAccount() {
        let name = document.getElementById("name").value;
        let balance = document.getElementById("balance").value;

        if (name === "" || balance === "" || balance < 0) {
            alert("Fadlan geli xog sax ah");
            return;
        }

        account = {
            name: name,
            balance: Number(balance)
        };

        displayAccount();
    }

    function deposit() {
        if (!account) {
            alert("Account ma jiro");
            return;
        }

        let amount = document.getElementById("amount").value;

        if (amount === "" || amount <= 0) {
            alert("Geli lacag sax ah");
            return;
        }

        account.balance += Number(amount);
        displayAccount();
    }

    function withdraw() {
        if (!account) {
            alert("Account ma jiro");
            return;
        }

        let amount = document.getElementById("amount").value;

        if (amount === "" || amount <= 0) {
            alert("Geli lacag sax ah");
            return;
        }

        if (amount > account.balance) {
            alert("Lacagta kuma filna");
            return;
        }

        account.balance -= Number(amount);
        displayAccount();
    }

    function deleteAccount() {
        if (!account) {
            alert("Account horey looma abuurin");
            return;
        }

        account = null;
        document.getElementById("output").innerHTML = "";
        alert("Account waa la tirtiray");
    }

    function displayAccount() {
        document.getElementById("output").innerHTML = `
            <div class="account">
                <p><strong>Name:</strong> ${account.name}</p>
                <p><strong>Balance:</strong> $${account.balance}</p>
            </div>
        `;
    }
</script>

</body>
</html>
