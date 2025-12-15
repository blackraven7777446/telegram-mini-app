# telegram-mini-app

[index.html](https://github.com/user-attachments/files/24176991/index.html)
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Invite App</title>
  <script src="https://telegram.org/js/telegram-web-app.js"></script>
</head>
<body>
  <h2>Invite Mini App</h2>

  <input id="group" placeholder="@groupname"><br><br>

  <textarea id="users" rows="5" placeholder="user1
user2"></textarea><br><br>

  <button onclick="start()">START</button>

  <script>
    const tg = window.Telegram.WebApp;
    tg.expand();

    function start() {
      alert("Кнопка працює! 🎉");
    }
  </script>
</body>
</html>
