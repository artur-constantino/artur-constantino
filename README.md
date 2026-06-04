<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GitHub Profile — Artur Constantino</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0d1117;
    --surface: #161b22;
    --surface2: #21262d;
    --border: #30363d;
    --accent: #58a6ff;
    --accent2: #3fb950;
    --accent3: #f78166;
    --text: #e6edf3;
    --muted: #8b949e;
    --mono: 'JetBrains Mono', monospace;
    --sans: 'Syne', sans-serif;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--mono);
    min-height: 100vh;
    padding: 2rem 1rem;
    line-height: 1.6;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
  }

  /* ── HEADER ── */
  .header {
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 2rem 2.5rem;
    background: var(--surface);
    margin-bottom: 1.5rem;
    position: relative;
    overflow: hidden;
  }

  .header::before {
    content: '';
    position: absolute;
    top: -40px; right: -40px;
    width: 220px; height: 220px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(88,166,255,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .name-line {
    font-family: var(--sans);
    font-size: 2.2rem;
    font-weight: 800;
    letter-spacing: -0.5px;
    color: var(--text);
  }

  .name-line span {
    color: var(--accent);
  }

  .tagline {
    font-size: 0.9rem;
    color: var(--muted);
    margin-top: 0.4rem;
    margin-bottom: 1.2rem;
  }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 1rem;
  }

  .badge {
    font-size: 0.72rem;
    padding: 4px 12px;
    border-radius: 20px;
    font-weight: 700;
    letter-spacing: 0.5px;
    text-transform: uppercase;
    border: 1px solid;
  }

  .badge-blue  { background: rgba(88,166,255,0.12); color: #58a6ff; border-color: rgba(88,166,255,0.3); }
  .badge-green { background: rgba(63,185,80,0.12);  color: #3fb950; border-color: rgba(63,185,80,0.3); }
  .badge-red   { background: rgba(247,129,102,0.12); color: #f78166; border-color: rgba(247,129,102,0.3); }
  .badge-yellow{ background: rgba(210,153,34,0.12); color: #d29922; border-color: rgba(210,153,34,0.3); }

  .contact-row {
    display: flex;
    flex-wrap: wrap;
    gap: 1.5rem;
    margin-top: 1.2rem;
    font-size: 0.82rem;
    color: var(--muted);
  }

  .contact-row a {
    color: var(--accent);
    text-decoration: none;
  }

  .contact-row a:hover { text-decoration: underline; }

  /* ── TYPING ANIMATION ── */
  .typing-wrap {
    font-size: 1rem;
    color: var(--accent2);
    margin-top: 0.6rem;
  }

  .cursor {
    display: inline-block;
    width: 2px;
    height: 1em;
    background: var(--accent2);
    vertical-align: text-bottom;
    animation: blink 1s step-end infinite;
  }

  @keyframes blink { 50% { opacity: 0; } }

  /* ── SECTION TITLE ── */
  .section-title {
    font-family: var(--sans);
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 0.8rem;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── GRID ── */
  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.2rem;
    margin-bottom: 1.5rem;
  }

  .grid-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 1.2rem;
    margin-bottom: 1.5rem;
  }

  @media (max-width: 640px) {
    .grid-2, .grid-3 { grid-template-columns: 1fr; }
  }

  /* ── CARD ── */
  .card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 1.25rem 1.4rem;
    transition: border-color 0.2s;
  }

  .card:hover { border-color: #58a6ff55; }

  .card-title {
    font-family: var(--sans);
    font-size: 0.95rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 0.3rem;
  }

  .card-sub {
    font-size: 0.75rem;
    color: var(--accent);
    margin-bottom: 0.6rem;
  }

  .card-body {
    font-size: 0.78rem;
    color: var(--muted);
    line-height: 1.7;
  }

  .card-body li {
    padding-left: 1rem;
    position: relative;
    margin-bottom: 3px;
    list-style: none;
  }

  .card-body li::before {
    content: '▸';
    position: absolute;
    left: 0;
    color: var(--accent2);
    font-size: 0.65rem;
    top: 3px;
  }

  /* ── SKILL PILL ── */
  .skill-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 1.5rem;
  }

  .skill {
    font-size: 0.76rem;
    padding: 5px 14px;
    border-radius: 6px;
    background: var(--surface2);
    border: 1px solid var(--border);
    color: var(--text);
    font-weight: 400;
    transition: border-color 0.2s, background 0.2s;
  }

  .skill:hover {
    border-color: var(--accent);
    background: rgba(88,166,255,0.08);
    color: var(--accent);
  }

  /* ── PROGRESS BAR ── */
  .lang-row {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 8px;
    font-size: 0.8rem;
  }

  .lang-name { min-width: 80px; color: var(--text); }
  .lang-bar-wrap { flex: 1; background: var(--surface2); border-radius: 4px; height: 8px; overflow: hidden; border: 1px solid var(--border); }
  .lang-bar { height: 100%; border-radius: 4px; }
  .lang-pct { min-width: 36px; text-align: right; color: var(--muted); font-size: 0.73rem; }

  /* ── STAT BOXES ── */
  .stat-box {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 1rem;
    text-align: center;
  }

  .stat-num {
    font-family: var(--sans);
    font-size: 1.6rem;
    font-weight: 800;
    color: var(--accent);
  }

  .stat-label {
    font-size: 0.7rem;
    color: var(--muted);
    margin-top: 2px;
    text-transform: uppercase;
    letter-spacing: 1px;
  }

  /* ── TIMELINE ── */
  .timeline { position: relative; padding-left: 1.4rem; margin-bottom: 1.5rem; }
  .timeline::before { content: ''; position: absolute; left: 4px; top: 4px; bottom: 4px; width: 1px; background: var(--border); }

  .tl-item { position: relative; margin-bottom: 1.2rem; }
  .tl-dot { position: absolute; left: -1.35rem; top: 5px; width: 9px; height: 9px; border-radius: 50%; background: var(--accent); border: 2px solid var(--bg); }
  .tl-dot.green { background: var(--accent2); }

  .tl-date { font-size: 0.7rem; color: var(--muted); margin-bottom: 2px; }
  .tl-title { font-size: 0.88rem; color: var(--text); font-weight: 700; font-family: var(--sans); }
  .tl-company { font-size: 0.76rem; color: var(--accent); margin-bottom: 4px; }
  .tl-desc { font-size: 0.76rem; color: var(--muted); line-height: 1.65; }

  /* ── CERT LIST ── */
  .cert-item {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    padding: 8px 0;
    border-bottom: 1px solid var(--border);
    font-size: 0.78rem;
  }

  .cert-item:last-child { border-bottom: none; }
  .cert-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--accent3); margin-top: 5px; flex-shrink: 0; }
  .cert-name { color: var(--text); }
  .cert-org { color: var(--muted); margin-left: auto; white-space: nowrap; padding-left: 12px; font-size: 0.72rem; }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    font-size: 0.72rem;
    color: var(--muted);
    padding: 2rem 0 1rem;
  }

  .footer span { color: var(--accent3); }

  /* ── COMMENT BLOCK ── */
  .comment {
    color: #636e7b;
    font-size: 0.78rem;
    margin-bottom: 1rem;
    font-style: italic;
  }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <div class="header">
    <p class="comment">/* github.com/arturconstantino — README.md */</p>
    <div class="name-line">Artur <span>Constantino</span></div>
    <div class="tagline">Sapé, Paraíba · arturdesouzabrasil@gmail.com · +55 (83) 99674-3955</div>
    <div class="typing-wrap" id="typing"><span id="typed-text"></span><span class="cursor"></span></div>
    <div class="badges">
      <span class="badge badge-blue">Suporte em TI</span>
      <span class="badge badge-green">Infraestrutura</span>
      <span class="badge badge-yellow">BI Júnior</span>
      <span class="badge badge-red">Ciência de Dados</span>
      <span class="badge badge-blue">Open to Work</span>
      <span class="badge badge-green">Home Office ✓</span>
    </div>
    <div class="contact-row">
      <span>📍 Sapé — PB</span>
      <a href="https://www.linkedin.com/in/arturconstantino" target="_blank">🔗 linkedin.com/in/arturconstantino</a>
      <span>🌐 PT · EN · ES</span>
      <span>🚗 CNH-B</span>
    </div>
  </div>

  <!-- STATS -->
  <div class="section-title">stats</div>
  <div class="grid-3" style="margin-bottom:1.5rem">
    <div class="stat-box">
      <div class="stat-num">3+</div>
      <div class="stat-label">Anos de Experiência</div>
    </div>
    <div class="stat-box">
      <div class="stat-num">15+</div>
      <div class="stat-label">Certificações</div>
    </div>
    <div class="stat-box">
      <div class="stat-num">4</div>
      <div class="stat-label">Formações Ativas</div>
    </div>
  </div>

  <!-- OBJECTIVE -->
  <div class="section-title">objetivo</div>
  <div class="card" style="margin-bottom:1.5rem">
    <div class="card-body" style="font-size:0.85rem; color:var(--text); line-height:1.9">
      Buscando oportunidades em início de carreira em <span style="color:var(--accent)">Suporte de TI</span>,
      <span style="color:var(--accent2)">Infraestrutura</span> ou <span style="color:var(--accent3)">Analista de BI Júnior</span>.
      Foco em garantir continuidade de processos internos através de soluções eficientes,
      suporte ágil aos usuários e otimização de fluxos de trabalho.
    </div>
  </div>

  <!-- EXPERIÊNCIA -->
  <div class="section-title">experiência profissional</div>
  <div class="timeline">
    <div class="tl-item">
      <div class="tl-dot green"></div>
      <div class="tl-date">jul/2025 – atual</div>
      <div class="tl-title">Suporte em TI / Administração de Sistemas</div>
      <div class="tl-company">Centro Médico Sapé</div>
      <div class="tl-desc">
        Manutenção de computadores, rede local e suporte técnico a usuários.
        Configuração e monitoramento do sistema interno. Automação de rotinas e gestão de canais digitais.
      </div>
    </div>
    <div class="tl-item">
      <div class="tl-dot"></div>
      <div class="tl-date">nov/2024 – mai/2025</div>
      <div class="tl-title">Suporte Financeiro & Suporte de TI</div>
      <div class="tl-company">Varejo e Comércio de Produtos Locais</div>
      <div class="tl-desc">
        Suporte técnico em hardware, software e resolução de problemas operacionais.
        Organização de dados e relatórios financeiros em Excel.
      </div>
    </div>
    <div class="tl-item">
      <div class="tl-dot"></div>
      <div class="tl-date">jul/2024 – out/2024</div>
      <div class="tl-title">Suporte em TI / Administração de Sistemas</div>
      <div class="tl-company">MG Móveis</div>
      <div class="tl-desc">
        Administração de sistemas internos, suporte técnico a colaboradores e apoio direto às operações administrativas.
      </div>
    </div>
  </div>

  <!-- FORMAÇÃO -->
  <div class="section-title">formação acadêmica</div>
  <div class="grid-2" style="margin-bottom:1.5rem">
    <div class="card">
      <div class="card-title">Gestão Comercial</div>
      <div class="card-sub">IFPB · Conclusão: 2025</div>
      <div class="card-body">Superior de Tecnologia</div>
    </div>
    <div class="card">
      <div class="card-title">Ciência da Computação</div>
      <div class="card-sub">Unipê · Em andamento</div>
      <div class="card-body">Bacharelado</div>
    </div>
    <div class="card">
      <div class="card-title">Ciências de Dados & IA</div>
      <div class="card-sub">Faculdade Líbano · Em andamento</div>
      <div class="card-body">Pós-graduação</div>
    </div>
    <div class="card">
      <div class="card-title">Gestão de TI & Projetos</div>
      <div class="card-sub">Faculdade Líbano · Em andamento</div>
      <div class="card-body">Pós-graduação</div>
    </div>
  </div>

  <!-- IDIOMAS -->
  <div class="section-title">idiomas</div>
  <div class="card" style="margin-bottom:1.5rem">
    <div class="lang-row">
      <span class="lang-name">Português</span>
      <div class="lang-bar-wrap"><div class="lang-bar" style="width:100%;background:#58a6ff"></div></div>
      <span class="lang-pct">Nativo</span>
    </div>
    <div class="lang-row">
      <span class="lang-name">Inglês</span>
      <div class="lang-bar-wrap"><div class="lang-bar" style="width:55%;background:#3fb950"></div></div>
      <span class="lang-pct">B1</span>
    </div>
    <div class="lang-row">
      <span class="lang-name">Espanhol</span>
      <div class="lang-bar-wrap"><div class="lang-bar" style="width:55%;background:#d29922"></div></div>
      <span class="lang-pct">B1</span>
    </div>
  </div>

  <!-- TECH SKILLS -->
  <div class="section-title">tech skills</div>
  <div class="skill-grid">
    <span class="skill">Infraestrutura de TI</span>
    <span class="skill">Segurança Digital</span>
    <span class="skill">LGPD</span>
    <span class="skill">Power BI</span>
    <span class="skill">Excel</span>
    <span class="skill">Word</span>
    <span class="skill">PowerPoint</span>
    <span class="skill">Windows</span>
    <span class="skill">Linux</span>
    <span class="skill">Redes Locais</span>
    <span class="skill">Hardware</span>
    <span class="skill">Redes Sociais</span>
    <span class="skill">Automação de Rotinas</span>
    <span class="skill">Relatórios Financeiros</span>
  </div>

  <!-- SOFT SKILLS -->
  <div class="section-title">soft skills</div>
  <div class="grid-2" style="margin-bottom:1.5rem">
    <div class="card">
      <div class="card-title">⚡ Proatividade</div>
      <div class="card-body">Iniciativa para identificar e resolver problemas antes que se tornem críticos.</div>
    </div>
    <div class="card">
      <div class="card-title">💬 Comunicação</div>
      <div class="card-body">Habilidade para transmitir informações técnicas de forma clara a diferentes públicos.</div>
    </div>
    <div class="card">
      <div class="card-title">📋 Organização</div>
      <div class="card-body">Gestão eficiente de múltiplas demandas com foco em prazos e qualidade.</div>
    </div>
    <div class="card">
      <div class="card-title">🔄 Adaptabilidade</div>
      <div class="card-body">Facilidade em aprender novas ferramentas e se ajustar a ambientes diferentes.</div>
    </div>
  </div>

  <!-- CERTIFICAÇÕES -->
  <div class="section-title">certificações</div>
  <div class="card" style="margin-bottom:1.5rem">
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Fundamentos de TI: Hardware e Software</span><span class="cert-org">Bradesco · 2024</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Segurança em Tecnologia da Informação</span><span class="cert-org">Bradesco · 2024</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Lei Geral de Proteção de Dados (LGPD)</span><span class="cert-org">Bradesco · 2024</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Segurança Digital</span><span class="cert-org">FGV · 2025</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">TI como Elemento Estratégico nas Organizações</span><span class="cert-org">FGV · 2025</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">IA e Produtividade</span><span class="cert-org">Google / Santander · 2025</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Power BI</span><span class="cert-org">CCO · 2024</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Excel Avançado</span><span class="cert-org">CCO · 2024</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Gestão de Projetos</span><span class="cert-org">Bradesco · 2024</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Estratégia de Negócios</span><span class="cert-org">Bradesco · 2025</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Empreendedorismo e Inovação</span><span class="cert-org">Bradesco · 2025</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Ecossistema de Fintechs</span><span class="cert-org">FGV · 2025</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Gestão Financeira</span><span class="cert-org">Sebrae · 2024</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Marketing Digital</span><span class="cert-org">2024</span></div>
    <div class="cert-item"><div class="cert-dot"></div><span class="cert-name">Liderança: Times de Alta Performance</span><span class="cert-org">Sebrae · 2024</span></div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <span>❤</span> feito com dedicação · aberto a novas oportunidades · <a href="https://www.linkedin.com/in/arturconstantino" style="color:var(--accent);text-decoration:none">linkedin</a>
  </div>

</div>

<script>
  const phrases = [
    'IT Support & Systems Admin',
    'Power BI | Excel | Infraestrutura',
    'Disponível para Home Office 🌐',
    'Aprendendo sempre. Evoluindo sempre.',
  ];
  let pi = 0, ci = 0, deleting = false;
  const el = document.getElementById('typed-text');
  function type() {
    const phrase = phrases[pi];
    if (!deleting) {
      el.textContent = phrase.slice(0, ++ci);
      if (ci === phrase.length) { deleting = true; setTimeout(type, 1800); return; }
    } else {
      el.textContent = phrase.slice(0, --ci);
      if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; setTimeout(type, 300); return; }
    }
    setTimeout(type, deleting ? 40 : 65);
  }
  setTimeout(type, 600);
</script>
</body>
</html>
