<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Faris – Personal Database Page</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #0f172a;
      color: #e5e7eb;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .card {
      background: #020617;
      border: 1px solid #1e293b;
      border-radius: 14px;
      padding: 24px;
      width: 100%;
      max-width: 420px;
    }

    h1 {
      margin-top: 0;
      text-align: center;
      font-size: 22px;
    }

    .row {
      display: flex;
      justify-content: space-between;
      padding: 10px 0;
      border-bottom: 1px solid #1e293b;
    }

    .row:last-child {
      border-bottom: none;
    }

    .label {
      color: #94a3b8;
    }

    .value {
      font-weight: bold;
      text-align: right;
    }

    .note {
      margin-top: 14px;
      font-size: 12px;
      color: #94a3b8;
      text-align: center;
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>Student Database Record</h1>

    <div class="row">
      <span class="label">Name</span>
      <span class="value" id="name"></span>
    </div>

    <div class="row">
      <span class="label">Phone</span>
      <span class="value" id="phone"></span>
    </div>

    <div class="row">
      <span class="label">Birth Year</span>
      <span class="value" id="birth"></span>
    </div>

    <div class="row">
      <span class="label">Email</span>
      <span class="value" id="email"></span>
    </div>

    <div class="row">
      <span class="label">University ID</span>
      <span class="value" id="uid"></span>
    </div>

    <div class="note">
      Stored locally using browser database (localStorage)
    </div>
  </div>

  <script>
    // "Database"
    const userData = {
      name: "faris",
      phone: "01040478958",
      birthYear: 2006,
      email: "faris.shireen@ufe.edu.eg",
      universityId: "MG24448"
    };

    // Save once
    if (!localStorage.getItem("faris_db")) {
      localStorage.setItem("faris_db", JSON.stringify(userData));
    }

    // Read from database
    const data = JSON.parse(localStorage.getItem("faris_db"));

    // Display
    document.getElementById("name").textContent = data.name;
    document.getElementById("phone").textContent = data.phone;
    document.getElementById("birth").textContent = data.birthYear;
    document.getElementById("email").textContent = data.email;
    document.getElementById("uid").textContent = data.universityId;
  </script>

</body>
</html>
