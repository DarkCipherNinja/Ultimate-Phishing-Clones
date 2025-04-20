<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Instagram Login Clone</title>
  <style>
    * {
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(160deg, #1e1e1e, #0d0d0d);
      color: #fff;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      position: relative;
    }

    .language {
      position: absolute;
      top: 15px;
      color: #ccc;
      font-size: 14px;
      cursor: pointer;
    }

    .logo {
      width: 60px;
      margin: 40px 0 20px;
    }

    .login-box {
      width: 90%;
      max-width: 320px;
      display: flex;
      flex-direction: column;
      gap: 12px;
    }

    .login-box input {
      padding: 12px;
      border: 1px solid #444;
      border-radius: 10px;
      background-color: #2a2a2a;
      color: #fff;
      font-size: 14px;
    }

    .login-box input::placeholder {
      color: #aaa;
    }

    .login-box button {
      padding: 12px;
      background-color: #0095f6;
      border: none;
      border-radius: 999px;
      color: white;
      font-weight: bold;
      font-size: 14px;
      cursor: pointer;
      margin-top: 10px;
    }

    .forgot {
      text-align: center;
      margin-top: 10px;
      font-size: 14px;
      color: #b3b3b3;
    }

    .forgot a {
      color: #b3b3b3;
      text-decoration: none;
    }

    .create {
      margin-top: 30px;
      width: 90%;
      max-width: 320px;
      border: 1px solid #444;
      border-radius: 999px;
      padding: 12px;
      text-align: center;
      font-weight: bold;
      color: #0095f6;
      background-color: transparent;
      cursor: pointer;
    }

    .meta-logo {
      width: 60px;
      margin-top: 20px;
      opacity: 0.8;
    }

    /* Language Popup */
    .language-popup {
      position: absolute;
      top: 50px;
      background-color: #2b2b2b;
      border: 1px solid #444;
      border-radius: 8px;
      padding: 10px;
      display: none;
      flex-direction: column;
      gap: 8px;
      z-index: 10;
    }

    .language-popup div {
      color: #fff;
      cursor: pointer;
      padding: 6px 10px;
      border-radius: 4px;
    }

    .language-popup div:hover {
      background-color: #444;
    }
  </style>
</head>
<body>
  <div class="language" onclick="toggleLanguagePopup()">English (UK)</div>
  <div class="language-popup" id="languagePopup">
    <div onclick="setLanguage('English (UK)')">English (UK)</div>
    <div onclick="setLanguage('Español')">Español</div>
    <div onclick="setLanguage('Français')">Français</div>
    <div onclick="setLanguage('Deutsch')">Deutsch</div>
    <div onclick="setLanguage('हिन्दी')">हिन्दी</div>
  </div>

  <img src="https://static.cdninstagram.com/rsrc.php/v4/yq/r/_7cAFFbc4Pr.png" alt="Instagram Logo" class="logo"/>

  <div class="login-box">
    <input type="text" placeholder="Username, email address or mobile number" />
    <input type="password" placeholder="Password" />
    <button>Log in</button>
  </div>

  <div class="forgot">
    <a href="#">Forgotten password?</a>
  </div>

  <div class="create">Create new account</div>

  <img src="https://static.cdninstagram.com/rsrc.php/v4/y3/r/aAfprBW6TIe.png" alt="Meta Logo" class="meta-logo" />

  <script>
    const popup = document.getElementById('languagePopup');
    const langBtn = document.querySelector('.language');

    function toggleLanguagePopup() {
      popup.style.display = popup.style.display === 'flex' ? 'none' : 'flex';
    }

    function setLanguage(language) {
      langBtn.innerText = language;
      popup.style.display = 'none';
    }

    document.addEventListener('click', (e) => {
      if (!popup.contains(e.target) && e.target !== langBtn) {
        popup.style.display = 'none';
      }
    });
  </script>
</body>
</html>
