<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Play Book de Uso de Antibióticos — HGRO Orizaba</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@300;400;500;600;700&family=IBM+Plex+Mono:wght@400;500&family=Crimson+Pro:ital,wght@0,400;0,600;1,400&display=swap');
 
  :root {
    --bg: #0d1117;
    --surface: #161b22;
    --surface2: #1c2128;
    --border: #30363d;
    --accent: #58a6ff;
    --accent2: #3fb950;
    --warn: #d29922;
    --danger: #f85149;
    --purple: #bc8cff;
    --teal: #39d3c3;
    --text: #e6edf3;
    --text-muted: #8b949e;
    --text-dim: #484f58;
  }
 
  * { box-sizing: border-box; margin: 0; padding: 0; }
 
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'IBM Plex Sans', sans-serif;
    font-size: 14px;
    line-height: 1.6;
    min-height: 100vh;
  }
 
  /* ── HEADER ── */
  .header {
    background: linear-gradient(135deg, #0d1117 0%, #161b22 50%, #0d1117 100%);
    border-bottom: 1px solid var(--border);
    padding: 32px 40px 24px;
    position: relative;
    overflow: hidden;
  }
  .header::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--accent), var(--teal), var(--accent2));
  }
  .header-grid {
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: start;
    gap: 20px;
    max-width: 1200px;
    margin: 0 auto;
  }
  .header-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: rgba(88,166,255,0.12);
    border: 1px solid rgba(88,166,255,0.3);
    border-radius: 20px;
    padding: 4px 12px;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.08em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 12px;
  }
  .header-title {
    font-family: 'Crimson Pro', Georgia, serif;
    font-size: 32px;
    font-weight: 600;
    color: var(--text);
    line-height: 1.2;
  }
  .header-subtitle {
    font-size: 13px;
    color: var(--text-muted);
    margin-top: 8px;
  }
  .header-meta {
    text-align: right;
    font-size: 12px;
    color: var(--text-muted);
    line-height: 1.8;
  }
  .meta-label { color: var(--text-dim); font-size: 10px; text-transform: uppercase; letter-spacing: 0.1em; }
 
  /* ── ALERT BOXES ── */
  .alert-strip {
    max-width: 1200px;
    margin: 20px auto 0;
    padding: 10px 16px;
    background: rgba(210,153,34,0.1);
    border: 1px solid rgba(210,153,34,0.35);
    border-radius: 6px;
    font-size: 12px;
    color: var(--warn);
    display: flex;
    gap: 8px;
    align-items: flex-start;
  }
 
  /* ── LAYOUT ── */
  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 24px 40px 60px;
  }
 
  /* ── STAT PILLS ── */
  .stats-row {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    margin-bottom: 28px;
  }
  .stat-pill {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 18px;
    display: flex;
    flex-direction: column;
    gap: 2px;
  }
  .stat-pill .num { font-size: 22px; font-weight: 700; font-family: 'IBM Plex Mono', monospace; }
  .stat-pill .lbl { font-size: 11px; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.06em; }
  .col-blue { color: var(--accent); }
  .col-green { color: var(--accent2); }
  .col-warn { color: var(--warn); }
  .col-red { color: var(--danger); }
  .col-purple { color: var(--purple); }
  .col-teal { color: var(--teal); }
 
  /* ── RESISTANCE LEGEND ── */
  .legend-row {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
    margin-bottom: 28px;
    align-items: center;
  }
  .legend-item {
    display: flex;
    align-items: center;
    gap: 6px;
    font-size: 12px;
    color: var(--text-muted);
  }
  .legend-dot {
    width: 10px; height: 10px;
    border-radius: 50%;
    flex-shrink: 0;
  }
 
  /* ── NAV ── */
  .toc {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px 24px;
    margin-bottom: 32px;
  }
  .toc-title {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--text-muted);
    margin-bottom: 14px;
  }
  .toc-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 6px;
  }
  .toc-link {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 6px 10px;
    border-radius: 6px;
    text-decoration: none;
    font-size: 13px;
    color: var(--text-muted);
    transition: background 0.15s, color 0.15s;
    border: 1px solid transparent;
  }
  .toc-link:hover {
    background: var(--surface2);
    color: var(--accent);
    border-color: var(--border);
  }
  .toc-type {
    font-size: 10px;
    padding: 1px 6px;
    border-radius: 3px;
    font-weight: 600;
    flex-shrink: 0;
  }
  .type-gram-neg { background: rgba(88,166,255,0.15); color: var(--accent); }
  .type-gram-pos { background: rgba(63,185,80,0.15); color: var(--accent2); }
  .type-fungal { background: rgba(188,140,255,0.15); color: var(--purple); }
 
  /* ── ORGANISM CARDS ── */
  .org-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    margin-bottom: 28px;
    overflow: hidden;
    scroll-margin-top: 20px;
  }
  .org-card:hover {
    border-color: #444c56;
  }
 
  .card-header {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    padding: 20px 24px 16px;
    border-bottom: 1px solid var(--border);
    gap: 12px;
    flex-wrap: wrap;
  }
  .card-header-left { flex: 1; min-width: 200px; }
  .org-name {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 17px;
    font-weight: 500;
    font-style: italic;
    color: var(--text);
    line-height: 1.3;
  }
  .org-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-top: 8px;
  }
  .tag {
    font-size: 10px;
    font-weight: 600;
    padding: 2px 8px;
    border-radius: 4px;
    letter-spacing: 0.05em;
    text-transform: uppercase;
  }
  .tag-gram-neg { background: rgba(88,166,255,0.1); color: var(--accent); border: 1px solid rgba(88,166,255,0.2); }
  .tag-gram-pos { background: rgba(63,185,80,0.1); color: var(--accent2); border: 1px solid rgba(63,185,80,0.2); }
  .tag-fungal { background: rgba(188,140,255,0.1); color: var(--purple); border: 1px solid rgba(188,140,255,0.2); }
  .tag-mdr { background: rgba(248,81,73,0.1); color: var(--danger); border: 1px solid rgba(248,81,73,0.2); }
  .tag-mrsa { background: rgba(248,81,73,0.1); color: var(--danger); border: 1px solid rgba(248,81,73,0.2); }
  .tag-esbl { background: rgba(210,153,34,0.1); color: var(--warn); border: 1px solid rgba(210,153,34,0.2); }
  .tag-alert { background: rgba(248,81,73,0.1); color: var(--danger); border: 1px solid rgba(248,81,73,0.2); }
 
  .card-header-right {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 6px;
  }
  .rank-badge {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 11px;
    color: var(--text-muted);
    white-space: nowrap;
  }
  .rank-bar-bg {
    width: 80px;
    height: 4px;
    background: var(--border);
    border-radius: 2px;
    overflow: hidden;
  }
  .rank-bar-fill { height: 100%; border-radius: 2px; }
 
  /* ── SECTIONS ── */
  .card-sections {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    border-top: 1px solid var(--border);
  }
  @media (max-width: 900px) {
    .card-sections { grid-template-columns: 1fr; }
  }
  .section {
    padding: 18px 20px 20px;
    border-right: 1px solid var(--border);
  }
  .section:last-child { border-right: none; }
 
  .section-label {
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 7px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--border);
  }
  .sl-epidemio { color: var(--teal); }
  .sl-terapia { color: var(--accent); }
  .sl-proa { color: var(--accent2); }
  .sl-dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    flex-shrink: 0;
  }
 
  /* ── DRUG BLOCKS ── */
  .drug-block {
    margin-bottom: 14px;
  }
  .drug-tier {
    font-size: 10px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--text-dim);
    margin-bottom: 5px;
  }
  .drug-box {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 10px 12px;
  }
  .drug-name {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 13px;
    font-weight: 500;
    color: var(--accent);
    margin-bottom: 4px;
  }
  .drug-name.green { color: var(--accent2); }
  .drug-name.purple { color: var(--purple); }
  .drug-name.warn { color: var(--warn); }
  .drug-name.teal { color: var(--teal); }
  .drug-dose {
    font-size: 12px;
    color: var(--text-muted);
    line-height: 1.5;
  }
  .drug-dose strong {
    color: var(--text);
    font-weight: 500;
    font-family: 'IBM Plex Mono', monospace;
  }
  .drug-dose em {
    font-style: normal;
    color: var(--warn);
    font-size: 11px;
  }
 
  /* ── NOTA TÉCNICA ── */
  .nota-tecnica {
    background: rgba(210,153,34,0.06);
    border: 1px solid rgba(210,153,34,0.25);
    border-left: 3px solid var(--warn);
    border-radius: 0 6px 6px 0;
    padding: 8px 10px;
    font-size: 11px;
    color: var(--warn);
    line-height: 1.5;
    margin-top: 8px;
  }
  .nota-tecnica strong { font-weight: 600; }
 
  /* ── CRITERIA LIST ── */
  .criteria-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 6px;
  }
  .criteria-list li {
    font-size: 12px;
    color: var(--text-muted);
    display: flex;
    gap: 7px;
    align-items: flex-start;
    line-height: 1.5;
  }
  .criteria-list li::before {
    content: '›';
    color: var(--accent2);
    font-size: 14px;
    flex-shrink: 0;
    line-height: 1.2;
    font-weight: 700;
  }
  .criteria-list li strong { color: var(--text); font-weight: 500; }
 
  .subsection-head {
    font-size: 11px;
    font-weight: 600;
    color: var(--text-muted);
    text-transform: uppercase;
    letter-spacing: 0.07em;
    margin-bottom: 6px;
    margin-top: 12px;
  }
  .subsection-head:first-child { margin-top: 0; }
 
  /* ── RESISTANCE TABLE mini ── */
  .resist-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 11px;
    padding: 4px 0;
    border-bottom: 1px solid var(--border);
    gap: 6px;
  }
  .resist-row:last-child { border-bottom: none; }
  .resist-drug { color: var(--text-muted); flex: 1; }
  .resist-pct {
    font-family: 'IBM Plex Mono', monospace;
    font-weight: 600;
    font-size: 12px;
    flex-shrink: 0;
  }
  .resist-bar {
    width: 50px;
    height: 3px;
    background: var(--border);
    border-radius: 2px;
    overflow: hidden;
    flex-shrink: 0;
  }
  .resist-bar-fill { height: 100%; border-radius: 2px; }
 
  .sens-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 11px;
    padding: 4px 0;
    border-bottom: 1px solid var(--border);
    gap: 6px;
  }
  .sens-row:last-child { border-bottom: none; }
  .sens-drug { color: var(--text-muted); flex: 1; }
  .sens-pct {
    font-family: 'IBM Plex Mono', monospace;
    font-weight: 600;
    font-size: 12px;
    flex-shrink: 0;
    color: var(--accent2);
  }
 
  /* ── DURATION BADGE ── */
  .duration-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: rgba(63,185,80,0.08);
    border: 1px solid rgba(63,185,80,0.2);
    border-radius: 6px;
    padding: 6px 12px;
    font-size: 12px;
    color: var(--accent2);
    margin-top: 8px;
  }
  .duration-badge .days {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 18px;
    font-weight: 700;
    color: var(--accent2);
    line-height: 1;
  }
 
  /* ── SECTION DIVIDER ── */
  .section-divider {
    display: flex;
    align-items: center;
    gap: 12px;
    margin: 32px 0 20px;
  }
  .section-divider hr { flex: 1; border: none; border-top: 1px solid var(--border); }
  .section-divider span {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--text-dim);
    white-space: nowrap;
  }
 
  /* ── FOOTER ── */
  footer {
    border-top: 1px solid var(--border);
    padding: 20px 40px;
    text-align: center;
    font-size: 11px;
    color: var(--text-dim);
    line-height: 1.8;
  }
 
  /* ── COLLAPSE ── */
  details > summary {
    list-style: none;
    cursor: pointer;
  }
  details > summary::-webkit-details-marker { display: none; }
 
  .collapse-trigger {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 11px;
    color: var(--text-dim);
    padding: 8px 0 0;
    user-select: none;
  }
  .collapse-trigger:hover { color: var(--accent); }
  details[open] .collapse-trigger { color: var(--accent); }
 
  /* Print */
  @media print {
    body { background: white; color: black; font-size: 11px; }
    .org-card { break-inside: avoid; border: 1px solid #ccc; }
  }
</style>
</head>
<body>
 
<!-- HEADER -->
<div class="header">
  <div class="header-grid">
    <div>
      <div class="header-badge">🏥 HGRO · IMSS · Orizaba, Veracruz</div>
      <h1 class="header-title">Play Book de Uso de Antimicrobianos</h1>
      <p class="header-subtitle">
        Guía de toma de decisiones rápida para residentes, internistas e intensivistas —
        fundamentada en la biota institucional real del HGRO · Criterios IDSA 2024 · Estrategia PROA
      </p>
    </div>
    <div class="header-meta">
      <div class="meta-label">Versión</div>
      <div>1.0 · Junio 2026</div>
      <div class="meta-label" style="margin-top:8px">Nivel de evidencia</div>
      <div>Biota institucional + IDSA</div>
      <div class="meta-label" style="margin-top:8px">Fuente de datos</div>
      <div>n ≥ 5,849 aislamientos</div>
    </div>
  </div>
 
  <div class="alert-strip" style="margin-top:20px;">
    ⚠️ <span><strong>AVISO LEGAL:</strong> Este documento es una herramienta de apoyo clínico basada en la epidemiología local del HGRO. No sustituye el juicio clínico individualizado. Toda prescripción debe considerar comorbilidades, función renal, alergias documentadas e interacciones farmacológicas. Ajustar dosis siempre por TFGe.</span>
  </div>
</div>
 
<!-- CONTAINER -->
<div class="container">
 
  <!-- ESTADÍSTICAS -->
  <div class="stats-row" style="margin-top:24px;">
    <div class="stat-pill"><span class="num col-blue">5,849</span><span class="lbl">Total aislamientos</span></div>
    <div class="stat-pill"><span class="num col-blue">4,890</span><span class="lbl">Consulta Externa</span></div>
    <div class="stat-pill"><span class="num col-warn">959</span><span class="lbl">Hospitalización</span></div>
    <div class="stat-pill"><span class="num col-red">35.7%</span><span class="lbl">MDR (Hospitalización)</span></div>
    <div class="stat-pill"><span class="num col-red">46%</span><span class="lbl">XDR (Hospitalización)</span></div>
    <div class="stat-pill"><span class="num col-green">11</span><span class="lbl">Microorganismos clave</span></div>
  </div>
 
  <!-- LEYENDA MDR -->
  <div class="legend-row">
    <span style="font-size:11px;color:var(--text-dim);font-weight:600;text-transform:uppercase;letter-spacing:0.08em;">Clasificación Magiorakos 2012:</span>
    <div class="legend-item"><div class="legend-dot" style="background:#3fb950;"></div>Sensible</div>
    <div class="legend-item"><div class="legend-dot" style="background:#58a6ff;"></div>Monorresistente</div>
    <div class="legend-item"><div class="legend-dot" style="background:#d29922;"></div>Resistente 2 clases</div>
    <div class="legend-item"><div class="legend-dot" style="background:#f85149;"></div>MDR (≥3 clases)</div>
    <div class="legend-item"><div class="legend-dot" style="background:#bc8cff;"></div>XDR</div>
  </div>
 
  <!-- ÍNDICE -->
  <div class="toc">
    <div class="toc-title">📋 Índice — Microorganismos por Biota Institucional HGRO</div>
    <div class="toc-grid">
      <a href="#ecoli" class="toc-link"><span class="toc-type type-gram-neg">G(−)</span>Escherichia coli</a>
      <a href="#kpneumo" class="toc-link"><span class="toc-type type-gram-neg">G(−)</span>Klebsiella pneumoniae</a>
      <a href="#paeruginosa" class="toc-link"><span class="toc-type type-gram-neg">G(−)</span>Pseudomonas aeruginosa</a>
      <a href="#pmirabilis" class="toc-link"><span class="toc-type type-gram-neg">G(−)</span>Proteus mirabilis</a>
      <a href="#abaumannii" class="toc-link"><span class="toc-type type-gram-neg">G(−)</span>Acinetobacter baumannii</a>
      <a href="#saureus" class="toc-link"><span class="toc-type type-gram-pos">G(+)</span>Staphylococcus aureus</a>
      <a href="#sepidermidis" class="toc-link"><span class="toc-type type-gram-pos">G(+)</span>S. epidermidis</a>
      <a href="#shaemolyticus" class="toc-link"><span class="toc-type type-gram-pos">G(+)</span>S. haemolyticus</a>
      <a href="#efaecalis" class="toc-link"><span class="toc-type type-gram-pos">G(+)</span>Enterococcus faecalis</a>
      <a href="#sagalactiae" class="toc-link"><span class="toc-type type-gram-pos">G(+)</span>Streptococcus agalactiae</a>
      <a href="#calbicans" class="toc-link"><span class="toc-type type-fungal">FUNG</span>Candida albicans</a>
    </div>
  </div>
 
  <!-- ══════════════════════════════════════════════════════
       1. ESCHERICHIA COLI
  ══════════════════════════════════════════════════════ -->
  <div class="section-divider"><hr/><span>Bacilos Gram negativos — Enterobacteriaceae</span><hr/></div>
 
  <div class="org-card" id="ecoli">
    <div class="card-header">
      <div class="card-header-left">
        <div class="org-name">Escherichia coli</div>
        <div class="org-tags">
          <span class="tag tag-gram-neg">Gram (−)</span>
          <span class="tag tag-esbl">BLEE Alta Prevalencia</span>
          <span class="tag tag-mdr">MDR Hospitalaria</span>
          <span class="tag" style="background:rgba(57,211,195,0.1);color:var(--teal);border:1px solid rgba(57,211,195,0.2);">#1 CE · #1 Hosp</span>
        </div>
      </div>
      <div class="card-header-right">
        <div class="rank-badge">CE: 2,115 aislamientos (43.3%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:100%;background:var(--accent);"></div></div></div>
        <div class="rank-badge">Hosp: 221 aislamientos (23%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:53%;background:var(--warn);"></div></div></div>
      </div>
    </div>
 
    <div class="card-sections">
      <!-- EPIDEMIOLOGÍA -->
      <div class="section">
        <div class="section-label sl-epidemio"><div class="sl-dot" style="background:var(--teal);"></div>Epidemiología Local</div>
 
        <div class="subsection-head">Perfil de Resistencia — CE</div>
        <div class="resist-row"><span class="resist-drug">Cefazolina (no orina)</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Tetraciclina</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Ceftazidima</span><span class="resist-pct" style="color:var(--danger);">88.4%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:88%;background:var(--danger);"></div></div></div>
 
        <div class="subsection-head" style="margin-top:10px;">Perfil de Resistencia — Hosp</div>
        <div class="resist-row"><span class="resist-drug">Cefazolina (no orina)</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Ceftazidima</span><span class="resist-pct" style="color:var(--danger);">94.2%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:94%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Meropenem (sensible)</span><span class="resist-pct" style="color:var(--accent2);">92.1%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:92%;background:var(--accent2);"></div></div></div>
 
        <div class="nota-tecnica" style="margin-top:12px;">
          <strong>⚠ Nota Técnica:</strong> Resistencia >88% a cefalosporinas de 3.ª generación confirma prevalencia de BLEE en esta institución. Las quinolonas (ciprofloxacino, levofloxacino) presentan resistencia significativa en hospitalización — no usar de forma empírica en infecciones graves. Mecanismo predominante: CTX-M tipo 1/9.
        </div>
 
        <div class="subsection-head" style="margin-top:12px;">Mayor Sensibilidad</div>
        <div class="sens-row"><span class="sens-drug">Tigeciclina</span><span class="sens-pct">99.5% (CE)</span></div>
        <div class="sens-row"><span class="sens-drug">Fosfomicina</span><span class="sens-pct">100% (CE)</span></div>
        <div class="sens-row"><span class="sens-drug">Meropenem</span><span class="sens-pct">92.1% (Hosp)</span></div>
        <div class="sens-row"><span class="sens-drug">Imipenem</span><span class="sens-pct">90.9% (Hosp)</span></div>
      </div>
 
      <!-- TERAPIA -->
      <div class="section">
        <div class="section-label sl-terapia"><div class="sl-dot" style="background:var(--accent);"></div>Esquema Terapéutico</div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica Inicial — Infección Urinaria (ITU)</div>
          <div class="drug-box">
            <div class="drug-name teal">Fosfomicina trometamol</div>
            <div class="drug-dose"><strong>3 g</strong> · VO · Dosis única (ITU no complicada)</div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Sepsis / Infección grave</div>
          <div class="drug-box">
            <div class="drug-name">Meropenem</div>
            <div class="drug-dose"><strong>1 g IV c/8 h</strong> · infusión 30 min<br><em>Reservar carbapenems — confirmar BLEE antes de escalar</em></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">✅ Terapia Dirigida (antibiograma)</div>
          <div class="drug-box">
            <div class="drug-name green">Ertapenem (si BLEE, sin Pseudomonas)</div>
            <div class="drug-dose"><strong>1 g IV c/24 h</strong> · infusión 30 min</div>
          </div>
        </div>
        <div class="drug-box" style="margin-bottom:14px;">
          <div class="drug-name green">Meropenem (sepsis grave / UCI)</div>
          <div class="drug-dose"><strong>1–2 g IV c/8 h</strong> · considerar infusión extendida (3–4 h) en UCI</div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔄 Alternativas — Alergia a betalactámicos</div>
          <div class="drug-box">
            <div class="drug-name warn">Tigeciclina</div>
            <div class="drug-dose"><strong>100 mg IV</strong> dosis carga, luego <strong>50 mg IV c/12 h</strong><br><em>No usar en bacteriemia primaria; actividad en ITU limitada</em></div>
          </div>
        </div>
 
        <div class="nota-tecnica">
          <strong>⚠ Nota Técnica:</strong> La alta resistencia a fluoroquinolonas en hospitalización hace que ciprofloxacino/levofloxacino NO sean opciones empíricas confiables para infecciones por E. coli en pacientes hospitalizados. Fosfomicina se reserva estrictamente para ITU no complicada (CE).
        </div>
      </div>
 
      <!-- PROA -->
      <div class="section">
        <div class="section-label sl-proa"><div class="sl-dot" style="background:var(--accent2);"></div>Estrategia PROA</div>
 
        <div class="subsection-head">Criterios de Desescalamiento</div>
        <ul class="criteria-list">
          <li>Antibiograma confirma sensibilidad a betalactámico de menor espectro</li>
          <li>Mejoría clínica sostenida ≥48–72 h (afebril, disminución PCR)</li>
          <li>Hemocultivos de control negativos (si bacteriemia)</li>
          <li>Desescalar carbapenems a Ertapenem si no hay Pseudomonas ni AmpC</li>
        </ul>
 
        <div class="subsection-head">Switch IV → VO</div>
        <ul class="criteria-list">
          <li>Temperatura < 38°C por ≥24 h sin antipirético</li>
          <li>Leucocitos en tendencia a la normalización</li>
          <li>Vía oral permeable y tránsito gastrointestinal conservado</li>
          <li>Hemodinámicamente estable (sin vasopresores)</li>
          <li><strong>Opción VO:</strong> Fosfomicina 3 g c/48 h (solo ITU)</li>
        </ul>
 
        <div class="subsection-head">Duración del Tratamiento</div>
        <ul class="criteria-list">
          <li><strong>ITU no complicada:</strong> dosis única (Fosfomicina)</li>
          <li><strong>ITU complicada / pielonefritis:</strong> 7 días</li>
          <li><strong>Bacteriemia sin foco:</strong> 14 días</li>
          <li><strong>Bacteriemia con foco (endovascular):</strong> 4–6 semanas</li>
          <li><strong>Infección intraabdominal:</strong> 4–7 días post control quirúrgico</li>
        </ul>
 
        <div class="duration-badge"><span class="days">7–14</span><span>días según foco</span></div>
      </div>
    </div>
  </div>
 
  <!-- ══════════════════════════════════════════════════════
       2. KLEBSIELLA PNEUMONIAE
  ══════════════════════════════════════════════════════ -->
  <div class="org-card" id="kpneumo">
    <div class="card-header">
      <div class="card-header-left">
        <div class="org-name">Klebsiella pneumoniae ssp. pneumoniae</div>
        <div class="org-tags">
          <span class="tag tag-gram-neg">Gram (−)</span>
          <span class="tag tag-esbl">BLEE Confirmada Hosp</span>
          <span class="tag tag-mdr">MDR / KPC Probable</span>
          <span class="tag" style="background:rgba(57,211,195,0.1);color:var(--teal);border:1px solid rgba(57,211,195,0.2);">#3 CE · #2 Hosp</span>
        </div>
      </div>
      <div class="card-header-right">
        <div class="rank-badge">CE: 485 aislamientos (9.9%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:22%;background:var(--accent);"></div></div></div>
        <div class="rank-badge">Hosp: 97 aislamientos (10.1%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:23%;background:var(--warn);"></div></div></div>
      </div>
    </div>
    <div class="card-sections">
      <div class="section">
        <div class="section-label sl-epidemio"><div class="sl-dot" style="background:var(--teal);"></div>Epidemiología Local</div>
        <div class="subsection-head">Resistencia — CE</div>
        <div class="resist-row"><span class="resist-drug">Cefazolina (no orina)</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Ceftazidima</span><span class="resist-pct" style="color:var(--danger);">96.8%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:96%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Ceftriaxona</span><span class="resist-pct" style="color:var(--danger);">38.9%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:39%;background:var(--warn);"></div></div></div>
 
        <div class="subsection-head" style="margin-top:10px;">Resistencia — Hosp</div>
        <div class="resist-row"><span class="resist-drug">Cefazolina (no orina)</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Ceftazidima</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Cefepima</span><span class="resist-pct" style="color:var(--danger);">76.1%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:76%;background:var(--danger);"></div></div></div>
 
        <div class="nota-tecnica" style="margin-top:12px;">
          <strong>⚠ Nota Técnica:</strong> Resistencia 100% a ceftazidima en hospitalización + resistencia a cefepima (76%) es patrón compatible con BLEE CTX-M de alto nivel y/o KPC emergente. Evaluar carbapenemasa mediante PCR cuando Meropenem MIC ≥ 0.5 µg/mL. Tigeciclina e imipenem mantienen actividad (88–90%).
        </div>
 
        <div class="subsection-head" style="margin-top:12px;">Mayor Sensibilidad</div>
        <div class="sens-row"><span class="sens-drug">Amicacina (CE)</span><span class="sens-pct">97.8%</span></div>
        <div class="sens-row"><span class="sens-drug">TMP/SMX (CE)</span><span class="sens-pct">100%</span></div>
        <div class="sens-row"><span class="sens-drug">Imipenem (Hosp)</span><span class="sens-pct">88.9%</span></div>
        <div class="sens-row"><span class="sens-drug">Meropenem (Hosp)</span><span class="sens-pct">88.5%</span></div>
      </div>
 
      <div class="section">
        <div class="section-label sl-terapia"><div class="sl-dot" style="background:var(--accent);"></div>Esquema Terapéutico</div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Infección moderada-grave (Hosp)</div>
          <div class="drug-box">
            <div class="drug-name">Meropenem</div>
            <div class="drug-dose"><strong>1 g IV c/8 h</strong> · infusión 30 min (estándar)<br>UCI o CIM elevado: <strong>2 g IV c/8 h</strong> en infusión extendida 3 h</div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Infección leve / CE (antibiograma previo)</div>
          <div class="drug-box">
            <div class="drug-name teal">Amicacina (monoterapia ITU)</div>
            <div class="drug-dose"><strong>15 mg/kg/día IV</strong> en dosis única diaria<br><em>Monitorear función renal; evitar en TFGe &lt; 30</em></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">✅ Terapia Dirigida</div>
          <div class="drug-box">
            <div class="drug-name green">Ertapenem (si BLEE, sin Pseudomonas)</div>
            <div class="drug-dose"><strong>1 g IV c/24 h</strong></div>
          </div>
        </div>
        <div class="drug-box" style="margin-bottom:14px;">
          <div class="drug-name warn">Tigeciclina (infección grave por XDR)</div>
          <div class="drug-dose"><strong>100 mg IV</strong> carga → <strong>50 mg IV c/12 h</strong><br><em>En monoterapia no recomendada para bacteriemia; considerar combinación</em></div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔄 Alternativas — Cepa KPC confirmada</div>
          <div class="drug-box">
            <div class="drug-name purple">Ceftazidima-Avibactam</div>
            <div class="drug-dose"><strong>2.5 g IV c/8 h</strong> · Referir a 3.er nivel si no disponible en cuadro básico</div>
          </div>
        </div>
      </div>
 
      <div class="section">
        <div class="section-label sl-proa"><div class="sl-dot" style="background:var(--accent2);"></div>Estrategia PROA</div>
 
        <div class="subsection-head">Criterios de Desescalamiento</div>
        <ul class="criteria-list">
          <li>Antibiograma confirma susceptibilidad a Ertapenem y ausencia de Pseudomonas → desescalar desde Meropenem</li>
          <li>Mejoría clínica ≥48–72 h (afebril, normalización PCR y procalcitonina)</li>
          <li>Si BLEE confirmada y sensible a TMP/SMX → considerar switch VO en ITU</li>
        </ul>
 
        <div class="subsection-head">Switch IV → VO</div>
        <ul class="criteria-list">
          <li>Hemodinámicamente estable ≥24 h</li>
          <li>Vía digestiva funcional</li>
          <li><strong>Opción VO (ITU-BLEE sensible):</strong> TMP/SMX <strong>800/160 mg c/12 h</strong></li>
          <li>Cuidado: 39% resistencia a ceftriaxona en CE → NO usar empíricamente</li>
        </ul>
 
        <div class="subsection-head">Duración del Tratamiento</div>
        <ul class="criteria-list">
          <li><strong>ITU complicada:</strong> 7–10 días</li>
          <li><strong>Neumonía nosocomial:</strong> 8 días (si buena respuesta)</li>
          <li><strong>Bacteriemia:</strong> 14 días mínimo</li>
          <li><strong>KPC / XDR:</strong> 14–21 días; valorar combinación con amicacina</li>
        </ul>
 
        <div class="duration-badge"><span class="days">7–21</span><span>días según cepa y foco</span></div>
      </div>
    </div>
  </div>
 
  <!-- ══════════════════════════════════════════════════════
       3. PSEUDOMONAS AERUGINOSA
  ══════════════════════════════════════════════════════ -->
  <div class="org-card" id="paeruginosa">
    <div class="card-header">
      <div class="card-header-left">
        <div class="org-name">Pseudomonas aeruginosa</div>
        <div class="org-tags">
          <span class="tag tag-gram-neg">Gram (−)</span>
          <span class="tag tag-mdr">MDR / XDR Frecuente</span>
          <span class="tag tag-alert">⚡ No Ertapenem</span>
          <span class="tag" style="background:rgba(57,211,195,0.1);color:var(--teal);border:1px solid rgba(57,211,195,0.2);">#8 CE · #3 Hosp</span>
        </div>
      </div>
      <div class="card-header-right">
        <div class="rank-badge">CE: 140 aislamientos (2.9%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:6%;background:var(--accent);"></div></div></div>
        <div class="rank-badge">Hosp: 93 aislamientos (9.7%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:22%;background:var(--warn);"></div></div></div>
      </div>
    </div>
    <div class="card-sections">
      <div class="section">
        <div class="section-label sl-epidemio"><div class="sl-dot" style="background:var(--teal);"></div>Epidemiología Local</div>
        <div class="subsection-head">Resistencia — CE</div>
        <div class="resist-row"><span class="resist-drug">Cefazolina</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Ceftriaxona</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Ciprofloxacino</span><span class="resist-pct" style="color:var(--warn);">33.3%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:33%;background:var(--warn);"></div></div></div>
 
        <div class="subsection-head" style="margin-top:10px;">Resistencia — Hosp</div>
        <div class="resist-row"><span class="resist-drug">Cefazolina</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Ceftriaxona</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Ciprofloxacino</span><span class="resist-pct" style="color:var(--danger);">43%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:43%;background:var(--warn);"></div></div></div>
 
        <div class="nota-tecnica" style="margin-top:12px;">
          <strong>⚠ Nota Técnica CRÍTICA:</strong> Pseudomonas es intrínsecamente resistente a Ertapenem. La resistencia a cefazolina/ceftriaxona es intrínseca (no BLEE). El ciprofloxacino conserva actividad parcial (&lt;57%) — NO usar como monoterapia en infecciones graves. Pip/Tazo mantiene 83% de sensibilidad en CE; evaluarlo como opción en infección de baja gravedad con antibiograma.
        </div>
 
        <div class="subsection-head" style="margin-top:12px;">Mayor Sensibilidad</div>
        <div class="sens-row"><span class="sens-drug">Pip/Tazo (CE)</span><span class="sens-pct">83.3%</span></div>
        <div class="sens-row"><span class="sens-drug">Gentamicina (CE)</span><span class="sens-pct">81.8%</span></div>
        <div class="sens-row"><span class="sens-drug">Meropenem (CE)</span><span class="sens-pct">80.8%</span></div>
        <div class="sens-row"><span class="sens-drug">Amicacina (Hosp)</span><span class="sens-pct">89.2%</span></div>
        <div class="sens-row"><span class="sens-drug">Ceftazidima (Hosp)</span><span class="sens-pct">72%</span></div>
      </div>
 
      <div class="section">
        <div class="section-label sl-terapia"><div class="sl-dot" style="background:var(--accent);"></div>Esquema Terapéutico</div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Infección grave / UCI (Hosp)</div>
          <div class="drug-box">
            <div class="drug-name">Meropenem</div>
            <div class="drug-dose"><strong>2 g IV c/8 h</strong> en infusión extendida <strong>3–4 h</strong> (PK/PD optimizado)<br><em>Combinar con amicacina en sepsis grave hasta antibiograma</em></div>
          </div>
        </div>
        <div class="drug-box" style="margin-bottom:14px;">
          <div class="drug-name">+ Amicacina (terapia combinada empírica)</div>
          <div class="drug-dose"><strong>15–20 mg/kg IV</strong> · dosis única diaria · monitorear niveles</div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Infección moderada (CE)</div>
          <div class="drug-box">
            <div class="drug-name teal">Piperacilina/Tazobactam</div>
            <div class="drug-dose"><strong>4.5 g IV c/6 h</strong> · infusión extendida 4 h si disponible</div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">✅ Terapia Dirigida (antibiograma)</div>
          <div class="drug-box">
            <div class="drug-name green">Ceftazidima (si sensible)</div>
            <div class="drug-dose"><strong>2 g IV c/8 h</strong> · infusión extendida 3 h en UCI</div>
          </div>
        </div>
        <div class="drug-box" style="margin-bottom:14px;">
          <div class="drug-name green">Ciprofloxacino VO (si susceptible, foco urinario)</div>
          <div class="drug-dose"><strong>500–750 mg VO c/12 h</strong> · solo si MIC confirmado sensible</div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔄 XDR — Consultar Infectología</div>
          <div class="drug-box">
            <div class="drug-name purple">Ceftolozano/Tazobactam</div>
            <div class="drug-dose"><strong>1.5 g IV c/8 h</strong> · 3.er nivel / referencia</div>
          </div>
        </div>
      </div>
 
      <div class="section">
        <div class="section-label sl-proa"><div class="sl-dot" style="background:var(--accent2);"></div>Estrategia PROA</div>
 
        <div class="subsection-head">Criterios de Desescalamiento</div>
        <ul class="criteria-list">
          <li>Antibiograma disponible → ajustar al antibiótico de menor espectro activo</li>
          <li>Si sensible a Pip/Tazo → desescalar desde Meropenem</li>
          <li>Mejoría clínica ≥72 h en neumonía asociada a VM</li>
          <li>Suspender aminoglucósido al día 3–5 si mejoría clínica (toxicidad renal)</li>
        </ul>
 
        <div class="subsection-head">Switch IV → VO</div>
        <ul class="criteria-list">
          <li>Muy limitado — Pseudomonas pocas opciones VO confiables</li>
          <li>Ciprofloxacino VO <strong>750 mg c/12 h</strong> solo si antibiograma confirma sensibilidad (MIC ≤ 0.5)</li>
          <li>Requiere hemodinamia estable y foco no endovascular</li>
        </ul>
 
        <div class="subsection-head">Duración del Tratamiento</div>
        <ul class="criteria-list">
          <li><strong>Neumonía nosocomial:</strong> 8 días (buena respuesta clínica)</li>
          <li><strong>Bacteriemia:</strong> 14 días mínimo</li>
          <li><strong>Infección de herida:</strong> 10–14 días</li>
          <li><strong>Osteomielitis:</strong> 6 semanas (valorar con Infectología)</li>
        </ul>
 
        <div class="duration-badge"><span class="days">8–14</span><span>días según foco</span></div>
      </div>
    </div>
  </div>
 
  <!-- ══════════════════════════════════════════════════════
       4. PROTEUS MIRABILIS
  ══════════════════════════════════════════════════════ -->
  <div class="org-card" id="pmirabilis">
    <div class="card-header">
      <div class="card-header-left">
        <div class="org-name">Proteus mirabilis</div>
        <div class="org-tags">
          <span class="tag tag-gram-neg">Gram (−)</span>
          <span class="tag tag-esbl">BLEE Presente</span>
          <span class="tag" style="background:rgba(57,211,195,0.1);color:var(--teal);border:1px solid rgba(57,211,195,0.2);">#4 CE · #10 Hosp</span>
        </div>
      </div>
      <div class="card-header-right">
        <div class="rank-badge">CE: 215 aislamientos (4.4%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:10%;background:var(--accent);"></div></div></div>
        <div class="rank-badge">Hosp: 31 aislamientos (3.2%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:7%;background:var(--warn);"></div></div></div>
      </div>
    </div>
    <div class="card-sections">
      <div class="section">
        <div class="section-label sl-epidemio"><div class="sl-dot" style="background:var(--teal);"></div>Epidemiología Local</div>
        <div class="subsection-head">Resistencia — CE</div>
        <div class="resist-row"><span class="resist-drug">Cefazolina (no orina)</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Tigeciclina</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Ciprofloxacino</span><span class="resist-pct" style="color:var(--warn);">56.1%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:56%;background:var(--warn);"></div></div></div>
 
        <div class="subsection-head" style="margin-top:10px;">Resistencia — Hosp</div>
        <div class="resist-row"><span class="resist-drug">Cefazolina (no orina)</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Cefazolina (oral)</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Cefepima</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
 
        <div class="nota-tecnica" style="margin-top:12px;">
          <strong>⚠ Nota Técnica:</strong> Proteus mirabilis es intrínsecamente resistente a Tigeciclina y Polimixinas. En esta institución muestra 100% resistencia a cefazolina + cefepima en hospitalización = patrón compatible con AmpC inducible o BLEE extendida. Los carbapenems y Pip/Tazo mantienen sensibilidad completa (100%).
        </div>
 
        <div class="subsection-head" style="margin-top:12px;">Mayor Sensibilidad</div>
        <div class="sens-row"><span class="sens-drug">Amicacina / Meropenem / Pip-Tazo (CE)</span><span class="sens-pct">100%</span></div>
        <div class="sens-row"><span class="sens-drug">Ertapenem / Meropenem / Pip-Tazo (Hosp)</span><span class="sens-pct">100%</span></div>
      </div>
 
      <div class="section">
        <div class="section-label sl-terapia"><div class="sl-dot" style="background:var(--accent);"></div>Esquema Terapéutico</div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Infección moderada</div>
          <div class="drug-box">
            <div class="drug-name teal">Piperacilina/Tazobactam</div>
            <div class="drug-dose"><strong>4.5 g IV c/6 h</strong></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Infección grave</div>
          <div class="drug-box">
            <div class="drug-name">Meropenem</div>
            <div class="drug-dose"><strong>1 g IV c/8 h</strong></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">✅ Terapia Dirigida</div>
          <div class="drug-box">
            <div class="drug-name green">Ertapenem (foco no-Pseudomonas)</div>
            <div class="drug-dose"><strong>1 g IV c/24 h</strong></div>
          </div>
        </div>
        <div class="drug-box" style="margin-bottom:14px;">
          <div class="drug-name green">Amicacina (ITU, CE)</div>
          <div class="drug-dose"><strong>15 mg/kg/día IV</strong> · dosis única diaria</div>
        </div>
 
        <div class="nota-tecnica">
          <strong>⚠ No usar:</strong> Tigeciclina (resistencia intrínseca en Proteus). Ciprofloxacino solo si MIC confirmado sensible (56% resistencia en CE).
        </div>
      </div>
 
      <div class="section">
        <div class="section-label sl-proa"><div class="sl-dot" style="background:var(--accent2);"></div>Estrategia PROA</div>
 
        <div class="subsection-head">Criterios de Desescalamiento</div>
        <ul class="criteria-list">
          <li>Desescalar Meropenem → Ertapenem si antibiograma confirma sensibilidad y no hay coinfección con Pseudomonas</li>
          <li>Mejoría clínica ≥48 h, PCR descendente</li>
        </ul>
 
        <div class="subsection-head">Switch IV → VO</div>
        <ul class="criteria-list">
          <li>Estabilidad hemodinámica + vía oral permeable</li>
          <li>Amoxicilina/Clavulanato <strong>875/125 mg VO c/8 h</strong> si sensible (confirmar en antibiograma)</li>
        </ul>
 
        <div class="subsection-head">Duración del Tratamiento</div>
        <ul class="criteria-list">
          <li><strong>ITU complicada:</strong> 7 días</li>
          <li><strong>Bacteriemia:</strong> 14 días</li>
          <li><strong>Infección de herida:</strong> 7–10 días</li>
        </ul>
 
        <div class="duration-badge"><span class="days">7–14</span><span>días según foco</span></div>
      </div>
    </div>
  </div>
 
  <!-- ══════════════════════════════════════════════════════
       5. ACINETOBACTER BAUMANNII
  ══════════════════════════════════════════════════════ -->
  <div class="org-card" id="abaumannii">
    <div class="card-header">
      <div class="card-header-left">
        <div class="org-name">Acinetobacter baumannii complex</div>
        <div class="org-tags">
          <span class="tag tag-gram-neg">Gram (−)</span>
          <span class="tag tag-mdr">XDR Frecuente</span>
          <span class="tag tag-alert">⚡ PRIORIDAD PROA</span>
          <span class="tag" style="background:rgba(57,211,195,0.1);color:var(--teal);border:1px solid rgba(57,211,195,0.2);">#7 Hosp (exclusivo)</span>
        </div>
      </div>
      <div class="card-header-right">
        <div class="rank-badge">Hosp: 35 aislamientos (3.6%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:8%;background:var(--warn);"></div></div></div>
        <div style="font-size:11px;color:var(--danger);">⚡ Solo presente en hospitalización</div>
      </div>
    </div>
    <div class="card-sections">
      <div class="section">
        <div class="section-label sl-epidemio"><div class="sl-dot" style="background:var(--teal);"></div>Epidemiología Local</div>
        <div class="subsection-head">Sin datos de antibiograma en tabla (n=35)</div>
        <p style="font-size:12px;color:var(--text-muted);line-height:1.6;margin-bottom:10px;">Los datos del HGRO no muestran antibiograma detallado para esta especie. Se aplican criterios IDSA 2022 + patrones epidemiológicos nacionales IMSS.</p>
 
        <div class="nota-tecnica">
          <strong>⚠ Nota Técnica:</strong> Acinetobacter baumannii complex es patógeno de alta alarma en UCI. En México, la prevalencia de cepas carbapenem-resistentes (CRAB) supera 60–70% en hospitales de 2.º-3.er nivel. Mecanismos predominantes: OXA-23, OXA-51, NDM. Se recomienda cultivo de vigilancia activa en UCI y aislamiento de contacto estricto desde el primer aislamiento.
        </div>
 
        <div class="subsection-head" style="margin-top:12px;">Factores de Riesgo Institucionales</div>
        <ul class="criteria-list">
          <li>Estancia en UCI ≥ 5 días</li>
          <li>Ventilación mecánica prolongada</li>
          <li>Catéter venoso central ≥ 7 días</li>
          <li>Carbapenems previos en los últimos 30 días</li>
        </ul>
      </div>
 
      <div class="section">
        <div class="section-label sl-terapia"><div class="sl-dot" style="background:var(--accent);"></div>Esquema Terapéutico</div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Cepa sensible a carbapenems</div>
          <div class="drug-box">
            <div class="drug-name">Meropenem</div>
            <div class="drug-dose"><strong>2 g IV c/8 h</strong> en infusión extendida <strong>3–4 h</strong></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Sospecha CRAB (XDR)</div>
          <div class="drug-box">
            <div class="drug-name warn">Sulbactam (como Ampicilina-Sulbactam)</div>
            <div class="drug-dose"><strong>9 g IV c/8 h</strong> (expresado como 6 g sulbactam/día) en infusión extendida 4 h</div>
          </div>
        </div>
        <div class="drug-box" style="margin-bottom:14px;">
          <div class="drug-name warn">+ Tigeciclina (terapia combinada)</div>
          <div class="drug-dose"><strong>100 mg IV</strong> carga → <strong>50 mg IV c/12 h</strong></div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔄 CRAB confirmado — Referir / Infectología</div>
          <div class="drug-box">
            <div class="drug-name purple">Sulbactam-Durlobactam</div>
            <div class="drug-dose"><strong>1 g / 1 g IV c/6 h</strong> · Disponibilidad 3.er nivel · Consultar PROA</div>
          </div>
        </div>
 
        <div class="nota-tecnica">
          <strong>⚠ Nota Técnica IDSA 2022:</strong> Para CRAB, la combinación de Sulbactam + Tigeciclina se recomienda sobre monoterapia con carbapenem. Colistina queda como última línea por toxicidad renal. Siempre obtener antibiograma completo con CIM antes de escalar.
        </div>
      </div>
 
      <div class="section">
        <div class="section-label sl-proa"><div class="sl-dot" style="background:var(--accent2);"></div>Estrategia PROA</div>
 
        <div class="subsection-head">Criterios de Desescalamiento</div>
        <ul class="criteria-list">
          <li>Identificación microbiológica + CIM disponible antes de escalar terapia</li>
          <li>Si sensible a carbapenems → monoterap. Meropenem infusión extendida</li>
          <li>Revisión PROA obligatoria al día 3 en todo aislamiento de UCI</li>
        </ul>
 
        <div class="subsection-head">Switch IV → VO</div>
        <ul class="criteria-list">
          <li><strong>No existe opción VO confiable para infecciones graves por CRAB</strong></li>
          <li>Completar tratamiento IV en todos los casos de bacteriemia o neumonía nosocomial</li>
        </ul>
 
        <div class="subsection-head">Duración del Tratamiento</div>
        <ul class="criteria-list">
          <li><strong>Neumonía asociada a VM:</strong> 8–14 días</li>
          <li><strong>Bacteriemia:</strong> 14 días mínimo</li>
          <li><strong>XDR/CRAB:</strong> 14–21 días; decisión individualizada con Infectología</li>
        </ul>
 
        <div class="duration-badge"><span class="days">8–21</span><span>días · evaluación diaria PROA</span></div>
      </div>
    </div>
  </div>
 
  <!-- GRAMPOSITIVOS -->
  <div class="section-divider"><hr/><span>Cocos Gram positivos</span><hr/></div>
 
  <!-- ══════════════════════════════════════════════════════
       6. STAPHYLOCOCCUS AUREUS
  ══════════════════════════════════════════════════════ -->
  <div class="org-card" id="saureus">
    <div class="card-header">
      <div class="card-header-left">
        <div class="org-name">Staphylococcus aureus</div>
        <div class="org-tags">
          <span class="tag tag-gram-pos">Gram (+)</span>
          <span class="tag tag-mrsa">MRSA ~59% CE / ~59% Hosp</span>
          <span class="tag" style="background:rgba(57,211,195,0.1);color:var(--teal);border:1px solid rgba(57,211,195,0.2);">#2 CE · #5 Hosp</span>
        </div>
      </div>
      <div class="card-header-right">
        <div class="rank-badge">CE: 530 aislamientos (10.8%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:25%;background:var(--accent);"></div></div></div>
        <div class="rank-badge">Hosp: 58 aislamientos (6%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:13%;background:var(--warn);"></div></div></div>
      </div>
    </div>
    <div class="card-sections">
      <div class="section">
        <div class="section-label sl-epidemio"><div class="sl-dot" style="background:var(--teal);"></div>Epidemiología Local</div>
        <div class="subsection-head">Resistencia — CE (n=530)</div>
        <div class="resist-row"><span class="resist-drug">Bencilpenicilina</span><span class="resist-pct" style="color:var(--danger);">92.5%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:92%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Oxacilina (= MRSA)</span><span class="resist-pct" style="color:var(--danger);">59.4%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:59%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Clindamicina</span><span class="resist-pct" style="color:var(--warn);">48.6%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:48%;background:var(--warn);"></div></div></div>
 
        <div class="subsection-head" style="margin-top:10px;">Resistencia — Hosp (n=58)</div>
        <div class="resist-row"><span class="resist-drug">Bencilpenicilina</span><span class="resist-pct" style="color:var(--danger);">98.3%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:98%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Oxacilina (= MRSA)</span><span class="resist-pct" style="color:var(--danger);">58.6%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:58%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Clindamicina</span><span class="resist-pct" style="color:var(--warn);">55.2%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:55%;background:var(--warn);"></div></div></div>
 
        <div class="nota-tecnica" style="margin-top:12px;">
          <strong>⚠ Nota Técnica:</strong> Prevalencia de MRSA ≈59% en ambas cohortes es MUY ALTA (promedio nacional IMSS ~40–50%). Esto implica que toda infección grave por S. aureus debe tratarse empíricamente como MRSA hasta tener resultado de oxacilina. Clindamicina NO es confiable (48–55% resistencia) — verificar fenotipo D (resistencia inducible) antes de usar.
        </div>
 
        <div class="subsection-head" style="margin-top:12px;">Mayor Sensibilidad</div>
        <div class="sens-row"><span class="sens-drug">Daptomicina (CE/Hosp)</span><span class="sens-pct">100%</span></div>
        <div class="sens-row"><span class="sens-drug">Nitrofurantoína (CE)</span><span class="sens-pct">100%</span></div>
        <div class="sens-row"><span class="sens-drug">Ceftaroline (Hosp)</span><span class="sens-pct">100%</span></div>
        <div class="sens-row"><span class="sens-drug">Rifampicina (CE)</span><span class="sens-pct">95.2%</span></div>
      </div>
 
      <div class="section">
        <div class="section-label sl-terapia"><div class="sl-dot" style="background:var(--accent);"></div>Esquema Terapéutico</div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Sospecha MRSA (bacteriemia, infección grave)</div>
          <div class="drug-box">
            <div class="drug-name">Vancomicina</div>
            <div class="drug-dose"><strong>25–30 mg/kg IV</strong> dosis de carga, luego ajustar por AUC/CIM (objetivo AUC 400–600 mg·h/L)<br><strong>Pauta habitual:</strong> 15–20 mg/kg c/8–12 h · ajustar por TFGe<br><em>Monitorear niveles valle si no se puede calcular AUC</em></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — MSSA (oxacilina sensible)</div>
          <div class="drug-box">
            <div class="drug-name green">Dicloxacilina (VO) / Nafcilina (IV)</div>
            <div class="drug-dose">Dicloxacilina <strong>500 mg VO c/6 h</strong> (inf. piel/tejidos blandos leve)<br>Nafcilina <strong>2 g IV c/4 h</strong> (infección grave MSSA confirmado)</div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">✅ Terapia Dirigida — MRSA confirmado</div>
          <div class="drug-box">
            <div class="drug-name">Vancomicina (continuar o ajustar)</div>
            <div class="drug-dose">Ajustar dosis para AUC/CIM ≥ 400 mg·h/L</div>
          </div>
        </div>
        <div class="drug-box" style="margin-bottom:14px;">
          <div class="drug-name">Daptomicina (bacteriemia / endocarditis)</div>
          <div class="drug-dose"><strong>6 mg/kg IV c/24 h</strong> (bacteriemia) · <strong>8–10 mg/kg IV c/24 h</strong> (endocarditis)<br><em>NO usar en neumonía (inactivado por surfactante)</em></div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔄 Alternativas (alergia, falla Vancomicina)</div>
          <div class="drug-box">
            <div class="drug-name purple">Linezolid</div>
            <div class="drug-dose"><strong>600 mg IV/VO c/12 h</strong> · máximo 14–28 días<br><em>Monitorear trombocitopenia y neuropatía periférica</em></div>
          </div>
        </div>
        <div class="drug-box" style="margin-bottom:14px;">
          <div class="drug-name purple">Ceftaroline (MRSA grave)</div>
          <div class="drug-dose"><strong>600 mg IV c/8 h</strong> · disponibilidad limitada</div>
        </div>
      </div>
 
      <div class="section">
        <div class="section-label sl-proa"><div class="sl-dot" style="background:var(--accent2);"></div>Estrategia PROA</div>
 
        <div class="subsection-head">Criterios de Desescalamiento</div>
        <ul class="criteria-list">
          <li>Resultado de oxacilina disponible (48–72 h): si MSSA → desescalar a Dicloxacilina/Nafcilina</li>
          <li>Desescalar de Vancomicina → Dicloxacilina IV si MSSA confirmado (reduce mortalidad)</li>
          <li>Mejoría clínica ≥72 h (afebril, PCR en descenso)</li>
        </ul>
 
        <div class="subsection-head">Switch IV → VO (MRSA)</div>
        <ul class="criteria-list">
          <li>Linezolid <strong>600 mg VO c/12 h</strong> (biodisponibilidad oral ~100%)</li>
          <li>TMP/SMX <strong>800/160 mg VO c/12 h</strong> si sensible (infecciones de piel/tejidos blandos)</li>
          <li>Condiciones: afebril ≥48 h, vía oral permeable, no bacteriemia activa</li>
        </ul>
 
        <div class="subsection-head">Switch IV → VO (MSSA)</div>
        <ul class="criteria-list">
          <li>Dicloxacilina <strong>500 mg VO c/6 h</strong> en ayunas</li>
        </ul>
 
        <div class="subsection-head">Duración del Tratamiento</div>
        <ul class="criteria-list">
          <li><strong>Inf. piel/tejidos blandos sin complicación:</strong> 5–7 días</li>
          <li><strong>Bacteriemia no complicada MRSA:</strong> 14 días (hemocultivos negativos)</li>
          <li><strong>Bacteriemia complicada / endocarditis:</strong> 4–6 semanas</li>
          <li><strong>Osteomielitis:</strong> 6 semanas</li>
        </ul>
 
        <div class="duration-badge"><span class="days">7–42</span><span>días según foco</span></div>
      </div>
    </div>
  </div>
 
  <!-- ══════════════════════════════════════════════════════
       7. S. EPIDERMIDIS
  ══════════════════════════════════════════════════════ -->
  <div class="org-card" id="sepidermidis">
    <div class="card-header">
      <div class="card-header-left">
        <div class="org-name">Staphylococcus epidermidis</div>
        <div class="org-tags">
          <span class="tag tag-gram-pos">Gram (+)</span>
          <span class="tag tag-mrsa">SCN-MR ~97–100% Hosp</span>
          <span class="tag" style="background:rgba(57,211,195,0.1);color:var(--teal);border:1px solid rgba(57,211,195,0.2);">#6 CE · #6 Hosp</span>
        </div>
      </div>
      <div class="card-header-right">
        <div class="rank-badge">CE: 185 aislamientos (3.8%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:8%;background:var(--accent);"></div></div></div>
        <div class="rank-badge">Hosp: 41 aislamientos (4.3%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:9%;background:var(--warn);"></div></div></div>
      </div>
    </div>
    <div class="card-sections">
      <div class="section">
        <div class="section-label sl-epidemio"><div class="sl-dot" style="background:var(--teal);"></div>Epidemiología Local</div>
        <div class="subsection-head">Resistencia — CE (n=185)</div>
        <div class="resist-row"><span class="resist-drug">Bencilpenicilina</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Oxacilina (= SCN-MR)</span><span class="resist-pct" style="color:var(--danger);">97.3%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:97%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Clindamicina</span><span class="resist-pct" style="color:var(--danger);">91.4%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:91%;background:var(--danger);"></div></div></div>
 
        <div class="subsection-head" style="margin-top:10px;">Resistencia — Hosp (n=41)</div>
        <div class="resist-row"><span class="resist-drug">Bencilpenicilina</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Eritromicina</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Oxacilina</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
 
        <div class="nota-tecnica" style="margin-top:12px;">
          <strong>⚠ Nota Técnica:</strong> Oxacilina 100% resistente en hospitalización = SCN-MR absoluto. Primera consideración clínica: distinguir infección verdadera de contaminación de hemocultivo (≥2 hemocultivos positivos, clínica compatible, material protésico). Si infección confirmada con catéter/implante, requiere retiro del material más Vancomicina sistémica.
        </div>
 
        <div class="subsection-head" style="margin-top:12px;">Mayor Sensibilidad</div>
        <div class="sens-row"><span class="sens-drug">Daptomicina / Nitrofurantoína (CE)</span><span class="sens-pct">100%</span></div>
        <div class="sens-row"><span class="sens-drug">TMP/SMX (CE)</span><span class="sens-pct">78.4%</span></div>
        <div class="sens-row"><span class="sens-drug">Vancomicina (Hosp)</span><span class="sens-pct">100%</span></div>
      </div>
 
      <div class="section">
        <div class="section-label sl-terapia"><div class="sl-dot" style="background:var(--accent);"></div>Esquema Terapéutico</div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Sospecha bacteriemia por catéter / SCN</div>
          <div class="drug-box">
            <div class="drug-name">Vancomicina</div>
            <div class="drug-dose"><strong>15–20 mg/kg IV c/8–12 h</strong> (ajustar por TFGe)<br>Objetivo AUC 400–600 mg·h/L</div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">✅ Terapia Dirigida — SCN-MR confirmado</div>
          <div class="drug-box">
            <div class="drug-name green">Vancomicina (continuar)</div>
            <div class="drug-dose">+ retirar catéter si bacteriemia asociada a CVC</div>
          </div>
        </div>
        <div class="drug-box" style="margin-bottom:14px;">
          <div class="drug-name green">Daptomicina (alternativa)</div>
          <div class="drug-dose"><strong>6 mg/kg IV c/24 h</strong></div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔄 Alternativas</div>
          <div class="drug-box">
            <div class="drug-name purple">Linezolid</div>
            <div class="drug-dose"><strong>600 mg IV/VO c/12 h</strong></div>
          </div>
        </div>
      </div>
 
      <div class="section">
        <div class="section-label sl-proa"><div class="sl-dot" style="background:var(--accent2);"></div>Estrategia PROA</div>
 
        <div class="subsection-head">Criterios de Desescalamiento</div>
        <ul class="criteria-list">
          <li>Confirmar que no es contaminante antes de iniciar antibiótico (2 hemocultivos positivos)</li>
          <li>Retirar CVC como intervención terapéutica primaria</li>
          <li>Si sensible a TMP/SMX (78.4% CE) → switch VO en infecciones de baja complejidad</li>
        </ul>
 
        <div class="subsection-head">Switch IV → VO</div>
        <ul class="criteria-list">
          <li>Linezolid <strong>600 mg VO c/12 h</strong> (bio ~100%)</li>
          <li>TMP/SMX <strong>800/160 mg VO c/12 h</strong> si sensible</li>
        </ul>
 
        <div class="subsection-head">Duración</div>
        <ul class="criteria-list">
          <li><strong>Bacteriemia por catéter (retirado):</strong> 5–7 días</li>
          <li><strong>Bacteriemia sin catéter identificable:</strong> 14 días</li>
          <li><strong>Infección prótesis:</strong> 6 semanas (con cirugía)</li>
        </ul>
 
        <div class="duration-badge"><span class="days">5–14</span><span>días según material</span></div>
      </div>
    </div>
  </div>
 
  <!-- ══════════════════════════════════════════════════════
       8. S. HAEMOLYTICUS
  ══════════════════════════════════════════════════════ -->
  <div class="org-card" id="shaemolyticus">
    <div class="card-header">
      <div class="card-header-left">
        <div class="org-name">Staphylococcus haemolyticus</div>
        <div class="org-tags">
          <span class="tag tag-gram-pos">Gram (+)</span>
          <span class="tag tag-mrsa">SCN-MR 100% Hosp</span>
          <span class="tag tag-alert">Resistencia Multi-fármaco</span>
          <span class="tag" style="background:rgba(57,211,195,0.1);color:var(--teal);border:1px solid rgba(57,211,195,0.2);">#10 Hosp</span>
        </div>
      </div>
      <div class="card-header-right">
        <div class="rank-badge">CE: ~80 aislamientos estimado<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:4%;background:var(--accent);"></div></div></div>
        <div class="rank-badge">Hosp: 32 aislamientos (3.3%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:7%;background:var(--warn);"></div></div></div>
      </div>
    </div>
    <div class="card-sections">
      <div class="section">
        <div class="section-label sl-epidemio"><div class="sl-dot" style="background:var(--teal);"></div>Epidemiología Local</div>
        <div class="subsection-head">Resistencia — CE</div>
        <div class="resist-row"><span class="resist-drug">Bencilpenicilina</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Oxacilina</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Eritromicina</span><span class="resist-pct" style="color:var(--danger);">68.8%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:68%;background:var(--danger);"></div></div></div>
 
        <div class="subsection-head" style="margin-top:10px;">Resistencia — Hosp</div>
        <div class="resist-row"><span class="resist-drug">Bencilpenicilina</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Ciprofloxacino</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Clindamicina</span><span class="resist-pct" style="color:var(--danger);">100%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:100%;background:var(--danger);"></div></div></div>
 
        <div class="nota-tecnica" style="margin-top:12px;">
          <strong>⚠ Nota Técnica:</strong> S. haemolyticus es el SCN con el perfil de resistencia más amplio. En hospitalización: resistencia 100% a oxacilina, ciprofloxacino Y clindamicina — opciones terapéuticas muy limitadas. Daptomicina y Vancomicina mantienen actividad completa (100%). Considerar siempre contaminación vs infección real.
        </div>
 
        <div class="subsection-head" style="margin-top:12px;">Mayor Sensibilidad</div>
        <div class="sens-row"><span class="sens-drug">Nitrofurantoína / Daptomicina / Vancomicina (CE)</span><span class="sens-pct">100%</span></div>
        <div class="sens-row"><span class="sens-drug">Daptomicina / Nitrofurantoína (Hosp)</span><span class="sens-pct">100%</span></div>
        <div class="sens-row"><span class="sens-drug">Tetraciclina (Hosp)</span><span class="sens-pct">96.9%</span></div>
      </div>
 
      <div class="section">
        <div class="section-label sl-terapia"><div class="sl-dot" style="background:var(--accent);"></div>Esquema Terapéutico</div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Bacteriemia / infección grave</div>
          <div class="drug-box">
            <div class="drug-name">Vancomicina</div>
            <div class="drug-dose"><strong>15–20 mg/kg IV c/8–12 h</strong></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">✅ Terapia Dirigida — SCN-MR confirmado</div>
          <div class="drug-box">
            <div class="drug-name green">Vancomicina o Daptomicina</div>
            <div class="drug-dose">Daptomicina: <strong>6–8 mg/kg IV c/24 h</strong></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔄 Alternativas limitadas</div>
          <div class="drug-box">
            <div class="drug-name purple">Linezolid</div>
            <div class="drug-dose"><strong>600 mg IV/VO c/12 h</strong></div>
          </div>
        </div>
 
        <div class="nota-tecnica">
          <strong>⚠ Nota Técnica CRÍTICA:</strong> NO usar ciprofloxacino (100% resistente en Hosp), clindamicina (100% resistente) ni macrólidos. Tetraciclina mantiene 96.9% sensibilidad — usar solo como terapia de rescate en infecciones menores (no bacteriemia). Daptomicina es la alternativa de elección cuando se sospecha falla a Vancomicina.
        </div>
      </div>
 
      <div class="section">
        <div class="section-label sl-proa"><div class="sl-dot" style="background:var(--accent2);"></div>Estrategia PROA</div>
 
        <div class="subsection-head">Criterios de Desescalamiento</div>
        <ul class="criteria-list">
          <li>Confirmar infección verdadera (≥2 hemocultivos) antes de cualquier antibiótico</li>
          <li>Retiro de dispositivo implantado si bacteriemia asociada</li>
          <li>No existe opción de desescalamiento a betalactámico (resistencia 100%)</li>
        </ul>
 
        <div class="subsection-head">Switch IV → VO</div>
        <ul class="criteria-list">
          <li>Linezolid <strong>600 mg VO c/12 h</strong></li>
          <li>Doxiciclina <strong>100 mg VO c/12 h</strong> (si sensible en antibiograma, infecciones menores)</li>
        </ul>
 
        <div class="subsection-head">Duración</div>
        <ul class="criteria-list">
          <li><strong>Bacteriemia por catéter (retirado):</strong> 5–7 días</li>
          <li><strong>Bacteriemia sin foco identificable:</strong> 14 días</li>
        </ul>
 
        <div class="duration-badge"><span class="days">5–14</span><span>días</span></div>
      </div>
    </div>
  </div>
 
  <!-- ══════════════════════════════════════════════════════
       9. ENTEROCOCCUS FAECALIS
  ══════════════════════════════════════════════════════ -->
  <div class="org-card" id="efaecalis">
    <div class="card-header">
      <div class="card-header-left">
        <div class="org-name">Enterococcus faecalis</div>
        <div class="org-tags">
          <span class="tag tag-gram-pos">Gram (+)</span>
          <span class="tag" style="background:rgba(57,211,195,0.1);color:var(--teal);border:1px solid rgba(57,211,195,0.2);">Ampicilina Sensible ~89%</span>
          <span class="tag" style="background:rgba(210,153,34,0.1);color:var(--warn);border:1px solid rgba(210,153,34,0.2);">VRE Vigilancia</span>
          <span class="tag" style="background:rgba(57,211,195,0.1);color:var(--teal);border:1px solid rgba(57,211,195,0.2);">#5 CE · #4 Hosp</span>
        </div>
      </div>
      <div class="card-header-right">
        <div class="rank-badge">CE: 190 aislamientos (3.9%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:9%;background:var(--accent);"></div></div></div>
        <div class="rank-badge">Hosp: 61 aislamientos (6.4%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:14%;background:var(--warn);"></div></div></div>
      </div>
    </div>
    <div class="card-sections">
      <div class="section">
        <div class="section-label sl-epidemio"><div class="sl-dot" style="background:var(--teal);"></div>Epidemiología Local</div>
        <div class="subsection-head">Resistencia — CE (n=190)</div>
        <div class="resist-row"><span class="resist-drug">Tetraciclina</span><span class="resist-pct" style="color:var(--danger);">78.9%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:78%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Gentamicina AN sinergia</span><span class="resist-pct" style="color:var(--warn);">55.3%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:55%;background:var(--warn);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Eritromicina</span><span class="resist-pct" style="color:var(--warn);">44.7%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:44%;background:var(--warn);"></div></div></div>
 
        <div class="subsection-head" style="margin-top:10px;">Resistencia — Hosp (n=61)</div>
        <div class="resist-row"><span class="resist-drug">Eritromicina</span><span class="resist-pct" style="color:var(--danger);">80.3%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:80%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Tetraciclina</span><span class="resist-pct" style="color:var(--danger);">75.4%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:75%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Gentamicina AN sinergia</span><span class="resist-pct" style="color:var(--danger);">72.1%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:72%;background:var(--danger);"></div></div></div>
 
        <div class="nota-tecnica" style="margin-top:12px;">
          <strong>⚠ Nota Técnica:</strong> Resistencia a Gentamicina de alto nivel (sinergia) del 72% en hospitalización implica que la combinación Ampicilina + Gentamicina pierde la sinergia bactericida en la mayoría de casos. Para endocarditis, evaluar combinación Ampicilina + Ceftriaxona (doble β-lactámico) que no requiere gentamicina de alto nivel. Vigilar VRE mediante tamizaje activo en UCI.
        </div>
 
        <div class="subsection-head" style="margin-top:12px;">Mayor Sensibilidad</div>
        <div class="sens-row"><span class="sens-drug">Nitrofurantoína (CE/Hosp)</span><span class="sens-pct">97.4% / 96.7%</span></div>
        <div class="sens-row"><span class="sens-drug">Ampicilina (CE/Hosp)</span><span class="sens-pct">89.5% / 88.5%</span></div>
        <div class="sens-row"><span class="sens-drug">Bencilpenicilina (CE)</span><span class="sens-pct">86.8%</span></div>
        <div class="sens-row"><span class="sens-drug">Linezolid (Hosp)</span><span class="sens-pct">80.3%</span></div>
      </div>
 
      <div class="section">
        <div class="section-label sl-terapia"><div class="sl-dot" style="background:var(--accent);"></div>Esquema Terapéutico</div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — ITU / Infección leve</div>
          <div class="drug-box">
            <div class="drug-name teal">Nitrofurantoína</div>
            <div class="drug-dose"><strong>100 mg VO c/6 h × 7 días</strong> (macrocristales)<br><em>Solo para ITU baja; no usar en pielonefritis ni bacteriemia</em></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Infección grave / bacteriemia</div>
          <div class="drug-box">
            <div class="drug-name">Ampicilina</div>
            <div class="drug-dose"><strong>2 g IV c/4–6 h</strong></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">✅ Terapia Dirigida — Endocarditis</div>
          <div class="drug-box">
            <div class="drug-name green">Ampicilina + Ceftriaxona</div>
            <div class="drug-dose">Ampicilina <strong>2 g IV c/4 h</strong> + Ceftriaxona <strong>2 g IV c/12 h</strong><br><em>Doble β-lactámico — NO requiere gentamicina (alta resistencia de sinergia)</em></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔄 Alternativas — VRE / Alergia Ampicilina</div>
          <div class="drug-box">
            <div class="drug-name purple">Linezolid</div>
            <div class="drug-dose"><strong>600 mg IV/VO c/12 h</strong></div>
          </div>
        </div>
        <div class="drug-box" style="margin-bottom:14px;">
          <div class="drug-name purple">Daptomicina (bacteriemia VRE)</div>
          <div class="drug-dose"><strong>6 mg/kg IV c/24 h</strong></div>
        </div>
      </div>
 
      <div class="section">
        <div class="section-label sl-proa"><div class="sl-dot" style="background:var(--accent2);"></div>Estrategia PROA</div>
 
        <div class="subsection-head">Criterios de Desescalamiento</div>
        <ul class="criteria-list">
          <li>Confirmar sensibilidad a Ampicilina en antibiograma (~88–89%)</li>
          <li>Si ITU y sensible a Nitrofurantoína → Nitrofurantoína VO (switch o monoterapia)</li>
          <li>Desescalar de glucopéptidos si no hay VRE documentado</li>
        </ul>
 
        <div class="subsection-head">Switch IV → VO</div>
        <ul class="criteria-list">
          <li>Amoxicilina <strong>500 mg VO c/8 h</strong> (si sensible, infección de baja complejidad)</li>
          <li>Linezolid <strong>600 mg VO c/12 h</strong> (equivalencia 1:1 IV/VO)</li>
          <li>Condiciones: afebril ≥48 h, foco controlado, no bacteriemia activa</li>
        </ul>
 
        <div class="subsection-head">Duración</div>
        <ul class="criteria-list">
          <li><strong>ITU no complicada:</strong> 7 días</li>
          <li><strong>Bacteriemia:</strong> 14 días</li>
          <li><strong>Endocarditis (válvula nativa):</strong> 6 semanas (Amp + Cef)</li>
        </ul>
 
        <div class="duration-badge"><span class="days">7–42</span><span>días según foco</span></div>
      </div>
    </div>
  </div>
 
  <!-- ══════════════════════════════════════════════════════
       10. STREPTOCOCCUS AGALACTIAE
  ══════════════════════════════════════════════════════ -->
  <div class="org-card" id="sagalactiae">
    <div class="card-header">
      <div class="card-header-left">
        <div class="org-name">Streptococcus agalactiae (GBS)</div>
        <div class="org-tags">
          <span class="tag tag-gram-pos">Gram (+)</span>
          <span class="tag" style="background:rgba(63,185,80,0.1);color:var(--accent2);border:1px solid rgba(63,185,80,0.2);">Ampicilina Sensible 100%</span>
          <span class="tag" style="background:rgba(57,211,195,0.1);color:var(--teal);border:1px solid rgba(57,211,195,0.2);">#9 CE</span>
        </div>
      </div>
      <div class="card-header-right">
        <div class="rank-badge">CE: 130 aislamientos (2.7%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:6%;background:var(--accent);"></div></div></div>
        <div style="font-size:11px;color:var(--text-muted);">Hosp: sin datos suficientes</div>
      </div>
    </div>
    <div class="card-sections">
      <div class="section">
        <div class="section-label sl-epidemio"><div class="sl-dot" style="background:var(--teal);"></div>Epidemiología Local</div>
        <div class="subsection-head">Resistencia — CE (n=95–130)</div>
        <div class="resist-row"><span class="resist-drug">Tetraciclina</span><span class="resist-pct" style="color:var(--warn);">57.9%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:57%;background:var(--warn);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Eritromicina</span><span class="resist-pct" style="color:var(--accent);">9.1%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:9%;background:var(--accent);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Levofloxacino</span><span class="resist-pct" style="color:var(--accent);">3.8%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:4%;background:var(--accent);"></div></div></div>
 
        <div class="subsection-head" style="margin-top:10px;">Mayor Sensibilidad</div>
        <div class="sens-row"><span class="sens-drug">Ampicilina / Bencilpenicilina / Linezolid</span><span class="sens-pct">100%</span></div>
 
        <div class="nota-tecnica" style="margin-top:12px;">
          <strong>✅ Perfil favorable:</strong> S. agalactiae mantiene sensibilidad 100% a betalactámicos en este hospital. Sin resistencia a penicilinas documentada. Alta relevancia en ginecología/obstetricia (colonización vaginal, sepsis neonatal, ITU en embarazo). El 58% de resistencia a tetraciclinas lo excluye completamente de opciones terapéuticas.
        </div>
      </div>
 
      <div class="section">
        <div class="section-label sl-terapia"><div class="sl-dot" style="background:var(--accent);"></div>Esquema Terapéutico</div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Primera línea — Infección activa</div>
          <div class="drug-box">
            <div class="drug-name green">Ampicilina</div>
            <div class="drug-dose"><strong>2 g IV c/4–6 h</strong> (infección grave / bacteriemia)<br><strong>500 mg VO c/8 h</strong> (infección leve / ITU)</div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Profilaxis intraparto (según protocolo obstétrico)</div>
          <div class="drug-box">
            <div class="drug-name green">Bencilpenicilina sódica</div>
            <div class="drug-dose"><strong>5 millones UI IV</strong> dosis inicial → <strong>2.5 millones UI IV c/4 h</strong> hasta parto</div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔄 Alternativas (alergia penicilina leve)</div>
          <div class="drug-box">
            <div class="drug-name teal">Cefazolina</div>
            <div class="drug-dose"><strong>2 g IV</strong> dosis inicial → <strong>1 g IV c/8 h</strong></div>
          </div>
        </div>
        <div class="drug-box" style="margin-bottom:14px;">
          <div class="drug-name purple">Clindamicina (alergia grave penicilina)</div>
          <div class="drug-dose"><strong>900 mg IV c/8 h</strong> · solo si sensibilidad confirmada por antibiograma (eritromicina 9% R)</div>
        </div>
      </div>
 
      <div class="section">
        <div class="section-label sl-proa"><div class="sl-dot" style="background:var(--accent2);"></div>Estrategia PROA</div>
 
        <div class="subsection-head">Criterios de Desescalamiento</div>
        <ul class="criteria-list">
          <li>Si iniciado con antibiótico de amplio espectro empírico → desescalar a Ampicilina (sensibilidad 100%)</li>
          <li>Mejoría clínica ≥48 h</li>
        </ul>
 
        <div class="subsection-head">Switch IV → VO</div>
        <ul class="criteria-list">
          <li>Amoxicilina <strong>500 mg VO c/8 h</strong></li>
          <li>Condiciones: afebril ≥24 h, tolerancia oral, no bacteriemia activa</li>
        </ul>
 
        <div class="subsection-head">Duración</div>
        <ul class="criteria-list">
          <li><strong>ITU:</strong> 7 días</li>
          <li><strong>Bacteriemia sin foco:</strong> 14 días</li>
          <li><strong>Meningitis neonatal:</strong> 14–21 días (con Infectología Pediátrica)</li>
        </ul>
 
        <div class="duration-badge"><span class="days">7–21</span><span>días según foco</span></div>
      </div>
    </div>
  </div>
 
  <!-- HONGOS -->
  <div class="section-divider"><hr/><span>Hongos — Candidiasis Invasiva</span><hr/></div>
 
  <!-- ══════════════════════════════════════════════════════
       11. CANDIDA ALBICANS
  ══════════════════════════════════════════════════════ -->
  <div class="org-card" id="calbicans">
    <div class="card-header">
      <div class="card-header-left">
        <div class="org-name">Candida albicans</div>
        <div class="org-tags">
          <span class="tag tag-fungal">Hongo</span>
          <span class="tag tag-mdr">Fluconazol R 64–77%</span>
          <span class="tag tag-alert">⚡ No azoles empírico</span>
          <span class="tag" style="background:rgba(57,211,195,0.1);color:var(--teal);border:1px solid rgba(57,211,195,0.2);">#7 CE · #9 Hosp</span>
        </div>
      </div>
      <div class="card-header-right">
        <div class="rank-badge">CE: 155 aislamientos (3.2%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:7%;background:var(--accent);"></div></div></div>
        <div class="rank-badge">Hosp: 31 aislamientos (3.2%)<div class="rank-bar-bg"><div class="rank-bar-fill" style="width:7%;background:var(--warn);"></div></div></div>
      </div>
    </div>
    <div class="card-sections">
      <div class="section">
        <div class="section-label sl-epidemio"><div class="sl-dot" style="background:var(--teal);"></div>Epidemiología Local</div>
        <div class="subsection-head">Resistencia — CE (n=155)</div>
        <div class="resist-row"><span class="resist-drug">Fluconazol</span><span class="resist-pct" style="color:var(--danger);">64.5%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:64%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Micafungina</span><span class="resist-pct" style="color:var(--warn);">41.9%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:41%;background:var(--warn);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Voriconazol</span><span class="resist-pct" style="color:var(--warn);">36.7%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:36%;background:var(--warn);"></div></div></div>
 
        <div class="subsection-head" style="margin-top:10px;">Resistencia — Hosp (n=30)</div>
        <div class="resist-row"><span class="resist-drug">Fluconazol</span><span class="resist-pct" style="color:var(--danger);">76.7%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:76%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Caspofungina</span><span class="resist-pct" style="color:var(--danger);">50%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:50%;background:var(--danger);"></div></div></div>
        <div class="resist-row"><span class="resist-drug">Micafungina</span><span class="resist-pct" style="color:var(--danger);">50%</span><div class="resist-bar"><div class="resist-bar-fill" style="width:50%;background:var(--danger);"></div></div></div>
 
        <div class="nota-tecnica" style="margin-top:12px;">
          <strong>⚠ Nota Técnica CRÍTICA (Regla de Oro Biota Local):</strong> Los datos del HGRO muestran resistencia a Fluconazol del 64.5–76.7% y resistencia a equinocandinas (Caspofungina + Micafungina) del 41.9–50%. Esto <strong>contradice directamente las guías IDSA 2016 que recomiendan equinocandinas como primera línea en candidemia</strong>. Aplicando la Regla de Oro de Biota Local: se prioriza Anfotericina B liposomal como empírico de elección. Estos perfiles atípicos deben confirmarse con pruebas de sensibilidad CIM antes de mantener cualquier esquema. Verificar metodología del reporte de resistencia a equinocandinas (posibles valores S-DD mal clasificados).
        </div>
 
        <div class="subsection-head" style="margin-top:12px;">Mayor Sensibilidad</div>
        <div class="sens-row"><span class="sens-drug">Flucitosina (CE)</span><span class="sens-pct">100%</span></div>
        <div class="sens-row"><span class="sens-drug">Anfotericina B (CE)</span><span class="sens-pct">58.6%</span></div>
        <div class="sens-row"><span class="sens-drug">Flucitosina (Hosp)</span><span class="sens-pct">68.4%</span></div>
        <div class="sens-row"><span class="sens-drug">Anfotericina B (Hosp)</span><span class="sens-pct">53.3%</span></div>
      </div>
 
      <div class="section">
        <div class="section-label sl-terapia"><div class="sl-dot" style="background:var(--accent);"></div>Esquema Terapéutico</div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Candidemia / Candidiasis invasiva (Hosp)</div>
          <div class="drug-box">
            <div class="drug-name purple">Anfotericina B liposomal</div>
            <div class="drug-dose"><strong>3–5 mg/kg IV c/24 h</strong><br><em>Primera línea institucional dada alta resistencia local a azoles y equinocandinas</em></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔵 Empírica — Candidiasis mucocutánea / vulvovaginal (CE)</div>
          <div class="drug-box">
            <div class="drug-name teal">Clotrimazol tópico</div>
            <div class="drug-dose"><strong>100 mg óvulo vaginal × 7 días</strong> o <strong>500 mg dosis única</strong><br><em>Evitar Fluconazol sistémico hasta tener sensibilidad confirmada</em></div>
          </div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">✅ Terapia Dirigida (antifungigrama disponible)</div>
          <div class="drug-box">
            <div class="drug-name green">Fluconazol (solo si CIM ≤ 2 µg/mL)</div>
            <div class="drug-dose"><strong>400 mg IV/VO c/24 h</strong> día 1 → <strong>200–400 mg c/24 h</strong><br><em>Usar ÚNICAMENTE con sensibilidad confirmada; resistencia 64–77% localmente</em></div>
          </div>
        </div>
        <div class="drug-box" style="margin-bottom:14px;">
          <div class="drug-name green">Caspofungina (si sensible por CIM)</div>
          <div class="drug-dose"><strong>70 mg IV</strong> carga → <strong>50 mg IV c/24 h</strong></div>
        </div>
 
        <div class="drug-block">
          <div class="drug-tier">🔄 Alternativas</div>
          <div class="drug-box">
            <div class="drug-name purple">Flucitosina (siempre en combinación)</div>
            <div class="drug-dose"><strong>25 mg/kg VO c/6 h</strong> · solo combinada (Anfo B + Flucitosina en meningitis fúngica)</div>
          </div>
        </div>
      </div>
 
      <div class="section">
        <div class="section-label sl-proa"><div class="sl-dot" style="background:var(--accent2);"></div>Estrategia PROA</div>
 
        <div class="subsection-head">Criterios de Desescalamiento</div>
        <ul class="criteria-list">
          <li>Antifungigrama con CIM disponible → ajustar a agente de menor toxicidad si sensible</li>
          <li>Retirar CVC si candidemia (dentro de las primeras 24–48 h)</li>
          <li>Hemocultivos de control negativos × 2 días consecutivos</li>
          <li>Desescalar a Fluconazol VO solo si CIM ≤ 2 µg/mL confirmado</li>
        </ul>
 
        <div class="subsection-head">Switch IV → VO</div>
        <ul class="criteria-list">
          <li>Fluconazol <strong>400 mg VO c/24 h</strong> (solo si sensible confirmado)</li>
          <li>Condiciones: hemodinámicamente estable, hemocultivos negativos ≥ 5 días</li>
          <li>Completar al menos 14 días IV antes de switch en candidemia</li>
        </ul>
 
        <div class="subsection-head">Duración del Tratamiento</div>
        <ul class="criteria-list">
          <li><strong>Candidiasis mucocutánea:</strong> 7–14 días</li>
          <li><strong>Candidemia sin complicación:</strong> 14 días desde hemocultivo negativo</li>
          <li><strong>Candidiasis intraabdominal:</strong> 14 días post control quirúrgico</li>
          <li><strong>Endoftalmitis:</strong> 4–6 semanas (con Oftalmología)</li>
        </ul>
 
        <div class="duration-badge"><span class="days">14+</span><span>días desde hemocultivo negativo</span></div>
 
        <div class="nota-tecnica" style="margin-top:12px;">
          <strong>⚠ Acción PROA prioritaria:</strong> La resistencia a equinocandinas del 41–50% en C. albicans es inusual a nivel mundial. Se recomienda revisar la metodología de susceptibilidad con el laboratorio de microbiología (puntos de corte EUCAST vs CLSI, técnica de microdilución) y activar investigación epidemiológica para descartar brotes o error sistemático.
        </div>
      </div>
    </div>
  </div>
 
  <!-- RESUMEN EJECUTIVO PROA -->
  <div class="section-divider"><hr/><span>Resumen Ejecutivo PROA — Alarmas Institucionales</span><hr/></div>
 
  <div style="background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:24px;margin-bottom:28px;">
    <div style="font-size:13px;font-weight:600;color:var(--text);margin-bottom:16px;display:flex;align-items:center;gap:8px;">
      🚨 Patrones de Resistencia Críticos — Acciones PROA Inmediatas
    </div>
    <div style="display:grid;grid-template-columns:1fr 1fr;gap:16px;">
 
      <div style="background:rgba(248,81,73,0.06);border:1px solid rgba(248,81,73,0.2);border-radius:8px;padding:14px;">
        <div style="font-size:11px;font-weight:700;color:var(--danger);text-transform:uppercase;letter-spacing:0.08em;margin-bottom:8px;">🔴 Alarma Máxima</div>
        <ul class="criteria-list">
          <li>MRSA ~59% en ambas cohortes → Vancomicina empírica en toda infección grave por S. aureus</li>
          <li>SCN-MR 97–100% en hospitalización → No usar oxacilina/cefazolina en SCN hospitalario</li>
          <li>BLEE >88% E. coli hospitalaria → No usar cefalosporinas de 3.ª gen. empíricamente en Hosp</li>
          <li>Klebsiella 100% R a ceftazidima en Hosp → Carbapenems de entrada en infección grave</li>
          <li>Fluconazol R 64–77% C. albicans → No usar Fluconazol empírico en candidemia</li>
        </ul>
      </div>
 
      <div style="background:rgba(210,153,34,0.06);border:1px solid rgba(210,153,34,0.2);border-radius:8px;padding:14px;">
        <div style="font-size:11px;font-weight:700;color:var(--warn);text-transform:uppercase;letter-spacing:0.08em;margin-bottom:8px;">🟡 Vigilancia Activa</div>
        <ul class="criteria-list">
          <li>Acinetobacter baumannii SOLO en hospitalización → Protocolo CRAB en UCI</li>
          <li>Equinocandinas R 41–50% en C. albicans → Verificar metodología de laboratorio + investigación epidemiológica</li>
          <li>Gentamicina sinergia R 72% E. faecalis → Usar Ampicilina + Ceftriaxona en endocarditis</li>
          <li>Pseudomonas ciprofloxacino R 33–43% → No quinolonas empíricas en infección grave</li>
          <li>MDR 46% + XDR 35.7% en hospitalización → Revisión PROA obligatoria día 3 en UCI</li>
        </ul>
      </div>
 
      <div style="background:rgba(63,185,80,0.06);border:1px solid rgba(63,185,80,0.2);border-radius:8px;padding:14px;">
        <div style="font-size:11px;font-weight:700;color:var(--accent2);text-transform:uppercase;letter-spacing:0.08em;margin-bottom:8px;">✅ Oportunidades de Desescalamiento</div>
        <ul class="criteria-list">
          <li>Proteus 100% sensible a Pip/Tazo + Meropenem → candidato ideal para desescalamiento</li>
          <li>S. agalactiae 100% sensible a Ampicilina → antibiótico de elección sin escalamiento</li>
          <li>E. faecalis 88–89% sensible a Ampicilina → desescalar desde glucopéptidos</li>
          <li>E. coli CE: Fosfomicina 100% → primera línea para ITU no complicada ambulatoria</li>
        </ul>
      </div>
 
      <div style="background:rgba(88,166,255,0.06);border:1px solid rgba(88,166,255,0.2);border-radius:8px;padding:14px;">
        <div style="font-size:11px;font-weight:700;color:var(--accent);text-transform:uppercase;letter-spacing:0.08em;margin-bottom:8px;">🔵 Principios PROA Institucionales</div>
        <ul class="criteria-list">
          <li>Obtener cultivo ANTES de iniciar antibiótico (excepción: sepsis grave)</li>
          <li>Revisión obligatoria con antibiograma a las 48–72 h</li>
          <li>Switch IV→VO activo cuando criterios cumplidos (reduce días de hospitalización)</li>
          <li>Duración definida en nota médica desde el inicio del tratamiento</li>
          <li>Consulta a Infectología en: bacteriemia, endocarditis, MRSA, XDR, fungemia</li>
        </ul>
      </div>
 
    </div>
  </div>
 
</div><!-- /container -->
 
<footer>
  <div style="color:var(--text-muted);margin-bottom:4px;font-weight:500;">
    Play Book de Uso de Antimicrobianos · Hospital General Regional de Orizaba · IMSS · Veracruz
  </div>
  <div>
    Elaborado con base en datos de biota institucional (n=5,849 aislamientos) · Criterios IDSA 2022–2024 · Clasificación Magiorakos et al. 2012 · Programa PROA Institucional
  </div>
  <div style="margin-top:6px;">
    Este documento es una herramienta de apoyo clínico. Ajustar siempre por función renal (TFGe), alergias documentadas e interacciones farmacológicas.
    Actualización recomendada: anual o ante cambios significativos en la biota institucional.
  </div>
</footer>
 
</body>
</html>
