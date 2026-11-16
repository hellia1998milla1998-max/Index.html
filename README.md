<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>С Днём Рождения, Ева!</title>
    <link href="https://fonts.googleapis.com/css2?family=Comfortaa:wght@400;700&display=swap" rel="stylesheet">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        body {
            background-color: #fdf5f6; /* Молочно-розовый фон */
            font-family: 'Comfortaa', cursive;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            text-align: center;
            color: #6b4c4c;
            padding: 20px;
            transition: background-color 0.5s;
        }
        .container {
            background: white;
            padding: 40px 30px;
            border-radius: 30px;
            box-shadow: 0 10px 30px rgba(255, 182, 193, 0.3);
            max-width: 500px;
            width: 100%;
            position: relative;
            overflow: hidden;
        }
        /* Красивое сердечко на фоне */
        .container::before {
            content: "🎀";
            position: absolute;
            top: -20px;
            right: -20px;
            font-size: 80px;
            opacity: 0.1;
            transform: rotate(20deg);
        }
        .screen {
            display: none;
            animation: fadeIn 0.8s ease-in-out;
        }
        .screen.active {
            display: block;
        }
        h1 {
            font-size: 24px;
            margin-bottom: 20px;
            color: #d47b8b;
            line-height: 1.4;
        }
        p {
            font-size: 16px;
            line-height: 1.6;
            margin-bottom: 25px;
        }
        .highlight {
            color: #d47b8b;
            font-weight: bold;
        }
        button {
            background-color: #f7c4cc;
            color: white;
            border: none;
            padding: 15px 25px;
            border-radius: 20px;
            font-size: 16px;
            font-family: 'Comfortaa', cursive;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(247, 196, 204, 0.4);
            width: 100%;
        }
        button:hover {
            background-color: #f0a8b5;
            transform: translateY(-2px);
        }
        .btn-group {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .emoji {
            font-size: 50px;
            margin-bottom: 15px;
            display: inline-block;
            animation: float 2s infinite ease-in-out;
        }
        .heart-icon {
            color: #e38b9d;
            font-size: 20px;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
    </style>
</head>
<body>

    <div class="container">
        
        <!-- ЭКРАН 1: Приветствие -->
        <div class="screen active" id="screen1">
            <span class="emoji">🎀</span>
            <h1>Привет, Ева!</h1>
            <p>Сегодня особенный день, и у нас есть для тебя маленький сюрприз-тест от твоей лучшей подруги <span class="highlight">Ани</span>.</p>
            <p>Готова пройти его? Только честно отвечай на вопросы!</p>
            <button onclick="nextScreen(2)">Начать ✨</button>
        </div>

        <!-- ЭКРАН 2: Вопрос о танцах -->
        <div class="screen" id="screen2">
            <span class="emoji">💃</span>
            <h1>Вопрос №1</h1>
            <p>Как думаешь, кто сегодня будет сиять ярче всех на паркете, ведь Ева занимается <span class="highlight">бальными танцами</span>?</p>
            <div class="btn-group">
                <button onclick="nextScreen(3)">Конечно, Ева! 👑</button>
                <button onclick="nextScreen(3)">Звезда танцпола! ⭐</button>
            </div>
        </div>

        <!-- ЭКРАН 3: Вопрос от Ани -->
        <div class="screen" id="screen3">
            <span class="emoji">🩰</span>
            <h1>Вопрос №2</h1>
            <p>Что самое главное в этот день?</p>
            <div class="btn-group">
                <button onclick="nextScreen(4)">Улыбки и подарки 🎁</button>
                <button onclick="nextScreen(4)">Знать, что меня лю Аня! 💖</button>
            </div>
        </div>

        <!-- ЭКРАН 4: Много поздравлений от Ани -->
        <div class="screen" id="screen4">
            <span class="emoji">🥛🌸</span>
            <h1 style="font-size: 28px;">С 13-летием, Ева!</h1>
            <p>Аня передаёт тебе огромный привет и вот эти слова:</p>
            <div style="background: #fff0f3; padding: 20px; border-radius: 15px; margin-bottom: 20px; text-align: left; font-size: 14px; line-height: 1.8;">
                «Евочка, с днём рождения! 13 лет — это круто! Желаю тебе самых красивых побед на бальных танцах, пусть каждый твой выход на паркет будет как в сказке. Ты невероятно талантливая и красивая. <br><br>
                <b>Я тебя очень-очень лю! 💕</b> Ты моя самая лучшая подруга, спасибо, что ты есть. Пусть этот год принесёт тебе море счастья, крутых эмоций и исполнения всех желаний!»
            </div>
            <p class="highlight" style="font-size: 18px;">С любовью, твоя Аня 💌</p>
            <button onclick="nextScreen(5)">Финальный сюрприз 🎉</button>
        </div>

        <!-- ЭКРАН 5: Финал (конфетти) -->
        <div class="screen" id="screen5">
            <span class="emoji">🎂</span>
            <h1>С Днём Рождения! 🎊</h1>
            <p>Ты прошла тест! Ты официально самая лучшая 13-летняя танцовщица на свете.</p>
            <p>Аня очень тебя любит и всегда рядом! <span class="heart-icon">❤️</span></p>
            <button onclick="triggerConfetti()" style="background-color: #d47b8b;">Нажми для салюта! 🎆</button>
        </div>

    </div>

    <!-- Простой скрипт для конфетти (без сторонних библиотек) -->
    <script>
        function nextScreen(screenNumber) {
            document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
            document.getElementById('screen' + screenNumber).classList.add('active');
        }

        // Функция для эффекта салюта из эмодзи
        function triggerConfetti() {
            const emojis = ['🌸', '💖', '🎀', '✨', '🥛', '🩰'];
            for (let i = 0; i < 30; i++) {
                let el = document.createElement('div');
                el.innerText = emojis[Math.floor(Math.random() * emojis.length)];
                el.style.position = 'fixed';
                el.style.left = Math.random() * 100 + 'vw';
                el.style.top = '-5vh';
                el.style.fontSize = (Math.random() * 20 + 15) + 'px';
                el.style.zIndex = '1000';
                el.style.transition = 'transform 3s linear, opacity 3s';
                document.body.appendChild(el);

                setTimeout(() => {
                    el.style.transform = 'translateY(110vh) rotate(' + (Math.random() * 360) + 'deg)';
                    el.style.opacity = '0';
                }, 50);

                setTimeout(() => {
                    el.remove();
                }, 3500);
            }
        }
    </script>
</body>
</html>
