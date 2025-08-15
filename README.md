# Kamao
Sab milkar kamayege
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Kamao - Login</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- Google Fonts for a clean look -->
  <link href="https://fonts.googleapis.com/css?family=Montserrat:700,400&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 0;
      min-height: 100vh;
      background: linear-gradient(135deg, #43cea2 0%, #185a9d 100%);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Montserrat', sans-serif;
      overflow: hidden;
    }
    .animated-bg {
      position: absolute;
      top: 0; left: 0; width: 100vw; height: 100vh;
      z-index: 0;
      overflow: hidden;
      pointer-events: none;
    }
    .bubble {
      position: absolute;
      border-radius: 50%;
      opacity: 0.35;
      animation: float 12s infinite linear;
      background: radial-gradient(circle at 30% 30%, #fff 60%, #43cea2 100%);
    }
    .bubble:nth-child(1) { width: 120px; height: 120px; left: 10vw; top: 70vh; animation-delay: 0s;}
    .bubble:nth-child(2) { width: 80px; height: 80px; left: 70vw; top: 75vh; animation-delay: 2s;}
    .bubble:nth-child(3) { width: 150px; height: 150px; left: 40vw; top: 80vh; animation-delay: 5s;}
    .bubble:nth-child(4) { width: 60px; height: 60px; left: 80vw; top: 60vh; animation-delay: 8s;}
    @keyframes float {
      0% { transform: translateY(0) scale(1);}
      100% { transform: translateY(-90vh) scale(1.1);}
    }

    .login-container {
      position: relative;
      z-index: 1;
      background: rgba(255,255,255,0.15);
      border-radius: 24px;
      box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
      padding: 48px 32px 40px 32px;
      width: 340px;
      backdrop-filter: blur(8px);
      border: 1.5px solid rgba(255,255,255,0.25);
      display: flex;
      flex-direction: column;
      align-items: center;
      animation: popIn 1.1s cubic-bezier(0.22,1,0.36,1) 0.1s backwards;
    }
    @keyframes popIn {
      0% { transform: scale(0.7) translateY(80px); opacity: 0; }
      100% { transform: scale(1) translateY(0); opacity: 1; }
    }
    .login-logo {
      font-size: 2.5em;
      font-weight: 700;
      color: #fff;
      letter-spacing: 2px;
      background: linear-gradient(90deg,#185a9d 60%, #43cea2 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      margin-bottom: 16px;
      animation: glow 2.5s infinite alternate;
    }
    @keyframes glow {
      0% { text-shadow: 0 0 12px #43cea2, 0 0 0px #fff; }
      100% { text-shadow: 0 0 24px #43cea2, 0 0 20px #fff; }
    }
    .login-title {
      color: #fff;
      font-size: 1.25em;
      font-weight: 400;
      margin-bottom: 28px;
      margin-top: 0;
      letter-spacing: 1px;
      text-shadow: 0 2px 10px #185a9d99;
    }
    form {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 20px;
    }
    .input-group {
      display: flex;
      flex-direction: column;
      position: relative;
    }
    .input-group label {
      color: #fff;
      font-size: 0.95em;
      margin-bottom: 4px;
      font-weight: 500;
      letter-spacing: 0.5px;
    }
    .input-group input {
      padding: 11px 14px;
      border-radius: 8px;
      border: none;
      outline: none;
      background: rgba(255,255,255,0.25);
      color: #185a9d;
      font-size: 1em;
      transition: background 0.2s;
      box-shadow: 0 1px 4px #43cea233;
    }
    .input-group input:focus {
      background: rgba(67,206,162,0.16);
      border: 1.5px solid #185a9d;
      color: #185a9d;
    }
    .login-btn {
      padding: 12px 0;
      background: linear-gradient(90deg,#185a9d 60%, #43cea2 100%);
      color: #fff;
      font-weight: 700;
      font-size: 1.1em;
      border: none;
      border-radius: 8px;
      box-shadow: 0 2px 12px #185a9d44;
      cursor: pointer;
      letter-spacing: 1px;
      transition: background 0.25s, box-shadow 0.25s, transform 0.1s;
      margin-top: 6px;
    }
    .login-btn:hover {
      background: linear-gradient(90deg,#43cea2 60%, #185a9d 100%);
      box-shadow: 0 4px 24px #185a9d77;
      transform: translateY(-2px) scale(1.015);
    }
    .forgot-link {
      text-align: right;
      font-size: 0.94em;
      color: #fff;
      text-decoration: none;
      margin-top: -10px;
      margin-bottom: 10px;
      opacity: 0.85;
      transition: color 0.15s;
    }
    .forgot-link:hover {
      color: #43cea2;
    }
    @media (max-width: 400px) {
      .login-container { width: 98vw; padding: 30px 6vw; }
    }
  </style>
</head>
<body>
  <div class="animated-bg">
    <div class="bubble"></div>
    <div class="bubble"></div>
    <div class="bubble"></div>
    <div class="bubble"></div>
  </div>
  <div class="login-container">
    <div class="login-logo">kamao</div>
    <p class="login-title">Welcome Back! Please Login</p>
    <form>
      <div class="input-group">
        <label for="email">Email</label>
        <input type="email" id="email" placeholder="Enter your email" required autocomplete="username">
      </div>
      <div class="input-group">
        <label for="password">Password</label>
        <input type="password" id="password" placeholder="Enter password" required autocomplete="current-password">
      </div>
      <a class="forgot-link" href="#">Forgot Password?</a>
      <button class="login-btn" type="submit">Login</button>
    </form>
  </div>
  <script>
    // Simple animation feedback on login submit
    document.querySelector("form").addEventListener("submit", function(e){
      e.preventDefault();
      const btn = document.querySelector('.login-btn');
      btn.textContent = "Logging in...";
      btn.disabled = true;
      btn.style.opacity = 0.8;
      setTimeout(() => {
        btn.textContent = "Login";
        btn.disabled = false;
        btn.style.opacity = 1;
        alert("Login Successful! (Demo only)");
      }, 1200);
    });
  </script>
</body>
</html>
