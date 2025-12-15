<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Invite App</title>
  <script src="https://telegram.org/js/telegram-web-app.js"></script>
</head>
<body>
  <h2>Invite Mini App</h2>

  <!-- Поле для введення групи -->
  <input id="group" placeholder="@groupname"><br><br>

  <!-- Поле для введення користувачів -->
  <textarea id="users" rows="5" placeholder="user1
user2"></textarea><br><br>

  <!-- Кнопка запуску -->
  <button onclick="start()">START</button>

  <script>
    // Підключення до Telegram Web App
    const tg = window.Telegram.WebApp;
    tg.expand();

    // Функція START
    function start() {
      const group = document.getElementById("group").value;
      const users = document.getElementById("users").value
                        .split("\n")
                        .map(u => u.trim())
                        .filter(u => u.length > 0);

      if(!group || users.length === 0){
          alert("Вкажіть групу та хоча б одного користувача!");
          return;
      }

      // Надсилаємо дані боту
      tg.sendData(JSON.stringify({
        group: group,
        users: users
      }));

      // Закриваємо Mini App після відправки
      tg.close();
    }
  </script>
</body>
</html>
