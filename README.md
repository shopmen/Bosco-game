<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Игра: Заработай Токены</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f9;
            background-image: url('https://www.w3schools.com/w3images/coffee.jpg'); /* Замените на свой фон */
            background-size: cover;
            background-position: center;
        }
        h1 {
            color: #ffffff;
            font-size: 36px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.6);
        }
        #game-container {
            margin-top: 50px;
        }
        #clickButton {
            font-size: 30px;
            padding: 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            transition: transform 0.2s;
        }
        #clickButton:hover {
            transform: scale(1.1);
        }
        #score {
            font-size: 25px;
            margin-top: 20px;
            color: #fff;
        }
        #reward {
            font-size: 20px;
            margin-top: 10px;
            color: #ff9800;
        }
        #icon {
            width: 100px;
            margin-top: 30px;
        }
    </style>
</head>
<body>

    <h1>Привет! Начни зарабатывать токены!</h1>
    <div id="game-container">
        <button id="clickButton">
            <img src="https://www.w3schools.com/w3images/coffee.jpg" alt="Click me!" width="30" style="vertical-align: middle; margin-right: 10px;">Кликни меня!
        </button>
        <div id="score">Токены: 0</div>
        <div id="reward"></div>
        <img id="icon" src="https://upload.wikimedia.org/wikipedia/commons/6/6d/Gold_coin_icon.svg" alt="Icon"> <!-- Иконка для бонусов -->
    </div>

    <script>
        let tokens = 0;
        const clickButton = document.getElementById("clickButton");
        const scoreElement = document.getElementById("score");
        const rewardElement = document.getElementById("reward");

        clickButton.onclick = function() {
            tokens++;  // Увеличиваем количество токенов за каждый клик
            scoreElement.innerText = "Токены: " + tokens;

            // Выдача бонусов на каждом 10-м токене
            if (tokens % 10 === 0) {
                rewardElement.innerText = "Поздравляем! Вы заработали 10 токенов!";
            } else {
                rewardElement.innerText = "";  // Очистить сообщение о бонусе
            }
        };
    </script>

</body>
</html>