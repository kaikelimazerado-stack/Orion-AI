<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes, viewport-fit=cover">
  <title>Geminix - IA Avançada com Configurações</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.30.0/tabler-icons.min.css">
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: 'Google Sans', 'Roboto', system-ui, -apple-system, sans-serif; background: #1e1f20; height: 100vh; overflow: hidden; transition: background 0.3s, color 0.3s; }
    
    /* Temas */
    body.light-theme { background: #f5f5f7; color: #1a1a1e; }
    body.light-theme .sidebar, body.light-theme .main, body.light-theme .input-area, body.light-theme .welcome-logo-inner,
    body.light-theme .msg-user-bubble, body.light-theme .input-box, body.light-theme .suggestion-card,
    body.light-theme .chat-item, body.light-theme .chip, body.light-theme .msg-action-btn { background-color: #ffffff; color: #1a1a1e; }
    body.light-theme .sidebar, body.light-theme .topbar { border-color: #e0e0e0; }
    body.light-theme .msg-user-bubble { background: linear-gradient(135deg, #e0e7ff, #c7d2fe); color: #1e1f2e; }
    body.light-theme .msg-gemini-text, body.light-theme .welcome-title, body.light-theme .welcome-subtitle { color: #1f2937; }
    
    /* Tamanhos de fonte */
    body.font-small { font-size: 12px; }
    body.font-medium { font-size: 14px; }
    body.font-large { font-size: 16px; }
    body.font-xlarge { font-size: 18px; }
    
    .app { display: flex; height: 100vh; min-height: 700px; background: inherit; color: inherit; overflow: hidden; position: relative; }

    /* SIDEBAR */
    .sidebar { width: 280px; background: #1e1f20; display: flex; flex-direction: column; padding: 12px 0; border-right: 1px solid #2d2e30; flex-shrink: 0; transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1), background 0.3s; z-index: 100; position: relative; }
    .sidebar-overlay { position: fixed; top: 0; left: 0; right: 0; bottom: 0; background: rgba(0,0,0,0.5); z-index: 90; display: none; backdrop-filter: blur(2px); }
    .mobile-menu-btn, .mobile-newchat-btn { display: none; position: fixed; width: 50px; height: 50px; border-radius: 50%; background: linear-gradient(135deg, #4285F4, #34A853); border: none; cursor: pointer; align-items: center; justify-content: center; color: white; font-size: 22px; z-index: 95; box-shadow: 0 4px 12px rgba(0,0,0,0.3); transition: transform 0.2s; }
    .mobile-menu-btn { bottom: 20px; left: 20px; }
    .mobile-newchat-btn { bottom: 20px; right: 20px; background: linear-gradient(135deg, #EA4335, #FBBC05); }
    .mobile-menu-btn:active, .mobile-newchat-btn:active { transform: scale(0.95); }

    .sidebar-top { padding: 8px 16px 12px; display: flex; align-items: center; gap: 10px; }
    .hamburger { width: 36px; height: 36px; border-radius: 50%; border: none; background: transparent; cursor: pointer; display: flex; align-items: center; justify-content: center; color: inherit; font-size: 20px; transition: background .2s; }
    .hamburger:hover { background: #2d2e30; }
    .gemini-logo { display: flex; align-items: center; gap: 6px; font-size: 20px; font-weight: 500; }
    .logo-icon { width: 28px; height: 28px; background: linear-gradient(135deg, #4285F4, #EA4335, #FBBC05, #34A853); border-radius: 50%; flex-shrink: 0; }
    .new-chat-btn { margin: 4px 12px 8px; padding: 10px 16px; background: #2d2e30; border: none; border-radius: 24px; color: inherit; font-size: 14px; cursor: pointer; display: flex; align-items: center; gap: 8px; transition: background .2s; }
    .chat-item { padding: 10px 16px; margin: 0 8px; border-radius: 8px; cursor: pointer; font-size: 14px; display: flex; align-items: center; gap: 10px; transition: background .15s; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
    .chat-item:hover { background: #2d2e30; }
    .chat-item.active { background: #2d4a6d; color: #a8c7fa; }
    .sidebar-bottom { margin-top: auto; border-top: 1px solid #2d2e30; padding-top: 8px; }
    .sidebar-bottom-item { padding: 12px 16px; margin: 0 8px; border-radius: 8px; cursor: pointer; display: flex; align-items: center; gap: 12px; transition: background .15s; }
    .sidebar-bottom-item:hover { background: #2d2e30; }
    .avatar { width: 28px; height: 28px; border-radius: 50%; background: linear-gradient(135deg, #4285F4, #EA4335); display: flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 600; color: white; flex-shrink: 0; }

    /* MAIN */
    .main { flex: 1; display: flex; flex-direction: column; overflow: hidden; background: #131314; transition: background 0.3s; }
    .topbar { height: 56px; display: flex; align-items: center; justify-content: space-between; padding: 0 16px; border-bottom: 1px solid #2d2e30; flex-shrink: 0; }
    .model-selector { display: flex; align-items: center; gap: 6px; padding: 6px 12px; border-radius: 20px; background: transparent; border: 1px solid #444; cursor: pointer; font-size: 13px; transition: background .2s; }
    .model-dot { width: 8px; height: 8px; border-radius: 50%; background: linear-gradient(135deg, #4285F4, #34A853); animation: pulse 2s infinite; }
    @keyframes pulse { 0%,100% { opacity: 1; } 50% { opacity: 0.5; } }
    .icon-btn { width: 36px; height: 36px; border-radius: 50%; background: transparent; border: none; cursor: pointer; display: flex; align-items: center; justify-content: center; font-size: 18px; transition: background .2s; }
    .icon-btn:hover { background: #2d2e30; }

    /* CONFIGURAÇÕES MODAL */
    .settings-modal { display: none; position: fixed; top: 0; left: 0; right: 0; bottom: 0; background: rgba(0,0,0,0.7); z-index: 200; align-items: center; justify-content: center; backdrop-filter: blur(4px); }
    .settings-content { background: #1e1f20; border-radius: 28px; max-width: 500px; width: 90%; max-height: 85vh; overflow-y: auto; padding: 24px; box-shadow: 0 20px 35px rgba(0,0,0,0.4); }
    .settings-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 24px; padding-bottom: 12px; border-bottom: 1px solid #2d2e30; }
    .settings-header h2 { font-size: 24px; font-weight: 500; }
    .close-settings { background: none; border: none; font-size: 24px; cursor: pointer; color: #9aa0a6; }
    .settings-section { margin-bottom: 28px; }
    .settings-section h3 { font-size: 16px; margin-bottom: 12px; color: #a8c7fa; display: flex; align-items: center; gap: 8px; }
    .setting-option { display: flex; justify-content: space-between; align-items: center; padding: 12px 0; border-bottom: 1px solid #2d2e30; }
    .setting-option label { font-size: 14px; font-weight: 500; }
    .setting-desc { font-size: 12px; color: #9aa0a6; margin-top: 4px; }
    select, .theme-buttons, .font-buttons { background: #2d2e30; border: 1px solid #3c3d3f; border-radius: 12px; padding: 8px 12px; color: #e3e3e3; font-size: 14px; cursor: pointer; }
    .theme-buttons, .font-buttons { display: flex; gap: 8px; }
    .theme-btn, .font-btn { padding: 6px 16px; border-radius: 20px; background: #2d2e30; border: none; cursor: pointer; color: #e3e3e3; transition: all 0.2s; }
    .theme-btn.active, .font-btn.active { background: #4285F4; color: white; }
    .device-option { display: flex; gap: 12px; margin-top: 8px; }
    .device-card { flex: 1; padding: 12px; border-radius: 16px; background: #2d2e30; text-align: center; cursor: pointer; transition: all 0.2s; border: 2px solid transparent; }
    .device-card.active { border-color: #4285F4; background: #2d4a6d; }
    .device-card i { font-size: 28px; margin-bottom: 8px; display: block; }

    /* CHAT E MENSAGENS */
    .chat-area { flex: 1; overflow-y: auto; padding: 16px 0; }
    .messages-container { max-width: 760px; width: 100%; margin: 0 auto; padding: 0 16px; display: flex; flex-direction: column; gap: 20px; }
    .msg-user { display: flex; justify-content: flex-end; }
    .msg-user-bubble { background: linear-gradient(135deg, #2d4a6d, #1e3a5f); border-radius: 20px 20px 4px 20px; padding: 10px 16px; max-width: 85%; line-height: 1.5; word-break: break-word; }
    .msg-gemini { display: flex; gap: 12px; align-items: flex-start; }
    .gemini-avatar { width: 32px; height: 32px; border-radius: 50%; background: conic-gradient(from 0deg, #4285F4, #EA4335, #FBBC05, #34A853, #4285F4); display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
    .gemini-avatar-inner { width: 26px; height: 26px; border-radius: 50%; background: #131314; display: flex; align-items: center; justify-content: center; font-size: 12px; font-weight: bold; background: linear-gradient(135deg, #4285F4, #EA4335); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
    .msg-gemini-content { flex: 1; min-width: 0; }
    .msg-gemini-text { line-height: 1.6; word-break: break-word; }
    .msg-gemini-text code { background: #2d2e30; padding: 2px 6px; border-radius: 4px; font-family: monospace; font-size: 0.9em; }
    .msg-actions { display: flex; align-items: center; gap: 6px; margin-top: 10px; flex-wrap: wrap; }
    .msg-action-btn { padding: 5px 10px; border-radius: 18px; background: transparent; border: none; cursor: pointer; font-size: 12px; display: flex; align-items: center; gap: 4px; transition: background .2s; }
    
    .input-area { padding: 12px 16px 20px; background: #131314; flex-shrink: 0; border-top: 1px solid #2d2e30; }
    .input-wrapper { max-width: 760px; margin: 0 auto; }
    .input-box { background: #1e1f20; border: 1px solid #2d2e30; border-radius: 28px; padding: 10px 16px; display: flex; flex-direction: column; gap: 8px; }
    .input-textarea { background: transparent; border: none; color: inherit; font-size: 15px; resize: none; width: 100%; outline: none; font-family: inherit; line-height: 1.4; min-height: 24px; max-height: 120px; }
    .send-btn { width: 38px; height: 38px; border-radius: 50%; background: linear-gradient(135deg, #4285F4, #34A853); border: none; cursor: pointer; display: flex; align-items: center; justify-content: center; color: white; font-size: 18px; transition: transform .1s; }
    .send-btn:disabled { background: #2d2e30; opacity: 0.5; cursor: not-allowed; }
    .typing-dots { display: inline-flex; gap: 4px; padding: 6px 0; }
    .dot { width: 7px; height: 7px; border-radius: 50%; background: #9aa0a6; animation: bounce 1.2s infinite; }
    @keyframes bounce { 0%,60%,100%{ transform: translateY(0); } 30%{ transform: translateY(-6px); } }

    /* RESPONSIVO */
    @media (max-width: 768px) {
      .sidebar { position: fixed; top: 0; left: 0; height: 100%; transform: translateX(-100%); z-index: 100; box-shadow: 2px 0 10px rgba(0,0,0,0.3); }
      .sidebar.open { transform: translateX(0); }
      .sidebar-overlay.active { display: block; }
      .mobile-menu-btn, .mobile-newchat-btn { display: flex; }
      .hamburger { display: none; }
      .settings-content { width: 95%; padding: 20px; }
    }
    
    .welcome { flex: 1; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 24px 16px; gap: 24px; text-align: center; }
    .suggestions { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 10px; width: 100%; max-width: 700px; }
    .suggestion-card { padding: 14px; background: #1e1f20; border: 1px solid #2d2e30; border-radius: 14px; cursor: pointer; transition: all 0.2s; }
    .suggestion-card:active { transform: scale(0.98); }
    .chips { display: flex; gap: 8px; flex-wrap: wrap; justify-content: center; margin-top: 8px; }
    .chip { padding: 5px 12px; border-radius: 18px; background: #1e1f20; border: 1px solid #2d2e30; font-size: 12px; cursor: pointer; }
  </style>
</head>
<body>
<div class="app">
  <div class="sidebar-overlay" id="sidebar-overlay" onclick="closeSidebar()"></div>
  <div class="mobile-menu-btn" onclick="toggleSidebar()"><i class="ti ti-menu-2"></i></div>
  <div class="mobile-newchat-btn" onclick="window.newChat?.()"><i class="ti ti-edit"></i></div>
  
  <nav class="sidebar" id="sidebar">
    <div class="sidebar-top"><button class="hamburger" onclick="toggleSidebar()"><i class="ti ti-menu-2"></i></button><div class="gemini-logo"><div class="logo-icon"></div>Geminix</div></div>
    <button class="new-chat-btn" onclick="window.newChat?.(); if(window.innerWidth<=768) closeSidebar();"><i class="ti ti-edit"></i> Novo chat</button>
    <div class="sidebar-section" id="chat-history-list"><div class="sidebar-section-title">Conversas Recentes</div></div>
    <div class="sidebar-bottom">
      <div class="sidebar-bottom-item" onclick="openSettings()"><i class="ti ti-settings"></i> Configurações</div>
      <div class="sidebar-bottom-item" onclick="clearAllChats()"><i class="ti ti-trash"></i> Limpar histórico</div>
      <div class="sidebar-bottom-item" onclick="alert('Minha conta')"><div class="avatar">U</div> Minha conta</div>
    </div>
  </nav>

  <main class="main">
    <div class="topbar"><div class="topbar-left"><button class="model-selector" onclick="toggleModelMenu()"><div class="model-dot"></div><span id="model-name">Geminix Pro</span><i class="ti ti-chevron-down"></i></button></div><div class="topbar-right"><button class="icon-btn" onclick="openSettings()"><i class="ti ti-settings"></i></button><button class="icon-btn" onclick="exportChat()"><i class="ti ti-download"></i></button><div class="avatar">G</div></div></div>

    <div id="welcome-screen" class="chat-area"><div class="welcome"><div class="welcome-logo"><div class="welcome-logo-inner" style="font-size:32px;">✦</div></div><div><div class="welcome-title">Olá, <span>Geminix</span></div><div class="welcome-subtitle">IA Avançada - Como posso ajudar?</div></div><div class="suggestions"><div class="suggestion-card" onclick="fillInput('Crie um plano de estudos de Python')">📘 Plano de estudos Python</div><div class="suggestion-card" onclick="fillInput('Explique IA de forma simples')">🧠 Como funciona a IA?</div><div class="suggestion-card" onclick="fillInput('Código Fibonacci em Python')">💻 Código Fibonacci</div><div class="suggestion-card" onclick="fillInput('Ideias criativas para projeto')">💡 Ideias criativas</div></div><div class="chips"><div class="chip" onclick="fillInput('Poema sobre tecnologia')">📝 Poema</div><div class="chip" onclick="fillInput('Dicas de produtividade')">⏰ Produtividade</div><div class="chip" onclick="fillInput('Receita saudável')">🥗 Receita</div></div></div></div>
    <div id="chat-screen" style="display:none; flex:1; overflow-y:auto; padding:16px 0;" class="chat-area"><div class="messages-container" id="messages"></div></div>
    <div class="input-area"><div class="input-wrapper"><div class="input-box"><textarea class="input-textarea" id="input" placeholder="Pergunte ao Geminix..." rows="1" onkeydown="window.handleKey(event)" oninput="window.autoResize(this); window.updateSendBtn()"></textarea><div class="input-actions"><div class="input-left"><button class="input-btn" onclick="alert('Em breve')"><i class="ti ti-paperclip"></i></button></div><button class="send-btn" id="send-btn" onclick="window.sendMessage()" disabled><i class="ti ti-arrow-up"></i></button></div></div><div class="input-footer">Geminix IA - Configurações personalizáveis</div></div></div>
  </main>
</div>

<!-- MODAL CONFIGURAÇÕES COMPLETO -->
<div id="settings-modal" class="settings-modal"><div class="settings-content"><div class="settings-header"><h2><i class="ti ti-settings"></i> Configurações</h2><button class="close-settings" onclick="closeSettings()">✕</button></div>
  <div class="settings-section"><h3><i class="ti ti-device-desktop"></i> Modo de Exibição</h3><div class="device-option"><div class="device-card" data-device="pc" onclick="setDeviceMode('pc')"><i class="ti ti-device-desktop"></i><span>PC / Desktop</span><small style="display:block;font-size:10px;">Layout completo</small></div><div class="device-card" data-device="mobile" onclick="setDeviceMode('mobile')"><i class="ti ti-device-mobile"></i><span>Celular / Mobile</span><small style="display:block;font-size:10px;">Botões flutuantes</small></div></div></div>
  <div class="settings-section"><h3><i class="ti ti-palette"></i> Tema</h3><div class="theme-buttons"><button class="theme-btn" data-theme="dark" onclick="setTheme('dark')">🌙 Escuro</button><button class="theme-btn" data-theme="light" onclick="setTheme('light')">☀️ Claro</button></div></div>
  <div class="settings-section"><h3><i class="ti ti-text-size"></i> Tamanho da Fonte</h3><div class="font-buttons"><button class="font-btn" data-font="small" onclick="setFontSize('small')">P</button><button class="font-btn" data-font="medium" onclick="setFontSize('medium')">M</button><button class="font-btn" data-font="large" onclick="setFontSize('large')">G</button><button class="font-btn" data-font="xlarge" onclick="setFontSize('xlarge')">GG</button></div></div>
  <div class="settings-section"><h3><i class="ti ti-message-2"></i> Preferências de IA</h3><div class="setting-option"><div><label>Modo de Resposta</label><div class="setting-desc">Criativo / Balanceado / Preciso</div></div><select id="response-mode"><option value="creative">✨ Criativo</option><option value="balanced" selected>⚖️ Balanceado</option><option value="precise">🎯 Preciso</option></select></div></div>
  <div class="settings-section"><h3><i class="ti ti-history"></i> Privacidade</h3><div class="setting-option"><div><label>Salvar histórico automaticamente</label><div class="setting-desc">Manter conversas no armazenamento local</div></div><input type="checkbox" id="save-history" checked style="width:20px;height:20px;cursor:pointer;"></div></div>
  <div class="settings-section"><h3><i class="ti ti-info-circle"></i> Sobre o Geminix</h3><div class="setting-option"><div><label>Versão 2.0.0</label><div class="setting-desc">IA avançada com suporte a PC e Mobile</div></div></div></div>
  <button onclick="closeSettings()" style="width:100%;padding:12px;background:#4285F4;border:none;border-radius:24px;color:white;font-size:16px;margin-top:16px;cursor:pointer;">Fechar</button>
</div></div>

<script>
// ==================== IA AVANÇADA ====================
const GEMINI_API_KEY = "SUA_CHAVE_AQUI";
async function callGeminiAI(prompt) {
  if (GEMINI_API_KEY && GEMINI_API_KEY !== "SUA_CHAVE_AQUI") {
    try {
      const res = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash-exp:generateContent?key=${GEMINI_API_KEY}`, {
        method: 'POST', headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ contents: [{ parts: [{ text: prompt }] }], generationConfig: { temperature: 0.7, maxOutputTokens: 2048 } })
      });
      const data = await res.json();
      if (data.candidates?.[0]?.content?.parts[0]?.text) return data.candidates[0].content.parts[0].text;
      return fallbackAI(prompt);
    } catch(e) { return fallbackAI(prompt); }
  }
  return fallbackAI(prompt);
}
function fallbackAI(prompt) {
  const p = prompt.toLowerCase();
  if (p.includes('python') && p.includes('plano')) return "**📚 Plano de Estudos Python (30 dias)**\n\n**Semana 1:** Fundamentos (variáveis, loops, funções)\n**Semana 2:** Estruturas de dados\n**Semana 3:** POO e módulos\n**Semana 4:** Projetos práticos\n\nQuer detalhar algum tópico?";
  if (p.includes('fibonacci')) return "**🔢 Código Fibonacci:**\n```python\ndef fib(n):\n    a,b=0,1\n    for _ in range(n): print(a,end=' '); a,b=b,a+b\nfib(10)\n```\nSaída: 0 1 1 2 3 5 8 13 21 34";
  if (p.includes('ia') || p.includes('inteligência')) return "**🧠 IA é a simulação de inteligência humana por máquinas. O Geminix usa redes neurais para entender contexto e gerar respostas inteligentes!**";
  if (p.includes('poema')) return "**✨ Poema da Tecnologia**\n\nCódigos dançam na tela\nBits tecem o amanhã\nGeminix, luz que irradia\nTransformação a nos guiar 🌟";
  return `**🤖 Geminix responde:**\n\nSobre "${prompt.substring(0, 60)}...", posso ajudar com programação, ciência, produtividade e muito mais! O que gostaria de explorar? 🚀`;
}

// ==================== ESTADO E CONFIGURAÇÕES ====================
let chats = [{ id: Date.now(), title: "Nova conversa", messages: [] }];
let currentChatId = chats[0].id, isTyping = false, isWelcome = true;

function saveChats() { if(document.getElementById('save-history')?.checked !== false) localStorage.setItem('geminix_chats', JSON.stringify(chats)); }
function loadChats() { const saved = localStorage.getItem('geminix_chats'); if(saved) { chats = JSON.parse(saved); if(!chats.length) resetDefault(); renderChatList(); if(chats.find(c=>c.id===currentChatId)) loadChatById(currentChatId); else selectChat(chats[0].id); } }
function resetDefault() { chats = [{ id: Date.now(), title: "Nova conversa", messages: [] }]; currentChatId = chats[0].id; saveChats(); }
function renderChatList() { const container = document.getElementById('chat-history-list'); if(!container) return; container.innerHTML = '<div class="sidebar-section-title">Conversas Recentes</div>'; [...chats].reverse().slice(0,12).forEach(chat => { const item = document.createElement('div'); item.className = `chat-item ${currentChatId === chat.id ? 'active' : ''}`; item.innerHTML = `<i class="ti ti-message"></i>${chat.title.length>22?chat.title.slice(0,19)+'...':chat.title}`; item.onclick = () => { selectChat(chat.id); if(window.innerWidth<=768) closeSidebar(); }; container.appendChild(item); }); }
function selectChat(chatId) { currentChatId = chatId; renderChatList(); showChatScreen(); const chat = chats.find(c=>c.id===chatId); if(chat) { const container = document.getElementById('messages'); if(container) { container.innerHTML = ''; chat.messages.forEach(msg => { if(msg.role==='user') addUserMsg(msg.text,false); else addGeminiMsg(msg.text,false,false); }); } } }
function showChatScreen() { if(isWelcome) { document.getElementById('welcome-screen').style.display = 'none'; document.getElementById('chat-screen').style.display = 'block'; isWelcome = false; } }
function addUserMsg(text, save=true) { const container = document.getElementById('messages'); const div = document.createElement('div'); div.className = 'msg-user'; div.innerHTML = `<div class="msg-user-bubble">${escapeHtml(text)}</div>`; container.appendChild(div); scrollBottom(); if(save) { const chat = chats.find(c=>c.id===currentChatId); if(chat){ chat.messages.push({ role:'user', text }); saveChats(); } } }
function addGeminiMsg(text, save=true, withActions=true) { const container = document.getElementById('messages'); const div = document.createElement('div'); div.className = 'msg-gemini'; let formatted = text.replace(/\*\*(.*?)\*\*/g,'<strong>$1</strong>').replace(/`([^`]+)`/g,'<code>$1</code>').replace(/\n/g,'<br>'); div.innerHTML = `<div class="gemini-avatar"><div class="gemini-avatar-inner">★</div></div><div class="msg-gemini-content"><div class="msg-gemini-name">Geminix</div><div class="msg-gemini-text">${formatted}</div>${withActions?`<div class="msg-actions"><button class="msg-action-btn" onclick="copyText(this)"><i class="ti ti-copy"></i>Copiar</button><button class="msg-action-btn" onclick="regenerateLast()"><i class="ti ti-refresh"></i>Regenerar</button></div>`:''}</div>`; container.appendChild(div); scrollBottom(); if(save) { const chat = chats.find(c=>c.id===currentChatId); if(chat){ chat.messages.push({ role:'gemini', text }); saveChats(); if(chat.messages.length===2 && chat.title==="Nova conversa") { chat.title = chat.messages[0].text.slice(0,28); renderChatList(); } } } }
function addTyping() { const c = document.getElementById('messages'); const d = document.createElement('div'); d.className = 'msg-gemini'; d.id = 'typing-msg'; d.innerHTML = `<div class="gemini-avatar"><div class="gemini-avatar-inner">★</div></div><div class="msg-gemini-content"><div class="typing-dots"><div class="dot"></div><div class="dot"></div><div class="dot"></div></div></div>`; c.appendChild(d); scrollBottom(); }
function removeTyping() { const t = document.getElementById('typing-msg'); if(t) t.remove(); }
function escapeHtml(t) { return t.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;'); }
function scrollBottom() { const s = document.getElementById('chat-screen'); if(s && s.style.display !== 'none') s.scrollTop = s.scrollHeight; }
function autoResize(el) { if(el) { el.style.height='auto'; el.style.height=Math.min(el.scrollHeight,120)+'px'; } }
function updateSendBtn() { const inp = document.getElementById('input'); const btn = document.getElementById('send-btn'); if(inp && btn) btn.disabled = !inp.value.trim(); }
function handleKey(e) { if(e.key==='Enter' && !e.shiftKey) { e.preventDefault(); const btn = document.getElementById('send-btn'); if(btn && !btn.disabled) sendMessage(); } }
function fillInput(text) { const inp = document.getElementById('input'); if(inp) { inp.value = text; autoResize(inp); updateSendBtn(); inp.focus(); } }
async function sendMessage() { if(isTyping) return; const inp = document.getElementById('input'); const text = inp.value.trim(); if(!text) return; showChatScreen(); inp.value = ''; autoResize(inp); updateSendBtn(); isTyping = true; addUserMsg(text); addTyping(); const mode = document.getElementById('response-mode')?.value || 'balanced'; let prompt = text; if(mode==='creative') prompt = "Seja criativo e inspirador: "+text; if(mode==='precise') prompt = "Seja direto e objetivo, com respostas curtas: "+text; const reply = await callGeminiAI(prompt); removeTyping(); addGeminiMsg(reply); isTyping = false; }
function newChat() { const newChatObj = { id: Date.now(), title: "Nova conversa", messages: [] }; chats.unshift(newChatObj); currentChatId = newChatObj.id; saveChats(); renderChatList(); document.getElementById('messages').innerHTML = ''; document.getElementById('welcome-screen').style.display = 'block'; document.getElementById('chat-screen').style.display = 'none'; isWelcome = true; isTyping = false; removeTyping(); if(window.innerWidth<=768) closeSidebar(); }
function clearAllChats() { if(confirm('Apagar todo o histórico?')) { resetDefault(); renderChatList(); newChat(); } }
function exportChat() { const chat = chats.find(c=>c.id===currentChatId); if(chat) { const a=document.createElement('a'); a.href=URL.createObjectURL(new Blob([JSON.stringify(chat,null,2)],{type:'application/json'})); a.download=`geminix_chat_${Date.now()}.json`; a.click(); } }
function copyText(btn) { const txt = btn.closest('.msg-gemini-content')?.querySelector('.msg-gemini-text')?.innerText; if(txt) navigator.clipboard.writeText(txt).then(()=>alert('Copiado!')); }
async function regenerateLast() { const chat = chats.find(c=>c.id===currentChatId); if(chat && chat.messages.length>=2) { const lastUser = [...chat.messages].reverse().find(m=>m.role==='user'); if(lastUser) { chat.messages.pop(); document.getElementById('messages').lastElementChild?.remove(); addTyping(); const newReply = await callGeminiAI(lastUser.text); removeTyping(); addGeminiMsg(newReply); saveChats(); } } }
function toggleSidebar() { document.getElementById('sidebar')?.classList.toggle('open'); document.getElementById('sidebar-overlay')?.classList.toggle('active'); }
function closeSidebar() { document.getElementById('sidebar')?.classList.remove('open'); document.getElementById('sidebar-overlay')?.classList.remove('active'); }
function toggleModelMenu() { const models = ['Geminix Pro', 'Geminix Ultra', 'Geminix Lite']; const span = document.getElementById('model-name'); let idx = models.indexOf(span.innerText); span.innerText = models[(idx+1)%models.length]; }
function openSettings() { document.getElementById('settings-modal').style.display = 'flex'; }
function closeSettings() { document.getElementById('settings-modal').style.display = 'none'; saveSettingsToLocal(); }
function setTheme(theme) { document.body.classList.remove('light-theme','dark-theme'); if(theme==='light') document.body.classList.add('light-theme'); localStorage.setItem('geminix_theme', theme); document.querySelectorAll('.theme-btn').forEach(btn=>btn.classList.remove('active')); document.querySelector(`.theme-btn[data-theme="${theme}"]`)?.classList.add('active'); }
function setFontSize(size) { document.body.classList.remove('font-small','font-medium','font-large','font-xlarge'); document.body.classList.add(`font-${size}`); localStorage.setItem('geminix_font', size); document.querySelectorAll('.font-btn').forEach(btn=>btn.classList.remove('active')); document.querySelector(`.font-btn[data-font="${size}"]`)?.classList.add('active'); }
function setDeviceMode(mode) { localStorage.setItem('geminix_device', mode); document.querySelectorAll('.device-card').forEach(card=>card.classList.remove('active')); document.querySelector(`.device-card[data-device="${mode}"]`)?.classList.add('active'); if(mode==='mobile') { document.body.style.setProperty('--sidebar-width', '280px'); } else { document.body.style.setProperty('--sidebar-width', '280px'); } if(window.innerWidth<=768 && mode==='pc') alert('Modo PC ativado. Para melhor experiência, gire o celular ou use desktop.'); }
function saveSettingsToLocal() { const saveHistory = document.getElementById('save-history').checked; localStorage.setItem('geminix_save_history', saveHistory); const responseMode = document.getElementById('response-mode').value; localStorage.setItem('geminix_response_mode', responseMode); }
function loadSettings() { const theme = localStorage.getItem('geminix_theme') || 'dark'; setTheme(theme); const font = localStorage.getItem('geminix_font') || 'medium'; setFontSize(font); const device = localStorage.getItem('geminix_device') || (window.innerWidth<=768?'mobile':'pc'); setDeviceMode(device); const saveHistory = localStorage.getItem('geminix_save_history'); if(saveHistory !== null) document.getElementById('save-history').checked = saveHistory === 'true'; const responseMode = localStorage.getItem('geminix_response_mode'); if(responseMode) document.getElementById('response-mode').value = responseMode; }

window.autoResize=autoResize; window.updateSendBtn=updateSendBtn; window.handleKey=handleKey; window.sendMessage=sendMessage; window.newChat=newChat; window.fillInput=fillInput; window.copyText=copyText; window.regenerateLast=regenerateLast; window.toggleSidebar=toggleSidebar; window.toggleModelMenu=toggleModelMenu; window.clearAllChats=clearAllChats; window.exportChat=exportChat; window.closeSidebar=closeSidebar; window.openSettings=openSettings; window.closeSettings=closeSettings; window.setTheme=setTheme; window.setFontSize=setFontSize; window.setDeviceMode=setDeviceMode;

loadSettings(); loadChats(); if(!chats.length) resetDefault(); renderChatList(); updateSendBtn(); if(chats.length && chats[0].messages.length) selectChat(chats[0].id);
</script>
</body>
</html>
