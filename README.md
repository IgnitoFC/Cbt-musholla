<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CBT Lomba Kuis Musholla Nurul Ikhwan - Login</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f0f0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .login-box {
      background: white;
      padding: 40px;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
      border-radius: 8px;
      text-align: center;
      width: 300px;
    }
    input {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    button {
      background: #2c7be5;
      color: white;
      padding: 10px;
      border: none;
      width: 100%;
      border-radius: 4px;
      cursor: pointer;
    }
    button:hover {
      background: #1a5ecc;
    }
    .error {
      color: red;
      font-size: 0.9em;
    }
  </style>
</head>
<body>
  <div class="login-box">
    <h2>Login CBT</h2>
    <input type="text" id="username" placeholder="Username">
    <input type="password" id="password" placeholder="Password">
    <input type="text" id="token" placeholder="Token">
    <div class="error" id="error"></div>
    <button onclick="login()">Masuk</button>
  </div>

  <script>
    const validUser = {
      username: "peserta1",
      password: "cbt123",
    };

    const tokenKey = "tokenCbt";

    function generateToken() {
      const token = Math.random().toString(36).substring(2, 8).toUpperCase();
      localStorage.setItem(tokenKey, token);
      console.log("[Panitia Only] Token saat ini:", token);
    }

    setInterval(generateToken, 600000); // ubah setiap 10 menit
    if (!localStorage.getItem(tokenKey)) generateToken();

    function login() {
      const u = document.getElementById("username").value;
      const p = document.getElementById("password").value;
      const t = document.getElementById("token").value;
      const currentToken = localStorage.getItem(tokenKey);

      if (u === validUser.username && p === validUser.password && t === currentToken) {
        window.location.href = "quiz.html";
      } else {
        document.getElementById("error").textContent = "Login gagal. Cek kembali data Anda.";
      }
    }
  </script>
</body>
</html>


Sudah saya tambahkan sistem login dengan username, password, dan token yang berubah setiap 10 menit.
Berikut akun peserta yang bisa login:

Username: peserta1

Password: cbt123


Token akan tampil di konsol (untuk panitia). Nanti halaman soal bisa disambungkan ke quiz.html. Siap bantu lanjut jika ingin ubah soal atau tambah peserta.

