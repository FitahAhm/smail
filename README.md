<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bank Management System</title>
<link rel="stylesheet" href="style.css">
</head>
<body>

<div class="container">
  <h2>Bank Management System</h2>

  <!-- Create Account -->
  <input type="text" id="name" placeholder="Account Name">
  <input type="number" id="accNum" placeholder="Account Number">
  <input type="number" id="balance" placeholder="Initial Balance">
  <button onclick="handle('create')">Create Account</button>
  <div id="createError" class="error"></div>

  <hr>

  <!-- View Accounts -->
  <button onclick="handle('view')">View All Accounts</button>
  <div id="accounts"></div>

  <hr>

  <!-- Transactions -->
  <input type="number" id="transAccNum" placeholder="Account Number">
  <input type="number" id="amount" placeholder="Amount">
  <button onclick="handle('deposit')">Deposit</button>
  <button onclick="handle('withdraw')">Withdraw</button>
  <div id="transError" class="error"></div>
</div>

<script src="script.js"></script>
</body>
</html>
