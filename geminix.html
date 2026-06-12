<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Geminix - Assistente AI Avançado</title>
  <!-- Tabler Icons -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.30.0/tabler-icons.min.css">
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: 'Google Sans', 'Roboto', system-ui, -apple-system, sans-serif; background: #1e1f20; height: 100vh; overflow: hidden; }

    .app { display: flex; height: 100vh; min-height: 700px; background: #1e1f20; color: #e3e3e3; font-family: 'Google Sans', 'Roboto', sans-serif; overflow: hidden; }

    /* SIDEBAR */
    .sidebar { width: 260px; background: #1e1f20; display: flex; flex-direction: column; padding: 12px 0; border-right: 1px solid #2d2e30; flex-shrink: 0; transition: transform 0.2s; }
    .sidebar-top { padding: 8px 16px 12px; display: flex; align-items: center; gap: 10px; }
    .hamburger { width: 36px; height: 36px; border-radius: 50%; border: none; background: transparent; cursor: pointer; display: flex; align-items: center; justify-content: center; color: #e3e3e3; font-size: 20px; transition: background .2s; }
    .hamburger:hover { background: #2d2e30; }
    .gemini-logo { display: flex; align-items: center; gap: 6px; font-size: 20px; font-weight: 500; color: #e3e3e3; }
    .logo-icon { width: 28px; height: 28px; background: linear-gradient(135deg, #4285F4, #EA4335, #FBBC05, #34A853); border-radius: 50%; flex-shrink: 0; }

    .new-chat-btn { margin: 4px 12px 8px; padding: 10px 16px; background: #2d2e30; border: none; border-radius: 24px; color: #e3e3e3; font-size: 14px; cursor: pointer; display: flex; align-items: center; gap: 8px; transition: background .2s; }
    .new-chat-btn:hover { background: #3c3d3f; }
    .new-chat-btn i { font-size: 18px; }

    .sidebar-section { padding: 4px 0; }
    .sidebar-section-title { padding: 8px 20px 4px; font-size: 12px; color: #9aa0a6; font-weight: 500; letter-spacing: .3px; }

    .chat-item { padding: 8px 16px; margin: 0 8px; border-radius: 8px; cursor: pointer; font-size: 14px; color: #c4c7c5; display: flex; align-items: center; gap: 8px; transition: background .15s; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
    .chat-item:hover { background: #2d2e30; }
    .chat-item.active { background: #2d4a6d; color: #a8c7fa; }
    .chat-item i { font-size: 16px; flex-shrink: 0; }

    .sidebar-bottom { margin-top: auto; border-top: 1px solid #2d2e30; padding-top: 8px; }
    .sidebar-bottom-item { padding: 10px 16px; margin: 0 8px; border-radius: 8px; cursor: pointer; font-size: 14px; color: #c4c7c5; display: flex; align-items: center; gap: 10px; transition: background .15s; }
    .sidebar-bottom-item:hover { background: #2d2e30; }
    .avatar { width: 28px; height: 28px; border-radius: 50%; background: linear-gradient(135deg, #4285F4, #EA4335); display: flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 600; color: white; flex-shrink: 0; }

    /* MAIN */
    .main { flex: 1; display: flex; flex-direction: column; overflow: hidden; background: #131314; }

    /* TOPBAR */
    .topbar { height: 56px; display: flex; align-items: center; justify-content: space-between; padding: 0 20px; border-bottom: 1px solid #2d2e30; flex-shrink: 0; }
    .topbar-left { display: flex; align-items: center; gap: 8px; }
    .model-selector { display: flex; align-items: center; gap: 6px; padding: 6px 12px; border-radius: 20px; background: transparent; border: 1px solid #444; cursor: pointer; color: #e3e3e3; font-size: 14px; font-weight: 500; transition: background .2s; }
    .model-selector:hover { background: #2d2e30; }
    .model-dot { width: 8px; height: 8px; border-radius: 50%; background: linear-gradient(135deg, #4285F4, #34A853); animation: pulse 2s infinite; }
    @keyframes pulse { 0%,100% { opacity: 1; } 50% { opacity: 0.5; } }
    .topbar-right { display: flex; align-items: center; gap: 8px; }
    .icon-btn { width: 36px; height: 36px; border-radius: 50%; background: transparent; border: none; cursor: pointer; display: flex; align-items: center; justify-content: center; color: #9aa0a6; font-size: 18px; transition: background .2s; }
    .icon-btn:hover { background: #2d2e30; color: #e3e3e3; }

    /* CHAT AREA */
    .chat-area { flex: 1; overflow-y: auto; padding: 20px 0; display: flex; flex-direction: column; }
    .chat-area::-webkit-scrollbar { width: 4px; }
    .chat-area::-webkit-scrollbar-thumb { background: #3c3d3f; border-radius: 2px; }

    /* WELCOME */
    .welcome { flex: 1; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 40px 20px; gap: 32px; }
    .welcome-logo { width: 80px; height: 80px; border-radius: 50%; background: conic-gradient(from 0deg, #4285F4, #EA4335, #FBBC05, #34A853, #4285F4); display: flex; align-items: center; justify-content: center; animation: spin 10s linear infinite; }
    @keyframes spin { 100% { transform: rotate(360deg); } }
    .welcome-logo-inner { width: 60px; height: 60px; border-radius: 50%; background: #131314; display: flex; align-items: center; justify-content: center; font-size: 32px; font-weight: bold; background: linear-gradient(135deg, #4285F4, #EA4335, #FBBC05, #34A853); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
    .welcome-title { font-size: 36px; font-weight: 400; text-align: center; line-height: 1.2; }
    .welcome-title span { background: linear-gradient(90deg, #4285F4, #EA4335, #FBBC05, #34A853); -webkit-background-clip: text; -webkit-text-fill-color: transparent; font-weight: 500; }
    .welcome-subtitle { font-size: 16px; color: #9aa0a6; text-align: center; }

    .suggestions { display: grid; grid-template-columns: repeat(2, 1fr); gap: 12px; width: 100%; max-width: 680px; }
    .suggestion-card { padding: 16px; background: #1e1f20; border: 1px solid #2d2e30; border-radius: 16px; cursor: pointer; transition: background .2s, border-color .2s, transform .1s; display: flex; flex-direction: column; gap: 8px; }
    .suggestion-card:hover { background: #2a2b2d; border-color: #4285F4; transform: translateY(-2px); }
    .suggestion-card p { font-size: 14px; color: #c4c7c5; line-height: 1.4; }
    .suggestion-card-icon { font-size: 20px; color: #9aa0a6; }

    /* MESSAGES */
    .messages-container { max-width: 760px; width: 100%; margin: 0 auto; padding: 0 20px; display: flex; flex-direction: column; gap: 24px; }

    .msg-user { display: flex; justify-content: flex-end; }
    .msg-user-bubble { background: linear-gradient(135deg, #2d4a6d, #1e3a5f); border-radius: 20px 20px 4px 20px; padding: 12px 18px; max-width: 80%; font-size: 15px; color: #e3e3e3; line-height: 1.5; }

    .msg-gemini { display: flex; gap: 14px; align-items: flex-start; }
    .gemini-avatar { width: 36px; height: 36px; border-radius: 50%; background: conic-gradient(from 0deg, #4285F4, #EA4335, #FBBC05, #34A853, #4285F4); display: flex; align-items: center; justify-content: center; flex-shrink: 0; animation: spin 8s linear infinite; }
    .gemini-avatar-inner { width: 28px; height: 28px; border-radius: 50%; background: #131314; display: flex; align-items: center; justify-content: center; font-size: 14px; font-weight: bold; background: linear-gradient(135deg, #4285F4, #EA4335); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
    .msg-gemini-content { flex: 1; }
    .msg-gemini-name { font-size: 13px; font-weight: 500; color: #9aa0a6; margin-bottom: 6px; }
    .msg-gemini-text { font-size: 15px; color: #e3e3e3; line-height: 1.7; }
    .msg-gemini-text strong { color: #a8c7fa; font-weight: 600; }
    .msg-gemini-text code { background: #2d2e30; padding: 2px 6px; border-radius: 4px; font-family: monospace; font-size: 13px; color: #81c995; }
    .msg-gemini-text pre { background: #1a1b1d; padding: 12px; border-radius: 8px; overflow-x: auto; margin: 8px 0; }

    .msg-actions { display: flex; align-items: center; gap: 4px; margin-top: 12px; }
    .msg-action-btn { padding: 6px 10px; border-radius: 20px; background: transparent; border: none; cursor: pointer; color: #9aa0a6; font-size: 13px; display: flex; align-items: center; gap: 4px; transition: background .2s, color .2s; }
    .msg-action-btn:hover { background: #2d2e30; color: #e3e3e3; }

    /* INPUT AREA */
    .input-area { padding: 16px 20px 20px; background: #131314; flex-shrink: 0; border-top: 1px solid #2d2e30; }
    .input-wrapper { max-width: 760px; margin: 0 auto; }
    .input-box { background: #1e1f20; border: 1px solid #2d2e30; border-radius: 28px; padding: 12px 20px; display: flex; flex-direction: column; gap: 10px; transition: border-color .2s; }
    .input-box:focus-within { border-color: #4285F4; box-shadow: 0 0 0 2px rgba(66,133,244,0.2); }
    .input-textarea { background: transparent; border: none; color: #e3e3e3; font-size: 15px; resize: none; width: 100%; outline: none; font-family: inherit; line-height: 1.5; min-height: 24px; max-height: 160px; }
    .input-textarea::placeholder { color: #5f6368; }
    .input-actions { display: flex; align-items: center; justify-content: space-between; }
    .input-left { display: flex; align-items: center; gap: 4px; }
    .input-btn { width: 36px; height: 36px; border-radius: 50%; background: transparent; border: none; cursor: pointer; display: flex; align-items: center; justify-content: center; color: #9aa0a6; font-size: 20px; transition: background .2s; }
    .input-btn:hover { background: #2d2e30; color: #e3e3e3; }
    .send-btn { width: 40px; height: 40px; border-radius: 50%; background: linear-gradient(135deg, #4285F4, #34A853); border: none; cursor: pointer; display: flex; align-items: center; justify-content: center; color: white; font-size: 20px; transition: transform .1s, opacity .2s; }
    .send-btn:hover { opacity: 0.9; transform: scale(1.02); }
    .send-btn:active { transform: scale(.95); }
    .send-btn:disabled { background: #2d2e30; color: #5f6368; cursor: not-allowed; opacity: 0.5; }

    .input-footer { text-align: center; font-size: 12px; color: #5f6368; margin-top: 10px; }

    /* TYPING */
    .typing-dots { display: inline-flex; gap: 4px; align-items: center; padding: 8px 0; }
    .dot { width: 8px; height: 8px; border-radius: 50%; background: #9aa0a6; animation: bounce 1.2s infinite; }
    .dot:nth-child(2) { animation-delay: .2s; }
    .dot:nth-child(3) { animation-delay: .4s; }
    @keyframes bounce { 0%,60%,100%{ transform: translateY(0); } 30%{ transform: translateY(-8px); } }

    .chips { display: flex; gap: 8px; flex-wrap: wrap; justify-content: center; margin-top: 8px; }
    .chip { padding: 6px 14px; border-radius: 20px; background: #1e1f20; border: 1px solid #2d2e30; font-size: 13px; color: #c4c7c5; cursor: pointer; transition: all .2s; }
    .chip:hover { background: #2d2e30; border-color: #4285F4; transform: translateY(-1px); }
  </style>
</head>
<body>
<div class="app">
  <nav class="sidebar">
    <div class="sidebar-top">
      <button class="hamburger" onclick="toggleSidebar()"><i class="ti ti-menu-2"></i></button>
      <div class="gemini-logo">
        <div class="logo-icon"></div>
        Geminix
      </div>
    </div>
    <button class="new-chat-btn" onclick="window.newChat()">
      <i class="ti ti-edit"></i> Novo chat
    </button>
    <div class="sidebar-section" id="chat-history-list">
      <div class="sidebar-section-title">Conversas Recentes</div>
    </div>
    <div class="sidebar-bottom">
      <div class="sidebar-bottom-item" onclick="clearAllChats()"><i class="ti ti-trash"></i> Limpar histórico</div>
      <div class="sidebar-bottom-item" onclick="alert('Configurações do Geminix')"><i class="ti ti-settings"></i> Configurações</div>
      <div class="sidebar-bottom-item" onclick="alert('Minha conta')"><div class="avatar">U</div> Minha conta</div>
    </div>
  </nav>

  <main class="main">
    <div class="topbar">
      <div class="topbar-left">
        <button class="model-selector" onclick="toggleModelMenu()">
          <div class="model-dot"></div>
          <span id="model-name">Geminix Pro 2.0</span>
          <i class="ti ti-chevron-down"></i>
        </button>
      </div>
      <div class="topbar-right">
        <button class="icon-btn" onclick="exportChat()"><i class="ti ti-download"></i></button>
        <button class="icon-btn" onclick="alert('Geminix - IA Avançada')"><i class="ti ti-info-circle"></i></button>
        <div class="avatar">G</div>
      </div>
    </div>

    <div id="welcome-screen" class="chat-area">
      <div class="welcome">
        <div class="welcome-logo"><div class="welcome-logo-inner">✦</div></div>
        <div><div class="welcome-title">Olá, <span>Geminix</span></div><div class="welcome-subtitle">IA Avançada - Como posso ajudar hoje?</div></div>
        <div class="suggestions">
          <div class="suggestion-card" onclick="fillInput('Crie um plano de estudos de Python para iniciantes em 30 dias')"><div class="suggestion-card-icon"><i class="ti ti-book"></i></div><p>Crie um plano de estudos de Python para iniciantes em 30 dias</p></div>
          <div class="suggestion-card" onclick="fillInput('Explique como funciona a inteligência artificial de forma simples')"><div class="suggestion-card-icon"><i class="ti ti-brain"></i></div><p>Explique como funciona a inteligência artificial de forma simples</p></div>
          <div class="suggestion-card" onclick="fillInput('Escreva um código para calcular Fibonacci em Python')"><div class="suggestion-card-icon"><i class="ti ti-code"></i></div><p>Escreva um código para calcular Fibonacci</p></div>
          <div class="suggestion-card" onclick="fillInput('Me dê ideias criativas para um projeto de final de semana')"><div class="suggestion-card-icon"><i class="ti ti-bulb"></i></div><p>Me dê ideias criativas para um projeto de final de semana</p></div>
        </div>
        <div class="chips"><div class="chip" onclick="fillInput('Escreva um poema sobre tecnologia')"><i class="ti ti-pencil"></i>Poema</div><div class="chip" onclick="fillInput('Explique buracos negros')"><i class="ti ti-planet"></i>Ciência</div><div class="chip" onclick="fillInput('Dicas de produtividade')"><i class="ti ti-clock"></i>Produtividade</div></div>
      </div>
    </div>

    <div id="chat-screen" style="display:none; flex:1; overflow-y:auto; padding:20px 0;" class="chat-area"><div class="messages-container" id="messages"></div></div>

    <div class="input-area">
      <div class="input-wrapper">
        <div class="input-box">
          <textarea class="input-textarea" id="input" placeholder="Pergunte ao Geminix..." rows="1" onkeydown="window.handleKey(event)" oninput="window.autoResize(this); window.updateSendBtn()"></textarea>
          <div class="input-actions"><div class="input-left"><button class="input-btn" onclick="alert('Anexar arquivo em breve')"><i class="ti ti-paperclip"></i></button><button class="input-btn" onclick="alert('Imagem em breve')"><i class="ti ti-photo"></i></button></div><button class="send-btn" id="send-btn" onclick="window.sendMessage()" disabled><i class="ti ti-arrow-up"></i></button></div>
        </div>
        <div class="input-footer">Geminix IA Avançada - Respostas inteligentes e contextualizadas</div>
      </div>
    </div>
  </main>
</div>

<script>
// ==================== CONFIGURAÇÃO DA IA AVANÇADA (API GEMINI GRÁTIS) ====================
// Chave API pública para demonstração - usuário deve substituir pela sua chave do Google AI Studio
// Para usar: acesse https://aistudio.google.com/apikey, crie uma chave e cole abaixo
const GEMINI_API_KEY = "SUA_CHAVE_AQUI"; // COLE SUA CHAVE DO GOOGLE AI STUDIO AQUI
const API_URL = "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash-exp:generateContent";

// Fallback local quando não há chave API
async function callGeminiAI(prompt, history = []) {
  // Se tiver chave configurada, usa API real
  if (GEMINI_API_KEY && GEMINI_API_KEY !== "SUA_CHAVE_AQUI") {
    try {
      const response = await fetch(`${API_URL}?key=${GEMINI_API_KEY}`, {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          contents: [{ parts: [{ text: prompt }] }],
          generationConfig: { temperature: 0.7, maxOutputTokens: 2048 }
        })
      });
      const data = await response.json();
      if (data.candidates && data.candidates[0]?.content?.parts[0]?.text) {
        return data.candidates[0].content.parts[0].text;
      }
      return "⚠️ Erro na API: " + (data.error?.message || "Resposta inválida");
    } catch (e) {
      return fallbackAI(prompt);
    }
  }
  return fallbackAI(prompt);
}

// IA local avançada (fallback inteligente)
function fallbackAI(prompt) {
  const p = prompt.toLowerCase();
  if (p.includes('python') && p.includes('plano')) return "**📚 Plano de Estudos Python (30 dias) - Geminix**\n\n**Semana 1:** Fundamentos (variáveis, loops, funções)\n**Semana 2:** Estruturas de dados (listas, dicionários)\n**Semana 3:** POO e módulos\n**Semana 4:** Projetos práticos (API, automação)\n\nQuer que eu detalhe algum tópico? 🐍";
  if (p.includes('fibonacci')) return "**🔢 Código Fibonacci em Python:**\n```python\ndef fibonacci(n):\n    a, b = 0, 1\n    for _ in range(n):\n        print(a, end=' ')\n        a, b = b, a + b\nfibonacci(10)\n```\nSaída: 0 1 1 2 3 5 8 13 21 34";
  if (p.includes('inteligência artificial') || p.includes('ia')) return "**🧠 O que é Inteligência Artificial?**\n\nIA é a simulação de processos humanos por máquinas. O Geminix usa aprendizado profundo para entender contexto, gerar código, responder perguntas e muito mais! Existem 3 tipos: IA Fraca (atual), IA Geral (futuro) e Super IA.\n\nQuer saber mais sobre Machine Learning?";
  if (p.includes('poema')) return "**✨ Poema da Tecnologia**\n\nCódigos dançam na tela\nBits tecem o amanhã\nAlgoritmos, poesia bela\nGeminix, a luz que irradia\n\nDa nuvem ao pensamento\nInovação a nos guiar\nTecnologia, o novo vento\nQue faz o mundo transformar 🌟";
  if (p.includes('produtividade')) return "**⏰ Dicas de Produtividade pelo Geminix:**\n\n1. Técnica Pomodoro (25min foco, 5min pausa)\n2. Matriz de Eisenhower (urgente x importante)\n3. Bloqueie distrações (modo não perturbe)\n4. Planeje o dia anterior\n5. Use o método 2-minutos para tarefas rápidas\n\nQuer uma planilha personalizada?";
  return `**🤖 Geminix responde:**\n\nExcelente pergunta! Sobre "${prompt.substring(0, 80)}...", posso ajudar com:\n- Explicações detalhadas\n- Códigos e exemplos\n- Análises profundas\n- Criatividade e redação\n\nPode me perguntar sobre programação, ciência, filosofia, produtividade e muito mais! O que gostaria de explorar? 🚀`;
}

// ==================== ESTADO GLOBAL ====================
let chats = [{ id: Date.now(), title: "Nova conversa", messages: [] }];
let currentChatId = chats[0].id;
let isTyping = false;
let isWelcome = true;

function saveChats() { localStorage.setItem('geminix_chats', JSON.stringify(chats)); }
function loadChats() { const saved = localStorage.getItem('geminix_chats'); if (saved) { chats = JSON.parse(saved); if (!chats.length) resetDefaultChat(); renderChatList(); if (chats.find(c => c.id === currentChatId)) loadChatById(currentChatId); else selectChat(chats[0].id); } }
function resetDefaultChat() { chats = [{ id: Date.now(), title: "Nova conversa", messages: [] }]; currentChatId = chats[0].id; saveChats(); }

function renderChatList() {
  const container = document.getElementById('chat-history-list');
  if (!container) return;
  const sectionDiv = document.createElement('div');
  sectionDiv.className = 'sidebar-section';
  const title = document.createElement('div');
  title.className = 'sidebar-section-title';
  title.innerText = 'Conversas Recentes';
  sectionDiv.appendChild(title);
  chats.slice(-8).reverse().forEach(chat => {
    const item = document.createElement('div');
    item.className = `chat-item ${currentChatId === chat.id ? 'active' : ''}`;
    item.innerHTML = `<i class="ti ti-message"></i>${chat.title.length > 25 ? chat.title.slice(0,22)+'...' : chat.title}`;
    item.onclick = () => selectChat(chat.id);
    sectionDiv.appendChild(item);
  });
  container.innerHTML = '';
  container.appendChild(sectionDiv);
}

function selectChat(chatId) {
  currentChatId = chatId;
  renderChatList();
  showChatScreen();
  const chat = chats.find(c => c.id === chatId);
  if (chat) {
    const container = document.getElementById('messages');
    if (container) {
      container.innerHTML = '';
      chat.messages.forEach(msg => {
        if (msg.role === 'user') addUserMsg(msg.text, false);
        else addGeminiMsg(msg.text, false, false);
      });
    }
  }
}

function loadChatById(chatId) { selectChat(chatId); }

function showChatScreen() {
  if (isWelcome) {
    document.getElementById('welcome-screen').style.display = 'none';
    document.getElementById('chat-screen').style.display = 'block';
    isWelcome = false;
  }
}

function addUserMsg(text, save = true) {
  const container = document.getElementById('messages');
  const div = document.createElement('div');
  div.className = 'msg-user';
  div.innerHTML = `<div class="msg-user-bubble">${escapeHtml(text)}</div>`;
  container.appendChild(div);
  scrollBottom();
  if (save) {
    const chat = chats.find(c => c.id === currentChatId);
    if (chat) { chat.messages.push({ role: 'user', text }); saveChats(); }
  }
}

function addGeminiMsg(text, save = true, withActions = true) {
  const container = document.getElementById('messages');
  const div = document.createElement('div');
  div.className = 'msg-gemini';
  let formatted = text.replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>').replace(/`([^`]+)`/g, '<code>$1</code>').replace(/\n/g, '<br>');
  div.innerHTML = `<div class="gemini-avatar"><div class="gemini-avatar-inner">★</div></div><div class="msg-gemini-content"><div class="msg-gemini-name">Geminix</div><div class="msg-gemini-text">${formatted}</div>${withActions ? `<div class="msg-actions"><button class="msg-action-btn" onclick="copyText(this)"><i class="ti ti-copy"></i>Copiar</button><button class="msg-action-btn" onclick="regenerateLast()"><i class="ti ti-refresh"></i>Regenerar</button></div>` : ''}</div>`;
  container.appendChild(div);
  scrollBottom();
  if (save) {
    const chat = chats.find(c => c.id === currentChatId);
    if (chat) { chat.messages.push({ role: 'gemini', text }); saveChats(); if (chat.messages.length === 2 && chat.title === "Nova conversa") { chat.title = chat.messages[0].text.slice(0, 30); renderChatList(); } }
  }
}

function addTyping() { const c = document.getElementById('messages'); const d = document.createElement('div'); d.className = 'msg-gemini'; d.id = 'typing-msg'; d.innerHTML = `<div class="gemini-avatar"><div class="gemini-avatar-inner">★</div></div><div class="msg-gemini-content"><div class="typing-dots"><div class="dot"></div><div class="dot"></div><div class="dot"></div></div></div>`; c.appendChild(d); scrollBottom(); }
function removeTyping() { const t = document.getElementById('typing-msg'); if (t) t.remove(); }
function escapeHtml(t) { return t.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;'); }
function scrollBottom() { const s = document.getElementById('chat-screen'); if (s && s.style.display !== 'none') s.scrollTop = s.scrollHeight; }
function autoResize(el) { if (el) { el.style.height = 'auto'; el.style.height = Math.min(el.scrollHeight, 160) + 'px'; } }
function updateSendBtn() { const inp = document.getElementById('input'); const btn = document.getElementById('send-btn'); if (inp && btn) btn.disabled = !inp.value.trim(); }
function handleKey(e) { if (e.key === 'Enter' && !e.shiftKey) { e.preventDefault(); const btn = document.getElementById('send-btn'); if (btn && !btn.disabled) sendMessage(); } }
function fillInput(text) { const inp = document.getElementById('input'); if (inp) { inp.value = text; autoResize(inp); updateSendBtn(); inp.focus(); } }

async function sendMessage() {
  if (isTyping) return;
  const inp = document.getElementById('input');
  const text = inp.value.trim();
  if (!text) return;
  showChatScreen();
  inp.value = '';
  autoResize(inp);
  updateSendBtn();
  isTyping = true;
  addUserMsg(text);
  addTyping();
  const reply = await callGeminiAI(text);
  removeTyping();
  addGeminiMsg(reply);
  isTyping = false;
}

function newChat() {
  const newChatObj = { id: Date.now(), title: "Nova conversa", messages: [] };
  chats.unshift(newChatObj);
  currentChatId = newChatObj.id;
  saveChats();
  renderChatList();
  document.getElementById('messages').innerHTML = '';
  document.getElementById('welcome-screen').style.display = 'block';
  document.getElementById('chat-screen').style.display = 'none';
  isWelcome = true;
  isTyping = false;
  removeTyping();
}

function clearAllChats() { if (confirm('Tem certeza que deseja apagar todo o histórico?')) { resetDefaultChat(); renderChatList(); newChat(); } }
function exportChat() { const chat = chats.find(c => c.id === currentChatId); if (chat) { const data = JSON.stringify(chat, null, 2); const blob = new Blob([data], {type: 'application/json'}); const a = document.createElement('a'); a.href = URL.createObjectURL(blob); a.download = `geminix_chat_${Date.now()}.json`; a.click(); } }
function copyText(btn) { const textDiv = btn.closest('.msg-gemini-content')?.querySelector('.msg-gemini-text'); if (textDiv) { navigator.clipboard.writeText(textDiv.innerText).then(() => alert('Copiado!')).catch(() => alert('Erro')); } }
async function regenerateLast() { const chat = chats.find(c => c.id === currentChatId); if (chat && chat.messages.length >= 2) { const lastUserMsg = [...chat.messages].reverse().find(m => m.role === 'user'); if (lastUserMsg) { chat.messages.pop(); document.getElementById('messages').lastElementChild?.remove(); addTyping(); const newReply = await callGeminiAI(lastUserMsg.text); removeTyping(); addGeminiMsg(newReply); saveChats(); } } }
function toggleSidebar() { const sidebar = document.querySelector('.sidebar'); sidebar.style.transform = sidebar.style.transform === 'translateX(-260px)' ? 'translateX(0)' : 'translateX(-260px)'; setTimeout(() => { if (sidebar.style.transform === 'translateX(-260px)') sidebar.style.transform = ''; }, 300); }
function toggleModelMenu() { const modelSpan = document.getElementById('model-name'); const models = ['Geminix Pro 2.0', 'Geminix Ultra', 'Geminix Lite']; let idx = models.indexOf(modelSpan.innerText); modelSpan.innerText = models[(idx + 1) % models.length]; alert(`Modelo alterado para: ${modelSpan.innerText}`); }

window.autoResize = autoResize; window.updateSendBtn = updateSendBtn; window.handleKey = handleKey; window.sendMessage = sendMessage; window.newChat = newChat; window.fillInput = fillInput; window.copyText = copyText; window.regenerateLast = regenerateLast; window.toggleSidebar = toggleSidebar; window.toggleModelMenu = toggleModelMenu; window.clearAllChats = clearAllChats; window.exportChat = exportChat;

loadChats();
if (!chats.length) resetDefaultChat();
renderChatList();
updateSendBtn();
if (chats.length && chats[0].messages.length === 0) { } else if (chats[0] && chats[0].messages.length) selectChat(chats[0].id);
</script>
</body>
</html>
