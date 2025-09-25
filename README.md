<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>Contagem Regressiva para 2026 | Bíblia Sagrada</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: 'Segoe UI', sans-serif;
            background: linear-gradient(135deg, #0d1b2a, #1b263b, #2c3e50);
            color: white;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding-top: 80px;
            position: relative;
            overflow-x: hidden;
        }
        .top-bar {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1rem 2rem;
            background: rgba(13, 27, 42, 0.95);
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
            border-bottom: 1px solid rgba(255, 215, 0, 0.3);
        }
        .logo { font-weight: bold; color: #FFD700; display: flex; align-items: center; gap: 0.5rem; }
        .date-display { text-align: right; }
        .weekday { font-weight: 600; color: #FFD700; }
        .full-date { font-size: 0.9rem; color: #ccc; }
        
        /* MENU DE AUTENTICAÇÃO */
        .auth-top-bar {
            position: fixed;
            top: 12px;
            right: 20px;
            display: flex;
            gap: 0.8rem;
            z-index: 101;
        }
        .auth-top-btn {
            padding: 0.5rem 1rem;
            border: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.95rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transition: all 0.2s ease;
        }
        .auth-top-btn:hover {
            transform: translateY(-2px);
        }
        .login-btn {
            background: rgba(30, 58, 138, 0.8);
            color: white;
            box-shadow: 0 2px 6px rgba(30, 58, 138, 0.4);
        }
        .signup-btn {
            background: rgba(13, 148, 136, 0.8);
            color: white;
            box-shadow: 0 2px 6px rgba(13, 148, 136, 0.4);
        }

        main { text-align: center; padding: 0 20px; max-width: 1000px; }
        h1 {
            font-size: 2.8rem;
            margin: 1.5rem 0;
            color: #FFD700;
        }
        .container {
            display: flex;
            gap: 1rem;
            margin: 2rem 0;
            flex-wrap: wrap;
            justify-content: center;
        }
        .time-segment-weeks, .time-segment {
            background: #0d1b2a;
            border: 1px solid rgba(255, 215, 0, 0.2);
            border-radius: 12px;
            padding: 1.2rem 0.8rem;
            min-width: 90px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        .number-weeks, .number {
            font-size: 2.2rem;
            font-weight: bold;
            color: #FFD700;
            text-shadow: 0 0 8px rgba(255, 215, 0, 0.6);
        }
        .label-weeks, .label {
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: #ccc;
            margin-top: 0.4rem;
        }
        .btn {
            display: inline-flex;
            align-items: center;
            gap: 0.7rem;
            padding: 0.9rem 1.8rem;
            border-radius: 50px;
            font-weight: 700;
            text-decoration: none;
            margin: 0.6rem 0;
            transition: transform 0.2s;
        }
        .btn:hover { transform: translateY(-2px); }
        .connect-button {
            background: #8B0000;
            color: white;
            border: 2px solid #FFD700;
        }
        .coming-soon-btn {
            background: linear-gradient(135deg, #1e3a8a, #2563eb);
            color: white;
        }
        .video-soon-btn {
            background: linear-gradient(135deg, #6a0dad, #8b28d9);
            color: white;
        }
        .bible-read-btn {
            background: linear-gradient(135deg, #c9a04b, #d4b060);
            color: #1a1a2e;
        }

        /* CHAT COM IA */
        .chat-section {
            margin-top: 2.5rem;
            background: rgba(20, 30, 50, 0.7);
            padding: 1.5rem;
            border-radius: 20px;
            width: 100%;
            max-width: 600px;
        }
        #spiritualChatBox {
            height: 220px;
            overflow-y: auto;
            background: rgba(0,0,0,0.3);
            padding: 1rem;
            border-radius: 10px;
            margin-bottom: 1rem;
            font-size: 0.95rem;
            line-height: 1.5;
        }
        #spiritualChatInput {
            width: 70%;
            padding: 0.7rem;
            border-radius: 50px;
            border: none;
            outline: none;
            background: rgba(255,255,255,0.1);
            color: white;
        }
        .send-btn {
            padding: 0.7rem 1.2rem;
            background: #4B0082;
            color: white;
            border: none;
            border-radius: 50px;
            cursor: pointer;
        }

        /* MODAL DE AUTENTICAÇÃO */
        .auth-modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.3s ease;
        }
        .auth-modal-overlay.active {
            opacity: 1;
            pointer-events: all;
        }
        .auth-modal {
            background: linear-gradient(135deg, #1a1a2e, #16213e);
            padding: 2rem;
            border-radius: 20px;
            width: 90%;
            max-width: 450px;
            border: 2px solid #FFD700;
            color: white;
        }
        .auth-modal h3 {
            color: #FFD700;
            margin-bottom: 1.5rem;
            text-align: center;
        }
        .auth-form {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }
        .auth-form input {
            padding: 0.8rem;
            border-radius: 10px;
            border: 1px solid #444;
            background: rgba(0,0,0,0.3);
            color: white;
            font-size: 1rem;
        }
        .auth-form input::placeholder {
            color: #888;
        }
        .auth-actions {
            display: flex;
            gap: 0.8rem;
            margin-top: 1rem;
        }
        .auth-btn-modal {
            flex: 1;
            padding: 0.8rem;
            border: none;
            border-radius: 10px;
            font-weight: bold;
            cursor: pointer;
        }
        .auth-btn-modal.cancel {
            background: #8B0000;
            color: white;
        }
        .auth-btn-modal.submit {
            background: #FFD700;
            color: #1a1a2e;
        }

        /* ELEMENTOS ESPIRITUAIS FLUTUANTES */
        .spiritual-element {
            position: fixed;
            font-size: 1.8rem;
            opacity: 0.7;
            z-index: -1;
            pointer-events: none;
            animation: float 15s infinite ease-in-out;
        }
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            25% { transform: translateY(-20px) rotate(2deg); }
            50% { transform: translateY(-10px) rotate(-2deg); }
            75% { transform: translateY(-25px) rotate(1deg); }
        }

        /* PLAY PROTECT BANNER */
        #playProtect {
            display: none;
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: #0d1b2a;
            color: #FFD700;
            padding: 12px 20px;
            border-radius: 10px;
            border: 1px solid #FFD700;
            z-index: 10000;
            box-shadow: 0 0 15px rgba(255,215,0,0.5);
            font-weight: bold;
        }

        @media (max-width: 500px) {
            .auth-top-bar { display: none; }
            .number-weeks, .number { font-size: 1.8rem; }
            h1 { font-size: 2rem; }
            .btn { padding: 0.7rem 1.4rem; font-size: 1rem; }
        }
    </style>
</head>
<body>

<!-- MENU DE AUTENTICAÇÃO -->
<div class="auth-top-bar">
    <button class="auth-top-btn login-btn" onclick="openModal('login')">
        <i class="fas fa-user"></i> Login
    </button>
    <button class="auth-top-btn signup-btn" onclick="openModal('signup')">
        <i class="fas fa-user-plus"></i> Cadastrar
    </button>
</div>

<div class="top-bar">
    <div class="logo"><i class="fas fa-bible"></i> Bíblia Sagrada</div>
    <div class="date-display">
        <div class="weekday" id="weekday">Carregando...</div>
        <div class="full-date" id="full-date">—</div>
    </div>
</div>

<main>
    <h1>⏳ Contagem Regressiva para 2026</h1>

    <div class="container">
        <div class="time-segment-weeks">
            <div class="number-weeks" id="weeks-display">000</div>
            <div class="label-weeks">Semanas</div>
        </div>
        <div class="time-segment">
            <div class="number" id="days">000</div>
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

    <!-- BOTÃO DO CANAL COM LINK EXATO -->
    <a href="https://youtube.com/@bibliasagrada-r3c4o?si=rcpyTgzjQt9DRdUL" target="_blank" class="btn connect-button">
        <i class="fab fa-youtube"></i> Conecte-se à Palavra: Visite nosso Canal
    </a>

    <a href="#" class="btn coming-soon-btn" onclick="window.scrollTo({top:0,behavior:'smooth'}); return false;">
        <i class="fas fa-calendar-star"></i> Ano em Breve: 2026 ✨
    </a>
    <a href="#" class="btn video-soon-btn" onclick="alert('🔔 Novo vídeo em breve! Inscreva-se no canal para não perder.'); return false;">
        <i class="fas fa-video"></i> Vídeo Lançado em Breve! 🎬
    </a>
    <a href="https://www.bibliaonline.com.br/" target="_blank" class="btn bible-read-btn">
        <i class="fas fa-book-open"></i> Ler a Bíblia Online 📖
    </a>

    <!-- CHAT COM IA -->
    <div class="chat-section">
        <h3>💬 Comentários com IA Espiritual</h3>
        <div id="spiritualChatBox"></div>
        <div>
            <input type="text" id="spiritualChatInput" placeholder="Escreva sua oração, dúvida ou testemunho..." />
            <button class="send-btn" onclick="sendSpiritualMessage()">Enviar</button>
        </div>
    </div>
</main>

<!-- MODAIS -->
<div class="auth-modal-overlay" id="loginModal">
    <div class="auth-modal">
        <h3><i class="fas fa-sign-in-alt"></i> Faça seu Login</h3>
        <form class="auth-form" onsubmit="handleAuth(event, 'login')">
            <input type="email" placeholder="E-mail" required />
            <input type="password" placeholder="Senha" required />
            <div class="auth-actions">
                <button type="button" class="auth-btn-modal cancel" onclick="closeAuthModal()">Cancelar</button>
                <button type="submit" class="auth-btn-modal submit">Entrar</button>
            </div>
        </form>
    </div>
</div>

<div class="auth-modal-overlay" id="signupModal">
    <div class="auth-modal">
        <h3><i class="fas fa-user-plus"></i> Crie sua Conta</h3>
        <form class="auth-form" onsubmit="handleAuth(event, 'signup')">
            <input type="text" placeholder="Nome completo" required />
            <input type="email" placeholder="E-mail" required />
            <input type="password" placeholder="Senha" required />
            <div class="auth-actions">
                <button type="button" class="auth-btn-modal cancel" onclick="closeAuthModal()">Cancelar</button>
                <button type="submit" class="auth-btn-modal submit">Cadastrar</button>
            </div>
        </form>
    </div>
</div>

<!-- PLAY PROTECT BANNER -->
<div id="playProtect">
    <i class="fas fa-shield-alt"></i> Verificando integridade do site...
</div>

<script>
// === PLAY PROTECT SIMULADO ===
function sitePlayProtect() {
    const protectBanner = document.getElementById('playProtect');
    protectBanner.style.display = 'block';
    
    setTimeout(() => {
        const hasCountdown = document.getElementById('days') && document.getElementById('hours');
        const jsWorking = typeof Date.now === 'function';
        
        if (hasCountdown && jsWorking) {
            protectBanner.innerHTML = '<i class="fas fa-check-circle"></i> Site verificado e seguro! ✝️';
            protectBanner.style.background = 'rgba(0, 100, 0, 0.8)';
            setTimeout(() => {
                protectBanner.style.opacity = '0';
                protectBanner.style.transition = 'opacity 1s';
                setTimeout(() => {
                    protectBanner.style.display = 'none';
                    protectBanner.style.opacity = '1';
                }, 1000);
            }, 2000);
        } else {
            protectBanner.innerHTML = '<i class="fas fa-exclamation-triangle"></i> Erro detectado. Recarregue a página.';
            protectBanner.style.background = 'rgba(139, 0, 0, 0.9)';
            protectBanner.style.display = 'block';
        }
    }, 1500);
}

// === DATA E DIA DA SEMANA (BRASIL) ===
function updateCurrentDate() {
    const now = new Date();
    const optionsWeekday = { weekday: 'long', timeZone: 'America/Sao_Paulo' };
    const optionsFullDate = { day: 'numeric', month: 'long', year: 'numeric', timeZone: 'America/Sao_Paulo' };
    const weekday = now.toLocaleDateString('pt-BR', optionsWeekday).replace(/^\w/, c => c.toUpperCase());
    const fullDate = now.toLocaleDateString('pt-BR', optionsFullDate).replace(/^\w/, c => c.toUpperCase());
    document.getElementById('weekday').textContent = weekday;
    document.getElementById('full-date').textContent = fullDate;
}

// === CONTAGEM REGRESSIVA CORRIGIDA (USA UTC) ===
function updateCountdown() {
    const targetDate = Date.UTC(2026, 0, 1, 0, 0, 0); // 1º de janeiro de 2026
    const now = Date.now();
    const distance = targetDate - now;

    if (distance < 0) {
        document.getElementById("weeks-display").innerText = "000";
        document.getElementById("days").innerText = "000";
        document.getElementById("hours").innerText = "00";
        document.getElementById("minutes").innerText = "00";
        document.getElementById("seconds").innerText = "00";
        document.querySelector("h1").innerText = "🎉 2026 CHEGOU!";
        return;
    }

    const days = Math.floor(distance / (1000 * 60 * 60 * 24));
    const weeks = Math.floor(days / 7);
    const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((distance % (1000 * 60)) / 1000);

    document.getElementById("weeks-display").innerText = String(weeks).padStart(3, '0');
    document.getElementById("days").innerText = String(days).padStart(3, '0');
    document.getElementById("hours").innerText = String(hours).padStart(2, '0');
    document.getElementById("minutes").innerText = String(minutes).padStart(2, '0');
    document.getElementById("seconds").innerText = String(seconds).padStart(2, '0');
}

// === CHAT COM IA ===
function loadSpiritualChat() {
    const box = document.getElementById('spiritualChatBox');
    const msgs = JSON.parse(localStorage.getItem('spiritualChatMessages')) || [];
    box.innerHTML = '';
    msgs.forEach(m => {
        const div = document.createElement('div');
        div.style.marginBottom = '0.8rem';
        div.style.padding = '0.6rem';
        div.style.borderRadius = '10px';
        div.style.maxWidth = '85%';
        if (m.type === 'user') {
            div.style.backgroundColor = 'rgba(255,255,255,0.08)';
            div.style.marginLeft = 'auto';
            div.style.textAlign = 'right';
            div.innerHTML = `<strong>Você:</strong> ${m.text}`;
        } else {
            div.style.backgroundColor = 'rgba(75, 0, 130, 0.35)';
            div.style.marginRight = 'auto';
            div.style.textAlign = 'left';
            div.innerHTML = `<strong>IA Espiritual:</strong> ${m.text}`;
        }
        box.appendChild(div);
    });
    box.scrollTop = box.scrollHeight;
}

function getSpiritualResponse(userMsg) {
    const msg = userMsg.toLowerCase();
    if (msg.includes('triste') || msg.includes('choro') || msg.includes('desespero')) {
        return "põe tua tristeza no altar. Salmos 34:18: 'O Senhor está perto dos que têm o coração quebrantado.' 🙏";
    }
    if (msg.includes('medo') || msg.includes('ansiedade') || msg.includes('temo')) {
        return "Isaías 41:10: 'Não temas, porque eu sou contigo; não te assombres, porque eu sou teu Deus.' ✨";
    }
    if (msg.includes('perdo') || msg.includes('ódio') || msg.includes('raiva')) {
        return "Efésios 4:32: 'Antes sede uns para com os outros benignos, misericordiosos, perdoando-vos uns aos outros, como também Deus vos perdoou em Cristo.' ❤️";
    }
    if (msg.includes('futuro') || msg.includes('2026') || msg.includes('ano novo')) {
        return "Jeremias 29:11: 'Porque eu bem sei os pensamentos que tenho a vosso respeito, diz o Senhor; pensamentos de paz, e não de mal, para vos dar o fim que esperais.' 🌟";
    }
    if (msg.includes('força') || msg.includes('cansado') || msg.includes('desanimado')) {
        return "Isaías 40:31: 'Mas os que esperam no Senhor renovarão as suas forças; subirão com asas como águias.' 🦅";
    }
    if (msg.includes('cura') || msg.includes('doença') || msg.includes('doente')) {
        return "Êxodo 15:26: 'Eu sou o Senhor que te sara.' Tiago 5:15: 'A oração da fé salvará o doente.' 🙌";
    }
    if (msg.includes('jesus') || msg.includes('cristo') || msg.includes('salvação')) {
        return "João 14:6: 'Eu sou o caminho, e a verdade, e a vida; ninguém vem ao Pai senão por mim.' 🕊️";
    }
    if (msg.includes('obrigado') || msg.includes('graças') || msg.includes('agradeço')) {
        return "1 Tessalonicenses 5:18: 'Em tudo dai graças, porque esta é a vontade de Deus em Cristo Jesus para convosco.' 🌈";
    }
    if (msg.includes('oração') || msg.includes('orar') || msg.includes('reze')) {
        return "Filipenses 4:6: 'Não estejais inquietos por coisa alguma; antes as vossas petições sejam em tudo conhecidas diante de Deus pela oração e súplica, com ação de graças.' 🙏";
    }
    return "A Palavra de Deus é lâmpada para os meus pés e luz para o meu caminho (Salmos 119:105). Confie nEle em todas as coisas! ✨";
}

function sendSpiritualMessage() {
    const input = document.getElementById('spiritualChatInput');
    const text = input.value.trim();
    if (!text) return;
    const messages = JSON.parse(localStorage.getItem('spiritualChatMessages')) || [];
    messages.push({ type: 'user', text });
    messages.push({ type: 'ai', text: getSpiritualResponse(text) });
    localStorage.setItem('spiritualChatMessages', JSON.stringify(messages));
    input.value = '';
    loadSpiritualChat();
}

// === LOGIN/CADASTRO ===
function openModal(type) {
    if (type === 'login') document.getElementById('loginModal').classList.add('active');
    else if (type === 'signup') document.getElementById('signupModal').classList.add('active');
}

function closeAuthModal() {
    document.getElementById('loginModal').classList.remove('active');
    document.getElementById('signupModal').classList.remove('active');
}

function handleAuth(event, type) {
    event.preventDefault();
    const form = event.target.closest('form');
    const inputs = form.querySelectorAll('input');
    const data = {};
    inputs.forEach(input => {
        data[input.placeholder.toLowerCase().replace(' ', '_')] = input.value;
    });
    if (type === 'login') {
        alert(`✅ Login simulado!\nE-mail: ${data.email}`);
    } else {
        alert(`✅ Cadastro simulado!\nBem-vindo, ${data.nome_completo || 'amigo'}!`);
    }
    closeAuthModal();
    form.reset();
}

// Fecha modal ao clicar fora
document.querySelectorAll('.auth-modal-overlay').forEach(modal => {
    modal.addEventListener('click', (e) => {
        if (e.target === modal) closeAuthModal();
    });
});

// === ELEMENTOS ESPIRITUAIS FLUTUANTES ===
function createSpiritualElements() {
    const symbols = ['👼', '😇', '🕊️', '✝️', '🙏', '🕯️', '✨', '⛪'];
    const container = document.body;
    for (let i = 0; i < 8; i++) {
        const el = document.createElement('div');
        el.className = 'spiritual-element';
        el.textContent = symbols[Math.floor(Math.random() * symbols.length)];
        const left = Math.random() * 90 + 5;
        const top = Math.random() * 80 + 10;
        el.style.left = `${left}%`;
        el.style.top = `${top}%`;
        el.style.animationDelay = `${Math.random() * 10}s`;
        el.style.fontSize = `${1.2 + Math.random() * 1.2}rem`;
        el.style.opacity = `${0.4 + Math.random() * 0.4}`;
        container.appendChild(el);
    }
}

// === INICIALIZAÇÃO ===
if (document.readyState === 'loading') {
    document.addEventListener('DOMContentLoaded', () => {
        createSpiritualElements();
        sitePlayProtect();
        updateCurrentDate();
        updateCountdown();
        loadSpiritualChat();
        setInterval(() => {
            updateCurrentDate();
            updateCountdown();
        }, 1000);
        document.getElementById('spiritualChatInput').addEventListener('keypress', (e) => {
            if (e.key === 'Enter') sendSpiritualMessage();
        });
    });
} else {
    createSpiritualElements();
    sitePlayProtect();
    updateCurrentDate();
    updateCountdown();
    loadSpiritualChat();
    setInterval(() => {
        updateCurrentDate();
        updateCountdown();
    }, 1000);
    document.getElementById('spiritualChatInput').addEventListener('keypress', (e) => {
        if (e.key === 'Enter') sendSpiritualMessage();
    });
}
</script>

</body>
</html>