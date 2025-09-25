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
        
        /* MENU DE AUTENTICAÇÃO NO TOPO DIREITO */
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

        @media (max-width: 500px) {
            .auth-top-bar { display: none; }
            .number-weeks, .number { font-size: 1.8rem; }
            h1 { font-size: 2rem; }
            .btn { padding: 0.7rem 1.4rem; font-size: 1rem; }
        }
    </style>
</head>
<body>

<!-- MENU DE AUTENTICAÇÃO (TOPO DIREITO) -->
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

    <!-- BOTÃO CORRIGIDO: LINK DO YOUTUBE SEM PARÂMETROS TEMPORÁRIOS -->
    <a href="https://www.youtube.com/@bibliasagrada" target="_blank" class="btn connect-button">
        <i class="fab fa-youtube"></i> Conecte-se à Palavra: Visite nosso Canal
    </a>

    <a href="#" class="btn coming-soon-btn" onclick="window.scrollTo({top:0,behavior:'smooth'}); return false;">
        <i class="fas fa-calendar-star"></i> Ano em Breve: 2026 ✨
    </a>
    <a hr
