<!doctype html>
<html lang="pt-BR">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>ORION — IA conversacional avançada em português</title>
<meta name="description" content="Converse com ORION, uma IA poderosa: chat em tempo real, análise de imagens, histórico de conversas, totalmente em português." />
<meta property="og:title" content="ORION — IA conversacional avançada em português" />
<meta property="og:description" content="Converse com ORION, uma IA poderosa: chat em tempo real, análise de imagens e histórico de conversas." />
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Space+Grotesk:wght@600;700;800&display=swap" rel="stylesheet" />
<style>
  :root{
    --bg:#0a0a1a; --bg2:#141432; --fg:#ececf1; --muted:#9aa0b4;
    --primary:#6366f1; --primary-glow:#818cf8; --border:rgba(255,255,255,.1);
  }
  *{box-sizing:border-box}
  html,body{margin:0;padding:0;background:var(--bg);color:var(--fg);font-family:Inter,system-ui,sans-serif;-webkit-font-smoothing:antialiased}
  a{color:inherit;text-decoration:none}
  .wrap{max-width:1200px;margin:0 auto;padding:0 1.5rem}
  .orb{position:absolute;top:-200px;left:50%;transform:translateX(-50%);width:800px;height:800px;border-radius:50%;background:radial-gradient(circle,var(--primary) 0%,transparent 70%);opacity:.25;filter:blur(120px);pointer-events:none;z-index:0}
  header{position:relative;z-index:10;display:flex;align-items:center;justify-content:space-between;padding:1.5rem 0}
  .logo{display:flex;align-items:center;gap:.5rem;font-family:'Space Grotesk',sans-serif;font-weight:800;font-size:1.25rem;letter-spacing:.02em}
  .logo-dot{width:28px;height:28px;border-radius:8px;background:linear-gradient(135deg,var(--primary),var(--primary-glow));box-shadow:0 0 20px rgba(129,140,248,.5)}
  .btn{display:inline-flex;align-items:center;gap:.5rem;padding:.6rem 1.1rem;border-radius:10px;font-weight:600;font-size:.9rem;border:1px solid transparent;cursor:pointer;transition:all .2s}
  .btn-ghost{background:transparent;color:var(--fg)}
  .btn-ghost:hover{background:rgba(255,255,255,.06)}
  .btn-primary{background:linear-gradient(135deg,var(--primary),var(--primary-glow));color:#fff;box-shadow:0 8px 32px rgba(99,102,241,.4)}
  .btn-primary:hover{opacity:.9}
  .btn-outline{background:transparent;color:var(--fg);border-color:var(--border)}
  .btn-lg{padding:.85rem 1.6rem;font-size:1rem}
  main{position:relative;z-index:10;text-align:center;padding:4rem 1.5rem 6rem;max-width:1000px;margin:0 auto}
  .pill{display:inline-flex;align-items:center;gap:.5rem;padding:.4rem 1rem;border-radius:999px;background:rgba(255,255,255,.04);border:1px solid var(--border);font-size:.78rem;color:var(--muted);backdrop-filter:blur(10px);margin-bottom:2rem}
  h1{font-family:'Space Grotesk',sans-serif;font-size:clamp(2.5rem,6vw,4.5rem);font-weight:800;line-height:1.05;letter-spacing:-.02em;margin:0}
  .gradient{background:linear-gradient(135deg,var(--primary-glow),#c4b5fd);-webkit-background-clip:text;background-clip:text;color:transparent}
  .lead{margin:2rem auto 0;max-width:640px;font-size:1.1rem;color:var(--muted);line-height:1.6}
  .ctas{margin-top:2.5rem;display:flex;gap:.75rem;justify-content:center;flex-wrap:wrap}
  section.features{margin-top:6rem}
  h2{font-family:'Space Grotesk',sans-serif;font-size:clamp(1.75rem,3.5vw,2.5rem);font-weight:700;margin:0 0 2.5rem;background:linear-gradient(135deg,var(--primary-glow),#c4b5fd);-webkit-background-clip:text;background-clip:text;color:transparent}
  .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:1rem;text-align:left}
  .card{background:rgba(255,255,255,.03);border:1px solid var(--border);border-radius:18px;padding:1.5rem;backdrop-filter:blur(10px);transition:all .2s}
  .card:hover{border-color:rgba(129,140,248,.4);box-shadow:0 8px 32px rgba(99,102,241,.15)}
  .card svg{color:var(--primary-glow);margin-bottom:.75rem}
  .card h3{margin:0;font-family:'Space Grotesk',sans-serif;font-size:1.1rem;font-weight:600}
  .card p{margin:.4rem 0 0;color:var(--muted);font-size:.9rem;line-height:1.5}
  footer{position:relative;z-index:10;border-top:1px solid rgba(255,255,255,.06);padding:2rem;text-align:center;color:var(--muted);font-size:.8rem}
  footer a{color:var(--primary-glow)}
  footer a:hover{text-decoration:underline}
  @keyframes fade-up{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:none}}
  main{animation:fade-up .6s ease-out}
</style>
</head>
<body>
<div class="orb"></div>
<header class="wrap">
  <div class="logo"><span class="logo-dot"></span>ORION</div>
  <div style="display:flex;gap:.5rem">
    <a href="https://orion-com.lovable.app/login" class="btn btn-ghost">Entrar</a>
    <a href="https://orion-com.lovable.app/login" class="btn btn-primary">Começar grátis</a>
  </div>
</header>

<main>
  <div class="pill">
    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="color:var(--primary-glow)"><path d="M12 2l2.4 7.4H22l-6.2 4.5L18.2 22 12 17.5 5.8 22l2.4-8.1L2 9.4h7.6z"/></svg>
    Powered by Gemini 2.5 — Resposta inteligente em tempo real
  </div>
  <h1>A inteligência artificial<br/><span class="gradient">do futuro</span>, hoje.</h1>
  <p class="lead">ORION é seu copiloto de IA: chat avançado, análise de imagens, geração de código e histórico completo — tudo em português brasileiro.</p>
  <div class="ctas">
    <a href="https://orion-com.lovable.app/login" class="btn btn-primary btn-lg">Começar agora →</a>
    <a href="#features" class="btn btn-outline btn-lg">Conhecer recursos</a>
  </div>

  <section id="features" class="features">
    <h2>Recursos do ORION</h2>
    <div class="grid">
      <div class="card"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg><h3>Chat em tempo real</h3><p>Respostas streaming, fluidas e contextuais.</p></div>
      <div class="card"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="9" cy="9" r="2"/><path d="m21 15-5-5L5 21"/></svg><h3>Análise de imagens</h3><p>Envie imagens e ORION as compreende.</p></div>
      <div class="card"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M13 2 3 14h9l-1 8 10-12h-9z"/></svg><h3>Memória de contexto</h3><p>Histórico completo, retoma de onde parou.</p></div>
      <div class="card"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg><h3>Seguro e privado</h3><p>Seus dados protegidos, só você acessa.</p></div>
      <div class="card"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M2 12h20M12 2a15 15 0 0 1 0 20M12 2a15 15 0 0 0 0 20"/></svg><h3>Multi-idioma</h3><p>Português, inglês, espanhol e mais.</p></div>
      <div class="card"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2l2.4 7.4H22l-6.2 4.5L18.2 22 12 17.5 5.8 22l2.4-8.1L2 9.4h7.6z"/></svg><h3>Geração de código</h3><p>Snippets, debug, refactor — instantâneo.</p></div>
    </div>
  </section>
</main>

<footer>© 2026 ORION. Suporte: <a href="mailto:kaike.lima.zerado@gmail.com">kaike.lima.zerado@gmail.com</a></footer>
</body>
</html>
