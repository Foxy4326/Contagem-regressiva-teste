<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contagem Regressiva para 2026 | Bíblia Sagrada</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0d1b2a, #1b263b, #2c3e50);
            color: white;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            overflow-x: hidden;
            position: relative;
        }

        /* MENU SUPERIOR */
        .top-bar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 1rem 2rem;
            background: rgba(13, 27, 42, 0.9);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.4);
            border-bottom: 1px solid rgba(255, 215, 0, 0.3);
        }

        .logo {
            font-weight: bold;
            font-size: 1.5rem;
            letter-spacing: 1px;
            color: #FFD700;
            text-shadow: 0 0 8px rgba(255, 215, 0, 0.7);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo i {
            font-size: 1.3rem;
        }

        .date-display {
            font-size: 1rem;
            text-align: right;
            line-height: 1.4;
        }

        .weekday {
            font-weight: 600;
            color: #FFD700;
        }

        .full-date {
            font-size: 0.9rem;
            color: #ccc;
        }

        /* CONTEÚDO PRINCIPAL */
        main {
            margin-top: 80px;
            z-index: 10;
            padding: 0 20px;
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
            animation: fadeInDown 1s ease-in-out;
            color: #FFD700;
            font-weight: 800;
        }

        .subtitle {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: #e0e0e0;
            max-width: 600px;
            line-height: 1.6;
        }

        .container {
            display: flex;
            gap: 1.5rem;
            margin: 2rem 0;
            flex-wrap: wrap;
            justify-content: center;
        }

        .time-segment {
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 1.5rem;
            min-width: 120px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 215, 0, 0.2);
            transition: transform 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .time-segment:hover {
            transform: translateY(-5px);
            border-color: rgba(255, 215, 0, 0.6);
        }

        .number {
            font-size: 3rem;
            font-weight: bold;
            color: #ffdd59;
            text-shadow: 0 0 15px rgba(255, 221, 89, 0.7);
        }

        .label {
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-top: 0.5rem;
            color: #e0e0e0;
        }

        /* BOTÃO DO CANAL */
        .bible-btn {
            margin-top: 2rem;
            padding: 1.2rem 2.5rem;
            background: linear-gradient(135deg, #8B0000, #4B0000);
            color: #FFD700;
            font-size: 1.3rem;
            font-weight: 700;
            border: 2px solid #FFD700;
            border-radius: 50px;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 1rem;
            box-shadow: 0 5px 20px rgba(139, 0, 0, 0.5);
            transition: all 0.3s ease;
            text-decoration: none;
            animation: pulse 2s infinite;
        }

        .bible-btn:hover {
            transform: translateY(-3px) scale(1.03);
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.4);
            background: linear-gradient(135deg, #a52a2a, #6b0f0f);
        }

        .bible-btn i {
            font-size: 1.6rem;
        }

        /* TEXTO/BOTÃO "EM BREVE LANÇARÁ EM 2026" */
        .launch-info {
            margin-top: 1.5rem;
            padding: 1rem 2.5rem;
            background: rgba(255, 255, 255, 0.1);
            color: #FFD700;
            font-size: 1.2rem;
            font-weight: 700;
            border: 1px solid rgba(255, 215, 0, 0.5);
            border-radius: 50px;
            display: inline-block;
            backdrop-filter: blur(5px);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
            animation: fadeIn 1.5s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* BOTÃO VÍDEO EM BREVE */
        .video-soon-btn {
            margin-top: 1.5rem;
            padding: 1rem 2.5rem;
            background: linear-gradient(135deg, #6a0dad, #3b006b);
            color: #fff;
            font-size: 1.2rem;
            font-weight: 700;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            box-shadow: 0 5px 20px rgba(106, 13, 173, 0.4);
            transition: all 0.4s ease;
            text-decoration: none;
            animation: glow 2s infinite alternate;
        }

        .video-soon-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(155, 50, 255, 0.6);
            background: linear-gradient(135deg, #8b28d9, #5a00b3);
        }

        .video-soon-btn i {
            font-size: 1.3rem;
            color: #FFD700;
        }

        @keyframes glow {
            from { box-shadow: 0 5px 20px rgba(106, 13, 173, 0.4); }
            to { box-shadow: 0 5px 25px rgba(186, 85, 255, 0.8); }
        }

        /* SEÇÃO DE CHAT */
        .chat-section {
            margin-top: 3rem;
            background: rgba(20, 30, 50, 0.7);
            padding: 1.5rem;
            border-radius: 20px;
            max-width: 600px;
            width: 90%;
        }

        .chat-section h3 {
            color: #FFD700;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        #chatBox {
            height: 200px;
            overflow-y: auto;
            background: rgba(0,0,0,0.3);
            padding: 1rem;
            border-radius: 10px;
            margin-bottom: 1rem;
            font-size: 0.95rem;
            line-height: 1.5;
        }

        #chatBox div {
            margin-bottom: 0.5rem;
            padding: 0.5rem;
            background: rgba(255,255,255,0.05);
            border-radius: 8px;
        }

        .chat-input-area {
            display: flex;
            gap: 0.5rem;
        }

        #chatInput {
            flex: 1;
            padding: 0.8rem;
            border-radius: 50px;
            border: none;
            outline: none;
            font-size: 1rem;
            background: rgba(255,255,255,0.1);
            color: white;
        }

        #chatInput::placeholder {
            color: #aaa;
        }

        .send-btn {
            background: #FFD700;
            color: #1a1a2e;
            border: none;
            padding: 0 1.5rem;
            border-radius: 50px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 4px 10px rgba(255, 215, 0, 0.3);
        }

        .send-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(255, 215, 0, 0.4);
        }

        .chat-footer {
            font-size: 0.85rem;
            color: #aaa;
            margin-top: 0.5rem;
        }

        @keyframes pulse {
            0% { box-shadow: 0 5px 20px rgba(139, 0, 0, 0.5); }
            50% { box-shadow: 0 5px 20px rgba(255, 215, 0, 0.6); }
            100% { box-shadow: 0 5px 20px rgba(139, 0, 0, 0.5); }
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @media (max-width: 768px) {
            .top-bar {
                flex-direction: column;
                gap: 0.5rem;
                padding: 1rem;
                text-align: center;
            }

            .logo {
                font-size: 1.3rem;
            }

            .date-display {
                text-align: center;
            }

            h1 {
                font-size: 2.5rem;
            }

            .subtitle {
                font-size: 1rem;
            }

            .container {
                gap: 1rem;
            }

            .time-segment {
                min-width: 100px;
                padding: 1rem;
            }

            .number {
                font-size: 2.5rem;
            }

            .bible-btn, .video-soon-btn, .launch-info {
                padding: 1rem 2rem;
                font-size: 1.1rem;
            }

            .chat-section {
                margin-top: 2rem;
                padding: 1rem;
            }

            #chatBox {
                height: 150px;
            }
        }
    </style>
