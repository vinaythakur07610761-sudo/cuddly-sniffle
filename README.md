<!DOCTYPE html>
<html>
<head>
  <title>Password Strength Checker</title>
  <style>
    body{
      font-family: Arial;
      text-align:center;
      margin-top:100px;
    }
    input{
      padding:10px;
      width:250px;
      font-size:16px;
    }
    #result{
      margin-top:20px;
      font-size:18px;
      font-weight:bold;
    }
  </style>
</head>
<body>

<h2>Password Strength Checker 🔐</h2>
<input type="password" id="password" placeholder="Enter password">
<div id="result"></div>

<script>
  const input = document.getElementById("password");
  const result = document.getElementById("result");

  input.addEventListener("input", () => {
    const val = input.value;
    let strength = "Weak";

    if(val.length > 8 && /[A-Z]/.test(val) && /[0-9]/.test(val)){
      strength = "Medium";
    }
    if(val.length > 10 && /[A-Z]/.test(val) && /[0-9]/.test(val) && /[!@#$%^&*]/.test(val)){
      strength = "Strong";
    }

    result.innerText = "Strength: " + strength;
  });
</script>

</body>
</html>
