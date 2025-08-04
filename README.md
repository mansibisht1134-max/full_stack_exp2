<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Responsive Banking UI</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background: #f1f1f1;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
    }

    .bank-container {
      background: white;
      padding: 2rem;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      width: 100%;
      max-width: 400px;
      text-align: center;
    }

    h2 {
      margin-bottom: 1rem;
    }

    .balance {
      font-size: 2rem;
      margin-bottom: 1.5rem;
      color: #2d6a4f;
    }

    .buttons {
      display: flex;
      justify-content: space-between;
      gap: 1rem;
    }

    button {
      flex: 1;
      padding: 0.75rem;
      font-size: 1rem;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: background 0.3s;
    }

    .deposit {
      background-color: #38b000;
      color: white;
    }

    .deposit:hover {
      background-color: #2d6a4f;
    }

    .withdraw {
      background-color: #d90429;
      color: white;
    }

    .withdraw:hover {
      background-color: #a50321;
    }

    @media (max-width: 500px) {
      .buttons {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>

  <div class="bank-container">
    <h2>Bank Account</h2>
    <div class="balance">₹ <span id="balance">1000</span></div>
    <div class="buttons">
      <button class="deposit" onclick="changeBalance(500)">Deposit ₹500</button>
      <button class="withdraw" onclick="changeBalance(-500)">Withdraw ₹500</button>
    </div>
  </div>

  <script>
    let balance = 1000;
    const balanceEl = document.getElementById("balance");

    function changeBalance(amount) {
      if (balance + amount < 0) {
        alert("Insufficient balance!");
        return;
      }
      balance += amount;
      balanceEl.textContent = balance;
    }
  </script>

</body>
</html>