</head>
<body>

    <!-- Menu Superior -->
    <div class="top-bar">
        <div class="logo">
            <i class="fas fa-bible"></i> Bíblia Sagrada
        </div>
        <div class="date-display">
            <div class="weekday" id="currentWeekday">Carregando...</div>
            <div class="full-date" id="currentDate">Carregando...</div>
        </div>
    </div>

    <!-- Conteúdo Principal -->
    <main>
        <h1>CONTAGEM REGRESSIVA</h1>
        <p class="subtitle">Aguardando o grande momento em 2026. Cada segundo conta para a transformação espiritual.</p>

        <div class="container">
            <div class="time-segment">
                <div class="number" id="days">00</div>
                <div class="label">Dias</div>
            </div>
            <div class="time-segment">
                <div class="number" id="hours">00</div>
                <div class="label">Horas</div>
            </div>
            <div class="time-segment">
                <div class="number" id="minutes">00</div>
                <div class="label">Minutos</div>
            </div>
            <div class="time-segment">
                <div class="number" id="seconds">00</div>
                <div class="label">Segundos</div>
            </div>
        </div>

        <a href="https://www.bible.com/pt-BR" target="_blank" class="bible-btn">
            <i class="fas fa-book-bible"></i> Ler Bíblia Online
        </a>

        <!-- NOVO: Texto "Em breve lançará em 2026" -->
        <div class="launch-info">
            ✨ Em breve lançará em 2026
        </div>

        <button class="video-soon-btn">
            <i class="fas fa-video"></i> Vídeo em Breve
        </button>
    </main>

    <!-- Seção de Chat -->
    <div class="chat-section">
        <h3><i class="fas fa-comments"></i> Chat Comunitário</h3>
        <div id="chatBox">
            <div><strong>Sistema:</strong> Bem-vindo ao chat espiritual! 🙏</div>
        </div>
        <div class="chat-input-area">
            <input type="text" id="chatInput" placeholder="Digite sua mensagem..." maxlength="100">
            <button class="send-btn" id="sendChatBtn">Enviar</button>
        </div>
        <div class="chat-footer">
            Seja respeitoso. Este é um espaço de fé e comunhão.
        </div>
    </div>

    <script>
        // Atualiza data e dia da semana
        function updateDate() {
            const now = new Date();
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            document.getElementById('currentDate').textContent = now.toLocaleDateString('pt-BR', options);
            document.getElementById('currentWeekday').textContent = now.toLocaleDateString('pt-BR', { weekday: 'long' }).charAt(0).toUpperCase() + now.toLocaleDateString('pt-BR', { weekday: 'long' }).slice(1);
        }
        updateDate();
        setInterval(updateDate, 60000); // Atualiza a cada minuto

        // Contagem regressiva para 1º de janeiro de 2026
        function updateCountdown() {
            const targetDate = new Date("January 1, 2026 00:00:00").getTime();
            const now = new Date().getTime();
            const distance = targetDate - now;

            if (distance < 0) {
                document.getElementById("days").innerText = "00";
                document.getElementById("hours").innerText = "00";
                document.getElementById("minutes").innerText = "00";
                document.getElementById("seconds").innerText = "00";
                return;
            }

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("days").innerText = days.toString().padStart(2, '0');
            document.getElementById("hours").innerText = hours.toString().padStart(2, '0');
            document.getElementById("minutes").innerText = minutes.toString().padStart(2, '0');
            document.getElementById("seconds").innerText = seconds.toString().padStart(2, '0');
        }

        updateCountdown();
        setInterval(updateCountdown, 1000);

        // Chat
        const chatInput = document.getElementById('chatInput');
        const sendChatBtn = document.getElementById('sendChatBtn');
        const chatBox = document.getElementById('chatBox');

        sendChatBtn.addEventListener('click', sendMessage);
        chatInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') sendMessage();
        });

        function sendMessage() {
            const message = chatInput.value.trim();
            if (message === '') return;

            const messageDiv = document.createElement('div');
            messageDiv.innerHTML = `<strong>Você:</strong> ${message}`;
            chatBox.appendChild(messageDiv);

            chatInput.value = '';
            chatBox.scrollTop = chatBox.scrollHeight; // Scroll automático

            // Resposta automática (opcional)
            setTimeout(() => {
                const replyDiv = document.createElement('div');
                replyDiv.innerHTML = `<strong>Sistema:</strong> Que Deus te abençoe! 🙏`;
                chatBox.appendChild(replyDiv);
                chatBox.scrollTop = chatBox.scrollHeight;
            }, 1000);
        }
    </script>

</body>
</html>
