<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>El caso de María Catalina — Ruta Jurídica Espacio Violeta</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,560;0,9..144,680;1,9..144,500&family=Work+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#241626;
    --bg-2:#2c1a2f;
    --surface:#3a2440;
    --surface-2:#4a2c52;
    --ink:#f6ede7;
    --ink-dim:#d9c6d6;
    --ink-faint:#b79cb4;
    --rose:#e0779f;
    --rose-dim:#8a4f66;
    --gold:#e3ac52;
    --teal:#59b09d;
    --terracotta:#d06a4f;
    --lavender:#8f7fd1;
    --line:rgba(246,237,231,0.14);
    --line-strong:rgba(246,237,231,0.28);
    --shadow: 0 30px 60px -25px rgba(10,4,12,0.65);
    --serif:'Fraunces', Georgia, 'Times New Roman', serif;
    --sans:'Work Sans', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
    --radius: 22px;
    color-scheme: dark;
  }
  :root[data-theme="light"]{
    --bg:#f6ede4;
    --bg-2:#f0e2d6;
    --surface:#ffffff;
    --surface-2:#fbf1e8;
    --ink:#2b1a2c;
    --ink-dim:#5e4358;
    --ink-faint:#8a7186;
    --line:rgba(43,26,44,0.12);
    --line-strong:rgba(43,26,44,0.22);
    --shadow: 0 30px 60px -30px rgba(60,30,40,0.3);
    color-scheme: light;
  }
  @media (prefers-color-scheme: light){
    :root:not([data-theme="dark"]){
      --bg:#f6ede4;
      --bg-2:#f0e2d6;
      --surface:#ffffff;
      --surface-2:#fbf1e8;
      --ink:#2b1a2c;
      --ink-dim:#5e4358;
      --ink-faint:#8a7186;
      --line:rgba(43,26,44,0.12);
      --line-strong:rgba(43,26,44,0.22);
      --shadow: 0 30px 60px -30px rgba(60,30,40,0.3);
      color-scheme: light;
    }
  }

  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:radial-gradient(circle at 15% -10%, var(--bg-2), var(--bg) 55%);
    color:var(--ink);
    font-family:var(--sans);
    min-height:100vh;
    -webkit-font-smoothing:antialiased;
    overflow-x:hidden;
  }
  h1,h2,h3,.serif{font-family:var(--serif);}
  a{color:inherit;}
  button{font-family:var(--sans);}
  .visually-hidden{position:absolute;width:1px;height:1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;}
  ::selection{background:var(--rose);color:#241626;}

  @media (prefers-reduced-motion: reduce){
    *{animation-duration:.001ms !important; animation-iteration-count:1 !important; transition-duration:.001ms !important; scroll-behavior:auto !important;}
  }

  /* ---------- App shell ---------- */
  #app{max-width:1180px;margin:0 auto;padding:0 clamp(16px,4vw,40px) 60px;}

  header.topbar{
    display:flex;align-items:center;justify-content:space-between;
    padding:20px 0 10px;gap:12px;
  }
  .brand{display:flex;align-items:center;gap:12px;}
  .brand__mark{
    width:38px;height:38px;border-radius:50%;
    background:conic-gradient(from 210deg, var(--rose), var(--gold), var(--teal), var(--rose));
    display:grid;place-items:center;flex:none;
    box-shadow: inset 0 0 0 2px rgba(0,0,0,0.08);
  }
  .brand__mark span{width:16px;height:16px;border-radius:50%;background:var(--bg);}
  .brand__text{line-height:1.15;}
  .brand__text b{font-family:var(--serif);font-size:1.05rem;font-weight:680;display:block;}
  .brand__text small{color:var(--ink-faint);font-size:.72rem;letter-spacing:.02em;}

  .topbar__tools{display:flex;align-items:center;gap:8px;}
  .icon-btn{
    background:var(--surface);border:1px solid var(--line);color:var(--ink);
    width:40px;height:40px;border-radius:50%;display:grid;place-items:center;cursor:pointer;
    transition:transform .15s ease, background .15s ease;
  }
  .icon-btn:hover{transform:translateY(-1px);}
  .icon-btn:active{transform:translateY(0);}
  .icon-btn svg{width:18px;height:18px;}

  /* ---------- Progress rail ---------- */
  nav.rail{
    display:flex;gap:6px;overflow-x:auto;padding:6px 2px 18px;
    scrollbar-width:none;
  }
  nav.rail::-webkit-scrollbar{display:none;}
  .rail__item{
    flex:none;display:flex;align-items:center;gap:8px;
    background:var(--surface);border:1px solid var(--line);
    padding:7px 14px 7px 8px;border-radius:100px;cursor:pointer;
    color:var(--ink-faint);font-size:.78rem;letter-spacing:.01em;
    transition:background .18s ease, color .18s ease, border-color .18s ease;
    white-space:nowrap;
  }
  .rail__item b{
    width:22px;height:22px;border-radius:50%;display:grid;place-items:center;
    background:var(--surface-2);font-family:var(--serif);font-size:.72rem;color:var(--ink-dim);flex:none;
  }
  .rail__item.is-done{color:var(--ink-dim);}
  .rail__item.is-done b{background:var(--teal);color:#12211d;}
  .rail__item.is-active{color:var(--ink);border-color:var(--line-strong);background:var(--surface-2);}
  .rail__item.is-active b{background:var(--rose);color:#2a1420;}

  /* ---------- Stage ---------- */
  .stage{
    position:relative;border-radius:var(--radius);overflow:hidden;
    background:var(--surface);border:1px solid var(--line);
    box-shadow:var(--shadow);
    min-height:min(78vh,720px);
    display:flex;flex-direction:column;
  }
  .scene{
    position:relative;flex:1;display:grid;
    grid-template-columns: 1.05fr 1fr;
    gap:0;
  }
  @media (max-width: 860px){
    .scene{grid-template-columns:1fr;}
  }

  .scene__art{
    position:relative;overflow:hidden;
    display:flex;align-items:flex-end;
    padding:26px;
    min-height:260px;
  }
  .scene__art svg{width:100%;height:auto;position:relative;z-index:1;}
  .scene__eyebrow{
    position:absolute;top:22px;left:26px;z-index:2;
    font-size:.72rem;letter-spacing:.03em;color:rgba(255,255,255,.86);
    background:rgba(0,0,0,.28);backdrop-filter:blur(6px);
    padding:6px 12px;border-radius:100px;border:1px solid rgba(255,255,255,.16);
  }

  .scene__body{
    padding:clamp(22px,4vw,42px);display:flex;flex-direction:column;gap:16px;
    border-left:1px solid var(--line);
    min-width:0;
  }
  @media (max-width: 860px){ .scene__body{border-left:none;border-top:1px solid var(--line);} }

  .scene__title{font-size:clamp(1.35rem,2.6vw,1.85rem);font-weight:680;line-height:1.12;margin:0;}
  .scene__kicker{
    font-size:.78rem;color:var(--ink-faint);letter-spacing:.01em;margin:0;
  }

  .dialogue{display:flex;flex-direction:column;gap:10px;margin:2px 0 4px;}
  .line{
    display:flex;gap:10px;align-items:flex-start;
    opacity:0;transform:translateY(6px);
    animation:reveal .5s ease forwards;
  }
  .line:nth-child(1){animation-delay:.05s}
  .line:nth-child(2){animation-delay:.16s}
  .line:nth-child(3){animation-delay:.27s}
  .line:nth-child(4){animation-delay:.38s}
  .line:nth-child(5){animation-delay:.49s}
  @keyframes reveal{to{opacity:1;transform:none;}}
  @keyframes stageIn{from{opacity:0;transform:translateY(10px) scale(.99);}to{opacity:1;transform:none;}}
  .scene, .cover{animation:stageIn .55s cubic-bezier(.2,.7,.3,1) both;}
  @keyframes flicker{0%,100%{opacity:.35;}45%{opacity:1;}60%{opacity:.55;}}
  @keyframes drift{from{transform:translateX(0);}to{transform:translateX(24px);}}
  @keyframes driftBack{from{transform:translateX(0);}to{transform:translateX(-30px);}}
  @keyframes bob{0%,100%{transform:translateY(0);}50%{transform:translateY(-5px);}}
  @keyframes dashMove{to{stroke-dashoffset:-40;}}
  @keyframes pulseNode{0%,100%{opacity:.55;r:8;}50%{opacity:1;r:11;}}
  @keyframes glowPulse{0%,100%{opacity:.5;}50%{opacity:.95;}}
  .fx-flicker{animation:flicker 2.6s ease-in-out infinite;}
  .fx-flicker.d2{animation-delay:.6s;}
  .fx-flicker.d3{animation-delay:1.3s;}
  .fx-drift{animation:drift 9s ease-in-out infinite alternate;}
  .fx-driftback{animation:driftBack 13s ease-in-out infinite alternate;}
  .fx-bob{animation:bob 3.4s ease-in-out infinite;}
  .fx-path{stroke-dasharray:6 8;animation:dashMove 1.6s linear infinite;}
  .fx-node{animation:pulseNode 2.2s ease-in-out infinite;}
  .fx-glow{animation:glowPulse 3.2s ease-in-out infinite;}
  .line__avatar{
    flex:none;width:30px;height:30px;border-radius:50%;
    display:grid;place-items:center;font-family:var(--serif);font-size:.82rem;
    color:#241626;margin-top:2px;
  }
  .line--narrador .line__avatar{background:var(--ink-faint);color:var(--bg);}
  .line--valentina .line__avatar{background:var(--gold);}
  .line--maria .line__avatar{background:var(--rose);}
  .line--equipo .line__avatar{background:var(--teal);}
  .line--vivian .line__avatar{background:var(--lavender);}
  .line__text{
    background:var(--surface-2);border:1px solid var(--line);
    padding:10px 14px;border-radius:14px;font-size:.95rem;line-height:1.5;
    color:var(--ink-dim);
  }
  .line--narrador .line__text{background:transparent;border:none;padding:2px 0;font-style:italic;color:var(--ink-faint);}
  .line__who{display:block;font-size:.68rem;letter-spacing:.03em;color:var(--ink-faint);margin-bottom:2px;}

  .legalbox{
    background:linear-gradient(155deg, rgba(227,172,82,.14), rgba(227,172,82,.03));
    border:1px solid rgba(227,172,82,.35);
    border-radius:16px;padding:14px 16px;
  }
  .legalbox h4{
    margin:0 0 8px;font-family:var(--sans);font-size:.78rem;font-weight:600;
    color:var(--gold);letter-spacing:.01em;display:flex;align-items:center;gap:6px;
  }
  .legalbox ul{margin:0;padding-left:18px;display:flex;flex-direction:column;gap:5px;}
  .legalbox li{font-size:.86rem;color:var(--ink-dim);line-height:1.45;}
  .legalbox li em{color:var(--ink);font-style:normal;font-weight:600;}

  .flow{display:flex;flex-direction:column;gap:10px;}
  .flow__branches{display:grid;grid-template-columns:repeat(auto-fit,minmax(190px,1fr));gap:12px;}
  .flow__branch{background:var(--surface-2);border:1px solid var(--line);border-radius:16px;padding:12px 14px;}
  .flow__branch h5{margin:0 0 8px;font-size:.72rem;letter-spacing:.02em;color:var(--ink-faint);font-weight:600;}
  .flow__node{
    font-size:.86rem;padding:8px 10px;border-radius:10px;margin-bottom:6px;
    background:var(--bg);border:1px solid var(--line);color:var(--ink);
  }
  .flow__node:last-child{margin-bottom:0;}
  .flow__node.accent{border-color:var(--accent,var(--rose));color:var(--accent,var(--rose));font-weight:600;}
  .flow__arrow{text-align:center;color:var(--ink-faint);font-size:.8rem;margin:-2px 0;}

  .chain{display:flex;flex-wrap:wrap;gap:8px;align-items:center;}
  .chain__node{
    font-size:.82rem;padding:7px 12px;border-radius:100px;background:var(--surface-2);
    border:1px solid var(--line);color:var(--ink-dim);
  }
  .chain__sep{color:var(--ink-faint);font-size:.8rem;}

  /* ---------- Controls / captions ---------- */
  .stage__foot{
    display:flex;align-items:center;gap:14px;justify-content:space-between;
    padding:14px 20px;border-top:1px solid var(--line);
    background:var(--bg-2);
  }
  .caption{
    flex:1;min-width:0;font-size:.82rem;color:var(--ink-faint);
    white-space:nowrap;overflow:hidden;text-overflow:ellipsis;
  }
  .caption b{color:var(--ink-dim);font-weight:600;}
  .stage__actions{display:flex;align-items:center;gap:8px;flex:none;}

  .btn{
    border:1px solid var(--line-strong);background:var(--surface);color:var(--ink);
    padding:9px 16px;border-radius:100px;font-size:.84rem;cursor:pointer;
    display:inline-flex;align-items:center;gap:7px;font-weight:500;
    transition:transform .12s ease, background .15s ease, border-color .15s ease;
  }
  .btn:hover{transform:translateY(-1px);border-color:var(--line-strong);}
  .btn:disabled{opacity:.4;cursor:not-allowed;transform:none;}
  .btn--primary{background:var(--rose);border-color:var(--rose);color:#2a1420;font-weight:600;}
  .btn--primary:hover{filter:brightness(1.06);}
  .btn--ghost{background:transparent;}
  .btn svg{width:15px;height:15px;flex:none;}

  .nav-arrows{display:flex;gap:8px;}

  /* ---------- Cover ---------- */
  .cover{
    position:relative;min-height:min(82vh,760px);
    border-radius:var(--radius);overflow:hidden;border:1px solid var(--line);
    display:flex;align-items:flex-end;box-shadow:var(--shadow);
    background:
      radial-gradient(ellipse at 30% 15%, rgba(224,119,159,.35), transparent 55%),
      radial-gradient(ellipse at 80% 0%, rgba(89,176,157,.22), transparent 45%),
      linear-gradient(190deg, #2c1a30, #1c1120 78%);
  }
  .cover__hills{position:absolute;inset:auto 0 0 0;height:46%;z-index:0;}
  .cover__content{position:relative;z-index:1;padding:clamp(24px,5vw,56px);max-width:720px;}
  .cover__eyebrow{
    display:inline-flex;align-items:center;gap:8px;font-size:.78rem;color:var(--gold);
    background:rgba(227,172,82,.12);border:1px solid rgba(227,172,82,.35);
    padding:6px 13px;border-radius:100px;margin-bottom:18px;
  }
  .cover h1{font-size:clamp(2.1rem,5.4vw,3.6rem);line-height:1.04;margin:0 0 14px;color:#fbf3ee;font-weight:560;}
  .cover h1 i{font-style:italic;color:var(--rose);font-weight:500;}
  .cover p{color:#e4d3de;font-size:1.02rem;line-height:1.55;max-width:56ch;margin:0 0 26px;}
  .cover__meta{display:flex;flex-wrap:wrap;gap:10px;margin-bottom:28px;}
  .cover__meta span{
    font-size:.78rem;color:#d9c6d6;background:rgba(255,255,255,.06);
    border:1px solid rgba(255,255,255,.14);padding:6px 12px;border-radius:100px;
  }
  .cover__actions{display:flex;flex-wrap:wrap;gap:12px;align-items:center;}
  .cover__hint{font-size:.78rem;color:#c8b4c4;max-width:36ch;}

  /* ---------- Closing ---------- */
  .closing-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;}
  @media (max-width:640px){.closing-grid{grid-template-columns:repeat(2,1fr);}}
  .closing-grid div{
    background:var(--surface-2);border:1px solid var(--line);border-radius:12px;
    padding:10px 12px;font-size:.78rem;color:var(--ink-dim);line-height:1.4;
  }
  .closing-grid b{display:block;color:var(--ink);font-size:.9rem;font-family:var(--serif);margin-bottom:2px;}

  .reflect{
    margin-top:6px;border:1px dashed var(--line-strong);border-radius:14px;padding:14px 16px;
    font-size:.9rem;color:var(--ink-dim);font-style:italic;
  }

  footer.foot{
    margin-top:34px;display:flex;flex-wrap:wrap;justify-content:space-between;gap:14px;
    color:var(--ink-faint);font-size:.78rem;padding-top:18px;border-top:1px solid var(--line);
  }
</style>
</head>
<body>
<div id="app">

  <header class="topbar">
    <div class="brand">
      <div class="brand__mark" aria-hidden="true"><span></span></div>
      <div class="brand__text">
        <b>Espacio Violeta</b>
        <small>Consultorio Jurídico · Fundación Universitaria de Popayán</small>
      </div>
    </div>
    <div class="topbar__tools">
      <button class="icon-btn" id="themeToggle" title="Cambiar tema" aria-label="Cambiar tema claro u oscuro">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M12 3v2M12 19v2M4.2 4.2l1.4 1.4M18.4 18.4l1.4 1.4M3 12h2M19 12h2M4.2 19.8l1.4-1.4M18.4 5.6l1.4-1.4" stroke-linecap="round"/><circle cx="12" cy="12" r="4.4"/></svg>
      </button>
      <button class="icon-btn" id="muteToggle" title="Silenciar narración" aria-label="Activar o silenciar la narración">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" id="muteIcon"><path d="M4 9v6h3.6L13 19V5L7.6 9H4z" stroke-linejoin="round"/><path d="M16.2 8.2a5 5 0 0 1 0 7.6M18.6 5.8a8.6 8.6 0 0 1 0 12.4" stroke-linecap="round"/></svg>
      </button>
    </div>
  </header>

  <nav class="rail" id="rail" aria-label="Progreso del caso"></nav>

  <main class="stage" id="stage"></main>

  <footer class="foot">
    <span>Historia ficticia con fines pedagógicos para el Consultorio Jurídico FUP · Sede Norte, Santander de Quilichao, Cauca.</span>
    <span>Contenido de orientación educativa — debe validarse con la normativa vigente y los protocolos institucionales.</span>
    <span>La narración usa la voz en español de tu dispositivo; el acento puede variar según el navegador.</span>
  </footer>
</div>

<script>
(function(){
"use strict";

/* ============ DATA ============ */
const AVA = {narrador:"N", valentina:"V", maria:"MC", equipo:"E", vivian:"PS"};
const WHO = {narrador:"Narrador", valentina:"Valentina · estudiante", maria:"María Catalina", equipo:"Equipo docente", vivian:"Vivian · psicóloga"};

function svgWrap(inner, bg, extraDefs){
  return `<svg viewBox="0 0 520 300" preserveAspectRatio="xMidYMax meet" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <linearGradient id="g1" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0" stop-color="${bg[0]}"/><stop offset="1" stop-color="${bg[1]}"/>
      </linearGradient>
      <radialGradient id="skin" cx="35%" cy="30%" r="75%">
        <stop offset="0" stop-color="#d8a377"/><stop offset="1" stop-color="#b97c56"/>
      </radialGradient>
      <radialGradient id="lamp" cx="50%" cy="45%" r="55%">
        <stop offset="0" stop-color="#ffe3a8" stop-opacity=".9"/><stop offset="1" stop-color="#ffe3a8" stop-opacity="0"/>
      </radialGradient>
      <linearGradient id="ruana" x1="0" y1="0" x2="1" y2="0">
        <stop offset="0" stop-color="#a6395f"/><stop offset=".33" stop-color="#c9536f"/><stop offset=".33" stop-color="#e0ac52"/><stop offset=".55" stop-color="#e0ac52"/><stop offset=".55" stop-color="#a6395f"/><stop offset=".78" stop-color="#a6395f"/><stop offset=".78" stop-color="#6f7fae"/><stop offset="1" stop-color="#6f7fae"/>
      </linearGradient>
      ${extraDefs||''}
    </defs>
    <rect width="520" height="300" fill="url(#g1)"/>
    ${inner}
  </svg>`;
}
function firefly(x,y,c,delay){
  return `<circle cx="${x}" cy="${y}" r="2.2" fill="${c||'#ffe3a8'}" class="fx-flicker ${delay||''}"/>`;
}
function bird(x,y,s,cls){
  s=s||1;
  return `<path d="M${x} ${y} q${6*s} -8 ${12*s} 0 q${6*s} -8 ${12*s} 0" fill="none" stroke="#efe0ea" stroke-width="1.6" stroke-linecap="round" opacity=".55" class="${cls||''}"/>`;
}
function mountains(){
  return `
  <g class="fx-driftback">
    <path d="M-20 220 L70 130 L150 200 L230 110 L300 190 L390 120 L470 195 L560 150 L560 300 L-20 300 Z" fill="#241130" opacity=".9"/>
  </g>
  <g class="fx-drift">
    <path d="M-20 255 L110 195 L190 240 L290 180 L380 245 L470 205 L560 245 L560 300 L-20 300 Z" fill="#2b1734" opacity=".95"/>
  </g>`;
}
function townRow(baseY){
  return `
  <g opacity=".92">
    <rect x="66" y="${baseY-46}" width="42" height="46" fill="#3d2440"/>
    <path d="M62 ${baseY-46} L87 ${baseY-66} L112 ${baseY-46} Z" fill="#a45a4a"/>
    <rect x="118" y="${baseY-64}" width="52" height="64" fill="#4a2c4f"/>
    <path d="M113 ${baseY-64} L144 ${baseY-86} L175 ${baseY-64} Z" fill="#b6664f"/>
    <rect x="330" y="${baseY-54}" width="46" height="54" fill="#3d2440"/>
    <path d="M325 ${baseY-54} L353 ${baseY-74} L381 ${baseY-54} Z" fill="#a45a4a"/>
    <rect x="382" y="${baseY-40}" width="38" height="40" fill="#4a2c4f"/>
    <rect x="228" y="${baseY-92}" width="34" height="92" fill="#3d2440"/>
    <path d="M223 ${baseY-92} L245 ${baseY-118} L267 ${baseY-92} Z" fill="#c98753"/>
    <rect x="240" y="${baseY-108} " width="10" height="18" fill="#2b1734"/>
    <circle cx="245" cy="${baseY-122}" r="5" fill="#2b1734"/>
    <rect x="236" y="${baseY-60}" width="8" height="14" rx="1" fill="#e3ac52" opacity=".8"/>
    <rect x="252" y="${baseY-60}" width="8" height="14" rx="1" fill="#e3ac52" opacity=".8"/>
    <rect x="82" y="${baseY-28}" width="10" height="14" rx="1" fill="#e3ac52" opacity=".75"/>
    <rect x="140" y="${baseY-40}" width="10" height="14" rx="1" fill="#e3ac52" opacity=".7"/>
  </g>`;
}
function moto(x,y,s){
  s=s||1;
  return `<g transform="translate(${x} ${y}) scale(${s})" opacity=".8">
    <circle cx="-10" cy="8" r="6" fill="none" stroke="#c9536f" stroke-width="2"/>
    <circle cx="12" cy="8" r="6" fill="none" stroke="#c9536f" stroke-width="2"/>
    <path d="M-10 8 L0 -4 L12 8 M0 -4 L4 -10" stroke="#e0ac52" stroke-width="2" fill="none" stroke-linecap="round"/>
  </g>`;
}
function lampPost(x,y){
  return `<g transform="translate(${x} ${y})">
    <rect x="-2" y="-70" width="4" height="70" fill="#241130"/>
    <circle cx="0" cy="-74" r="20" fill="url(#lamp)" class="fx-glow"/>
    <circle cx="0" cy="-74" r="5" fill="#ffe3a8"/>
  </g>`;
}
function sunAfternoon(cx,cy,r){
  return `<circle cx="${cx}" cy="${cy}" r="${r*1.7}" fill="#f2a860" opacity=".22" class="fx-glow"/>
  <circle cx="${cx}" cy="${cy}" r="${r}" fill="#ffd899"/>`;
}
function cloud(x,y,s,cls){
  s=s||1;
  return `<g transform="translate(${x} ${y}) scale(${s})" opacity=".5" class="${cls||''}">
    <ellipse cx="0" cy="0" rx="22" ry="9" fill="#fbe6c8"/>
    <ellipse cx="16" cy="-4" rx="14" ry="8" fill="#fbe6c8"/>
    <ellipse cx="-16" cy="-2" rx="12" ry="7" fill="#fbe6c8"/>
  </g>`;
}
function signText(x,y,content,opts){
  opts = opts||{};
  return `<text x="${x}" y="${y}" font-family="Work Sans, sans-serif" font-size="${opts.size||11}" letter-spacing="${opts.spacing||1}" fill="${opts.color||'#f6ede7'}" opacity="${opts.opacity!=null?opts.opacity:.85}" text-anchor="${opts.anchor||'start'}" font-weight="${opts.weight||600}">${content}</text>`;
}
function scaleIcon(x,y,s,color){
  s=s||1; color=color||'#e3ac52';
  return `<g transform="translate(${x} ${y}) scale(${s})" stroke="${color}" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round" opacity=".85">
    <path d="M0 -14 V14"/><path d="M-16 -10 H16"/>
    <path d="M-16 -10 L-24 4 a8 6 0 0 0 16 0 Z"/>
    <path d="M16 -10 L8 4 a8 6 0 0 0 16 0 Z"/>
    <path d="M-9 14 H9"/>
  </g>`;
}
function bookshelf(x,y,w,h){
  const cols = ['#c1567f','#e0ac52','#59b09d','#8f7fd1','#d06a4f','#7a4a63'];
  let books = '';
  let bx = x;
  let i = 0;
  while(bx < x+w-6){
    const bw = 7 + (i%3)*2;
    const bh = h - 6 - (i%4)*5;
    books += `<rect x="${bx}" y="${y+h-bh}" width="${bw-1}" height="${bh}" fill="${cols[i%cols.length]}" opacity=".8"/>`;
    bx += bw; i++;
  }
  return `<rect x="${x}" y="${y}" width="${w}" height="${h}" fill="#241730" opacity=".7"/>${books}
  <rect x="${x}" y="${y+h}" width="${w}" height="4" fill="#1c1120"/>`;
}
function callWaves(x,y,color){
  color = color||'#59b09d';
  return `<g transform="translate(${x} ${y})" stroke="${color}" fill="none" stroke-width="2" stroke-linecap="round" opacity=".8">
    <path d="M0 0 q6 -6 0 -12" class="fx-flicker"/>
    <path d="M6 4 q12 -12 0 -24" class="fx-flicker d2"/>
  </g>`;
}
function person(cx, cy, opts){
  opts = opts||{};
  const skirt = opts.pattern ? `url(#ruana)` : (opts.skirt||'#7a4a63');
  const hair = opts.hair || HAIR_LONG_CURLY;
  const bruise = opts.bruise;
  const bob = opts.bob ? 'fx-bob' : '';
  return `
  <g transform="translate(${cx} ${cy})" class="${bob}">
    <ellipse cx="0" cy="42" rx="36" ry="9" fill="rgba(0,0,0,.25)"/>
    <path d="M-24 42 C-29 -4 -19 -36 0 -36 C19 -36 29 -4 24 42 Z" fill="${skirt}"/>
    <path d="M-24 42 C-29 -4 -19 -36 0 -36 C19 -36 29 -4 24 42 Z" fill="url(#skin)" opacity="0"/>
    <path d="M-16 -30 Q0 -20 16 -30 L20 -6 Q0 4 -20 -6 Z" fill="rgba(0,0,0,.12)"/>
    <circle cx="0" cy="-60" r="18" fill="url(#skin)"/>
    ${bruise? `<ellipse cx="8" cy="-63" rx="7" ry="5" fill="#8a5a6f" opacity="0.55"/>`:``}
    <path d="${hair}" fill="#2a1b22"/>
    <path d="${hair}" fill="#402a37" opacity=".4" transform="translate(-1,-2) scale(0.94)"/>
  </g>`;
}
const HAIR_LONG_CURLY = "M-18 -60 Q-24 -76 -6 -80 Q10 -84 18 -70 Q24 -58 17 -46 Q23 -40 18 -30 Q10 -40 8 -52 Q-2 -44 -14 -48 Q-22 -40 -20 -30 Q-28 -42 -22 -54 Q-24 -58 -18 -60 Z";
const HAIR_BRAID = "M-17 -62 Q-22 -78 -4 -82 Q12 -85 18 -70 Q22 -56 12 -48 Q18 -30 10 -14 Q6 -14 8 -30 Q0 -40 -4 -50 Q-16 -44 -20 -34 Q-26 -48 -17 -62 Z";
const HAIR_SHORT_A = "M-16 -60 Q-20 -76 0 -78 Q20 -76 16 -60 Q22 -50 14 -42 Q6 -50 -6 -46 Q-14 -50 -14 -42 Q-22 -50 -16 -60 Z";
const HAIR_SHORT_B = "M-15 -60 Q-18 -74 0 -76 Q18 -74 15 -60 Q20 -50 10 -44 Q0 -50 -10 -44 Q-20 -50 -15 -60 Z";

function sceneHook(){
  return svgWrap(`
    ${sunAfternoon(430,64,26)}
    ${cloud(90,50,1,'fx-drift')}${cloud(280,30,.7,'fx-driftback')}
    ${mountains()}
    ${townRow(258)}
    <path d="M0 272 L200 262 L340 270 L520 258 L520 300 L0 300 Z" fill="#2a1830"/>
    <rect x="176" y="228" width="98" height="34" rx="3" fill="#20111f"/>
    ${signText(225,249,'CONSULTORIO JURÍDICO · FUP',{size:8,spacing:.5,anchor:'middle',color:'#e3ac52'})}
    ${moto(300,268,0.9)}${moto(340,272,0.75)}
    ${bird(60,60,.9,'fx-drift')}${bird(120,40,.7,'fx-driftback')}
  `, ["#8a6a52","#2a1830"]);
}
function sceneStreetWorry(){
  return svgWrap(`
    ${sunAfternoon(90,54,22)}
    ${cloud(360,40,1,'fx-driftback')}
    ${mountains()}
    ${townRow(250)}
    <path d="M0 262 L520 262 L520 300 L0 300 Z" fill="#2a1830"/>
    <rect x="330" y="150" width="150" height="112" fill="#22132a"/>
    <rect x="345" y="168" width="120" height="80" rx="4" fill="#3d2a45" opacity=".9"/>
    ${signText(405,158,'ESPACIO VIOLETA',{size:9,spacing:.6,anchor:'middle',color:'#e0779f'})}
    <ellipse cx="150" cy="284" rx="50" ry="8" fill="rgba(0,0,0,.3)"/>
    <ellipse cx="180" cy="286" rx="18" ry="4" fill="rgba(0,0,0,.2)"/>
    ${person(150,250,{skirt:'url(#ruana)',pattern:true,hair:HAIR_LONG_CURLY})}
    <path d="M126 195 q10 -10 22 -2" stroke="#c1a6b8" stroke-width="3" fill="none" stroke-linecap="round" opacity=".9"/>
    <rect x="128" y="200" width="20" height="12" rx="2" fill="#dfe6f0" opacity=".85"/>
  `, ["#c99a63","#2a1830"]);
}
function sceneReception(){
  return svgWrap(`
    <rect x="0" y="0" width="520" height="300" fill="#3d2743"/>
    <path d="M330 0 L520 0 L520 230 L400 300 L300 300 Z" fill="#4a2c52" opacity=".4"/>
    <path d="M360 -10 L480 -10 L440 235 L335 235 Z" fill="#f2c98a" opacity=".16"/>
    <rect x="0" y="222" width="520" height="78" fill="#2c1a30"/>
    <rect x="52" y="200" width="240" height="28" rx="6" fill="#583a5f"/>
    <rect x="52" y="200" width="240" height="6" rx="3" fill="#e3ac52" opacity=".7"/>
    ${signText(70,193,'CONSULTORIO JURÍDICO FUP',{size:9,spacing:.6,color:'#f6ede7',opacity:.9})}
    ${signText(70,214,'Sede Norte · Espacio Violeta',{size:7.5,spacing:.4,color:'#d9c6d6',weight:400})}
    ${scaleIcon(160,178,0.55,'#e3ac52')}
    ${bookshelf(420,120,70,90)}
    <path d="M40 300 Q40 250 60 240 Q80 250 80 300 Z" fill="#3f6a54"/>
    <path d="M45 300 Q45 260 60 250 Q75 260 75 300 Z" fill="#4f8265"/>
    <g class="fx-bob">${person(210,225,{skirt:'#c1567f',hair:HAIR_LONG_CURLY})}</g>
    ${person(340,232,{pattern:true,hair:HAIR_BRAID,bruise:true})}
    <path d="M255 168 q26 -14 52 2" stroke="#e3ac52" stroke-width="2" fill="none" opacity=".6" stroke-linecap="round"/>
  `, ["#5a3a5f","#241626"]);
}
function scenePrivateRoom(accent){
  return svgWrap(`
    <rect x="0" y="0" width="520" height="300" fill="#3a2440"/>
    <rect x="34" y="30" width="452" height="240" rx="20" fill="#2c1a30" opacity=".55"/>
    <rect x="365" y="46" width="90" height="118" rx="4" fill="#f2c98a" opacity=".14"/>
    <rect x="46" y="46" width="90" height="30" rx="4" fill="${accent}" opacity=".12"/>
    ${signText(56,66,'ESPACIO VIOLETA',{size:8,spacing:.5,color:accent,weight:600,opacity:.8})}
    <rect x="60" y="150" width="4" height="90" fill="#583a5f" opacity=".6"/>
    <path d="M60 150 Q40 190 60 240" stroke="#583a5f" stroke-width="4" fill="none" opacity=".5"/>
    <rect x="120" y="90" width="70" height="46" rx="8" fill="${accent}" opacity=".16"/>
    <path d="M132 116 q17 -18 34 0 q17 -18 34 0" stroke="${accent}" stroke-width="2.4" fill="none" opacity=".7" stroke-linecap="round"/>
    <g class="fx-bob">${person(225,228,{skirt:'#c1567f',hair:HAIR_LONG_CURLY})}</g>
    ${person(340,232,{pattern:true,hair:HAIR_BRAID,bruise:true})}
    <path d="M40 300 Q40 265 55 258 Q70 265 70 300 Z" fill="#3f6a54" opacity=".8"/>
  `, ["#4a2c52","#221324"]);
}
function sceneTeam(){
  return svgWrap(`
    <rect x="0" y="0" width="520" height="300" fill="#241730"/>
    <rect x="360" y="60" width="120" height="110" rx="4" fill="#f2c98a" opacity=".12"/>
    ${bookshelf(20,50,90,120)}
    ${signText(65,44,'SALA DE CASOS',{size:8,spacing:1,anchor:'middle',color:'#d9c6d6',weight:600,opacity:.7})}
    <ellipse cx="260" cy="255" rx="230" ry="26" fill="#1c1120"/>
    <rect x="70" y="235" width="380" height="16" rx="8" fill="#4a2c52"/>
    <rect x="150" y="150" width="46" height="34" rx="4" fill="#3a2440" opacity=".9"/>
    <path d="M150 150 h46" stroke="#e3ac52" stroke-width="2" opacity=".6"/>
    ${scaleIcon(330,120,0.5,'#e0ac52')}
    <g class="fx-bob">${person(150,232,{skirt:'#c1567f',hair:HAIR_LONG_CURLY})}</g>
    ${person(280,238,{skirt:'#59b09d',hair:HAIR_SHORT_A})}
    ${person(390,234,{skirt:'#e0ac52',hair:HAIR_SHORT_B})}
    <rect x="255" y="205" width="30" height="22" rx="3" fill="#583a5f"/>
    <rect x="370" y="208" width="26" height="20" rx="3" fill="#583a5f"/>
  `, ["#3a2440","#180e1f"]);
}
function sceneVivian(){
  return svgWrap(`
    <rect x="0" y="0" width="520" height="300" fill="#2c1a30"/>
    <rect x="330" y="40" width="150" height="130" rx="4" fill="#f2c98a" opacity=".12"/>
    ${bookshelf(20,60,70,100)}
    <g class="fx-bob">${person(150,235,{skirt:'#c1567f',hair:HAIR_LONG_CURLY})}</g>
    <rect x="163" y="195" width="16" height="22" rx="3" fill="#e3ac52" opacity=".9"/>
    ${callWaves(186,196,'#59b09d')}
    <g opacity=".92">${person(400,236,{skirt:'#8f7fd1',hair:HAIR_SHORT_B})}</g>
    <rect x="380" y="190" width="26" height="20" rx="3" fill="#583a5f"/>
    ${signText(400,170,'VIVIAN · PSICÓLOGA',{size:8,spacing:.6,anchor:'middle',color:'#8f7fd1',weight:600})}
  `, ["#3a2440","#180e1f"]);
}
function badgeEmblem(x,y,s,color){
  s=s||1; color=color||'#e3ac52';
  return `<g transform="translate(${x} ${y}) scale(${s})">
    <path d="M0 -22 L20 -14 L20 6 Q20 24 0 32 Q-20 24 -20 6 L-20 -14 Z" fill="none" stroke="${color}" stroke-width="2.4" opacity=".85"/>
    ${scaleIcon(0,4,0.62,color)}
  </g>`;
}
function columnsFacade(x,y,w,h,color){
  color = color || '#e7ddc9';
  let cols='';
  const n = Math.floor(w/26);
  for(let i=0;i<n;i++){
    cols += `<rect x="${x+10+i*26}" y="${y+18}" width="9" height="${h-18}" fill="${color}" opacity=".85"/>`;
  }
  return `
  <path d="M${x} ${y+18} L${x+w/2} ${y-14} L${x+w} ${y+18} Z" fill="${color}" opacity=".9"/>
  <rect x="${x}" y="${y+14}" width="${w}" height="8" fill="${color}"/>
  ${cols}
  <rect x="${x-6}" y="${y+h}" width="${w+12}" height="8" fill="${color}" opacity=".9"/>`;
}
function hospitalCross(x,y,s){
  s=s||1;
  return `<g transform="translate(${x} ${y}) scale(${s})">
    <rect x="-16" y="-16" width="32" height="32" rx="7" fill="#c1533f"/>
    <rect x="-4" y="-11" width="8" height="22" fill="#fbe9e4"/>
    <rect x="-11" y="-4" width="22" height="8" fill="#fbe9e4"/>
  </g>`;
}
function sceneHospital(){
  return svgWrap(`
    <rect x="0" y="0" width="520" height="300" fill="#e9dcc9"/>
    <path d="M0 210 L520 210 L520 300 L0 300 Z" fill="#cdbda0"/>
    <rect x="60" y="80" width="400" height="130" fill="#f4ede0"/>
    <rect x="60" y="80" width="400" height="14" fill="#8fa79b"/>
    ${hospitalCross(260,60,1.15)}
    ${signText(260,140,'IPS · URGENCIAS',{size:12,spacing:1,anchor:'middle',color:'#3a5148',weight:700})}
    ${signText(260,158,'Atención integral y gratuita',{size:8,spacing:.4,anchor:'middle',color:'#5a6b62',weight:400})}
    <rect x="90" y="170" width="70" height="40" rx="4" fill="#8fa79b" opacity=".5"/>
    <rect x="360" y="170" width="70" height="40" rx="4" fill="#8fa79b" opacity=".5"/>
    <rect x="230" y="182" width="60" height="10" rx="4" fill="#c1533f" opacity=".8"/>
    <g class="fx-bob">${person(190,235,{skirt:'url(#ruana)',pattern:true,hair:HAIR_LONG_CURLY,bruise:true})}</g>
    ${person(320,238,{skirt:'#3a5148',hair:HAIR_SHORT_A})}
    <rect x="298" y="196" width="46" height="14" rx="3" fill="#fbe9e4"/>
    <rect x="298" y="196" width="46" height="14" rx="3" fill="none" stroke="#3a5148" stroke-width="1.4"/>
  `, ["#efe4d2","#cdbda0"]);
}
function sceneFiscalia(){
  return svgWrap(`
    <rect x="0" y="0" width="520" height="300" fill="#dfe3ea"/>
    <path d="M0 230 L520 230 L520 300 L0 300 Z" fill="#b7bfcc"/>
    ${columnsFacade(130,110,260,90,'#eef1f6')}
    <rect x="115" y="222" width="290" height="10" fill="#9aa3b3"/>
    ${badgeEmblem(260,72,1,'#8a6f2c')}
    ${signText(260,44,'FISCALÍA GENERAL DE LA NACIÓN',{size:9.5,spacing:.5,anchor:'middle',color:'#3a3f4d',weight:700})}
    <rect x="30" y="0" width="10" height="230" fill="#b1543f" opacity=".8"/>
    <rect x="30" y="0" width="10" height="76" fill="#e3ac52" opacity=".85"/>
    <rect x="30" y="76" width="10" height="76" fill="#2f5f8a" opacity=".85"/>
    <g class="fx-bob">${person(230,246,{skirt:'url(#ruana)',pattern:true,hair:HAIR_LONG_CURLY})}</g>
    ${person(330,250,{skirt:'#2f5f8a',hair:HAIR_SHORT_B})}
  `, ["#eef1f6","#b7bfcc"]);
}
function sceneComisaria(){
  return svgWrap(`
    <rect x="0" y="0" width="520" height="300" fill="#e4dbe6"/>
    <path d="M0 228 L520 228 L520 300 L0 300 Z" fill="#b9a9bd"/>
    <rect x="120" y="110" width="280" height="118" fill="#f2ecf4"/>
    <rect x="120" y="110" width="280" height="14" fill="#6f4f74"/>
    ${badgeEmblem(260,78,0.95,'#6f4f74')}
    ${signText(260,150,'COMISARÍA DE FAMILIA',{size:11,spacing:.8,anchor:'middle',color:'#4a2c52',weight:700})}
    <rect x="150" y="170" width="34" height="58" fill="#c9bccb"/>
    <rect x="336" y="170" width="34" height="58" fill="#c9bccb"/>
    <rect x="245" y="188" width="30" height="40" fill="#6f4f74" opacity=".85"/>
    <g class="fx-bob">${person(210,246,{skirt:'url(#ruana)',pattern:true,hair:HAIR_LONG_CURLY,bruise:true})}</g>
    ${person(320,250,{skirt:'#4a2c52',hair:HAIR_SHORT_A})}
  `, ["#f2ecf4","#b9a9bd"]);
}
function sceneRoute(accent){
  return svgWrap(`
    <rect x="0" y="0" width="520" height="300" fill="#221430"/>
    <circle cx="420" cy="70" r="70" fill="${accent}" opacity=".14" class="fx-glow"/>
    <circle cx="70" cy="240" r="80" fill="${accent}" opacity=".08"/>
    <g opacity=".5">
      <rect x="30" y="205" width="30" height="55" fill="#3a2440"/>
      <rect x="440" y="40" width="40" height="90" fill="#3a2440"/>
      <rect x="470" y="0" width="34" height="60" fill="#2c1a30"/>
    </g>
    <g fill="none" stroke="${accent}" stroke-width="3" stroke-linecap="round" opacity=".9">
      <path class="fx-path" d="M90 220 L90 160 L220 160 L220 110 L360 110 L360 70 L430 70"/>
    </g>
    <circle cx="90" cy="220" r="9" fill="${accent}"/>
    <circle cx="220" cy="160" r="7" fill="${accent}" class="fx-node" opacity=".8"/>
    <circle cx="360" cy="110" r="7" fill="${accent}" class="fx-node" opacity=".8"/>
    <circle cx="430" cy="70" r="10" fill="${accent}" class="fx-node"/>
    <path d="M78 232 h24 v-14 h-24 Z M84 232 v-8 h12 v8" fill="none" stroke="${accent}" stroke-width="2" opacity=".8"/>
  `, ["#2c1a30","#170c1f"]);
}
function sceneClosing(){
  return svgWrap(`
    ${sunAfternoon(120,66,30)}
    ${cloud(340,44,.9,'fx-drift')}
    ${mountains()}
    ${townRow(252)}
    <path d="M0 264 L520 264 L520 300 L0 300 Z" fill="#2a1830"/>
    <rect x="196" y="196" width="54" height="68" fill="#3a2440"/>
    <path d="M191 196 L223 170 L255 196 Z" fill="#c1785a"/>
    <rect x="216" y="228" width="14" height="36" fill="#f2c98a" opacity=".8"/>
    ${signText(223,190,'FUP',{size:7,spacing:1,anchor:'middle',color:'#e3ac52',weight:700})}
    <g class="fx-bob">${person(310,240,{skirt:'url(#ruana)',pattern:true,hair:HAIR_LONG_CURLY})}</g>
    ${bird(60,50,1,'fx-drift')}${bird(100,30,.8,'fx-driftback')}${bird(390,60,.9,'fx-drift')}
  `, ["#c99a63","#2a1830"]);
}

const chapters = [
{
  id:"hook", kicker:"Antes de empezar", title:"Un viernes en la tarde, en Santander de Quilichao",
  eyebrow:"18 de septiembre de 2026 · Cauca", art:sceneHook(), accent:"var(--rose)",
  lines:[
    {who:"narrador", text:"Arrímese, que le voy a contar un cuento de este Cauca bravo y bonito. Un viernes 18 de septiembre de 2026, con el sol de la tarde todavía pegando duro sobre Santander de Quilichao."},
    {who:"narrador", text:"Ese día llegó al Consultorio Jurídico de la FUP una mujer que decía venir por una simple cuota de alimentos."},
    {who:"narrador", text:"Pero óigame bien esto: las apariencias, en este oficio, casi nunca dicen toda la verdad."}
  ],
  legal:null, flow:null
},
{
  id:"llegada", kicker:"Minutos antes", title:"Un pie que entra y otro que quiere salir corriendo",
  eyebrow:"Fuera del Consultorio Jurídico · FUP Sede Norte", art:sceneStreetWorry(), accent:"var(--rose)",
  lines:[
    {who:"narrador", text:"Ahí la tienen: María Catalina, treinta y ocho años, parada frente a la puerta, con un pie que quería entrar y el otro que quería salir corriendo pa'l otro lado."},
    {who:"narrador", text:"Se tapaba el cachete con la mano, como si con eso alcanzara a esconder también el susto. Debajo, un morado que ya no había maquillaje que lo disimulara."},
    {who:"maria", text:"Vine porque necesito arreglar una cuota de alimentos pa' mi hija… al menos eso fue lo que me repetí todo el camino, pa' animarme a entrar."}
  ],
  legal:null, flow:null
},
{
  id:"recepcion", kicker:"Paso 1 · Recepción segura", title:"Aquí la atendemos, no se preocupe",
  eyebrow:"Recepción — Espacio Violeta", art:sceneReception(), accent:"var(--rose)",
  lines:[
    {who:"valentina", text:"Buenas tardes, ¿la puedo ayudar? Aquí la atendemos con confianza, no se preocupe."},
    {who:"maria", text:"Vengo porque necesito una cuota de alimentos pa' mi hija… pero también hay otras cosas."},
    {who:"valentina", text:"Con gusto la orientamos en eso. Si gusta, pasamos a un lugar más privado, y ahí me cuenta con calma todo lo que necesite."},
    {who:"narrador", text:"Y ojo con esto, porque aquí está la clave del primer paso: antes de hablar de denuncias o de cuotas de alimentos, se escucha, se protege la intimidad, y no se hace repetir a nadie lo que ya le costó tanto decir."}
  ],
  legal:{title:"Principio transversal", items:["Evitar preguntas innecesarias, juicios o cuestionamientos sobre su comportamiento.","<em>Evitar la revictimización secundaria</em> en cada contacto con la usuaria."]},
  flow:null
},
{
  id:"vivian", kicker:"Apoyo psicosocial", title:"Vivian se une a la conversación",
  eyebrow:"Espacio Violeta — atención conjunta", art:sceneVivian(), accent:"var(--lavender)",
  lines:[
    {who:"valentina", text:"Doña María Catalina, la va a acompañar también Vivian, nuestra psicóloga, pa' que se sienta más tranquila contándonos esto. Ya mismo la llamo."},
    {who:"vivian", text:"Buenas tardes, María Catalina. Vamos a un saloncito aparte, rosado, tranquilo, solo entre nosotras tres."},
    {who:"maria", text:"Gracias… la verdad me daba mucha pena contar esto delante de cualquiera."},
    {who:"narrador", text:"Y ahí, con esa sola frase, ya se entendía que lo de la cuota de alimentos era apenas la puerta de entrada a algo mucho más hondo."}
  ],
  legal:{title:"Por qué se activa apoyo psicológico", items:["La atención integral incluye <em>valoración psicológica</em>, no solo jurídica.","Reduce la revictimización: la usuaria no repite los hechos más dolorosos ante cada persona nueva."]},
  flow:null
},
{
  id:"valoracion", kicker:"Paso 2 · Valoración inicial", title:"Lo que empieza a salir a flote",
  eyebrow:"Espacio Violeta — sala privada", art:scenePrivateRoom("var(--rose)"), accent:"var(--rose)",
  lines:[
    {who:"maria", text:"Necesito que le fijen una cuota de alimentos a mi hija Sofía, de doce años. Nos separamos hace poco y él no nos ha dado nada."},
    {who:"vivian", text:"Claro que la orientamos en eso. Pero cuénteme, María Catalina: ¿cómo han estado usted y Sofía desde la separación?"},
    {who:"maria", text:"Pues… la verdad es que nos separamos porque ya no aguanté más golpes."},
    {who:"narrador", text:"Y ahí el equipo entendió que esto no era una consulta cualquiera. Porque detrás de una cuota de alimentos, casi siempre hay una historia entera esperando para ser contada."}
  ],
  legal:{title:"Preguntas guía del punto de decisión", items:["¿Existe riesgo actual?","¿Necesita atención médica urgente?","¿Hay niñas, niños o adolescentes en el hogar?","¿Ya realizó alguna denuncia?","¿Qué orientación jurídica requiere?"]},
  flow:null
},
{
  id:"giro", kicker:"El corazón del caso", title:"Trece años de matrimonio, contados despacio",
  eyebrow:"Espacio Violeta — sala privada", art:scenePrivateRoom("var(--terracotta)"), accent:"var(--terracotta)",
  lines:[
    {who:"maria", text:"Yo estuve trece años casada con Jesús Rendón. Él es pastor de una iglesia por el barrio, y siempre me metió en la cabeza que la mujer está para obedecer al marido."},
    {who:"maria", text:"Todo lo económico lo manejaba él. Yo nunca trabajé por fuera; me dediqué a la casa, a criar a Sofía, y así se me fue pasando la juventud, sin darme cuenta."},
    {who:"maria", text:"Y los golpes… esos empezaron hace años. Al principio era un empujón, un grito. Con el tiempo se fue poniendo peor."},
    {who:"narrador", text:"Óigame esto bien, porque aquí es donde el cuento pega el timonazo: María Catalina no vino a contar un episodio, vino cargando una historia de años. Y apenas estábamos oyendo la primera capa."}
  ],
  legal:null, flow:null
},
{
  id:"trasfondo", kicker:"Lo que nadie sabía", title:"Separados… pero el peligro no se fue",
  eyebrow:"Espacio Violeta — sala privada", art:scenePrivateRoom("var(--gold)"), accent:"var(--gold)",
  lines:[
    {who:"maria", text:"Hace unos días nos separamos de verdad. Ahora vivo donde mi mamá, con Sofía. Pero él no me deja tranquila: me manda mensajes diciendo que vuelva a la casa, o que si no, él va a ir por mí."},
    {who:"maria", text:"Una noche intentó entrar a la fuerza donde mi mamá. Gracias a Dios los vecinos hicieron bulla y él se fue. Si no, no sé qué hubiera pasado."},
    {who:"maria", text:"Y hace ocho días me lo encontré en la galería, haciendo mercado. Ahí fue que me alcanzó a golpear, delante de toda la gente. Este morado es de eso, y todavía no me sana bien."},
    {who:"maria", text:"Yo siento que corro peligro. Y no solo yo: también mi mamá, y Sofía."},
    {who:"narrador", text:"Y ahí quedó plantado el nudo del caso: separación, amenazas, un intento de violación de domicilio, y una agresión en plena calle, hace apenas una semana. Pilas, futuro abogado, porque esto apenas va empezando."}
  ],
  legal:{title:"Por qué esto no es «solo una cuota de alimentos»", items:[
    "Las amenazas de volver por la fuerza, sumadas al intento de ingreso a la vivienda, son <em>indicadores de riesgo grave e inminente</em>.",
    "El <em>control económico</em> sostenido durante el matrimonio también es una forma reconocida de violencia intrafamiliar.",
    "Un caso puede necesitar varias rutas a la vez: alimentos para Sofía, protección para toda la familia, salud y, eventualmente, denuncia penal."
  ]}, flow:null
},
{
  id:"equipo", kicker:"Entre bastidores", title:"Valentina consulta a la profesora Alexandra",
  eyebrow:"Sala de casos — Consultorio Jurídico", art:sceneTeam(), accent:"var(--teal)",
  lines:[
    {who:"valentina", text:"Profesora Alexandra, el caso que traía María Catalina no era solo una cuota de alimentos. Hay amenazas, un intento de entrar a la fuerza a la casa de la mamá, y una agresión hace ocho días en la galería."},
    {who:"equipo", text:"Buen trabajo evitando que lo repita dos veces. Vamos a mirar, paso por paso, qué rutas se activan antes de volver donde ella."},
    {who:"narrador", text:"Y así, mientras Vivian acompañaba a María Catalina, Valentina y la profesora Alexandra empezaban a trazar el mapa jurídico del caso, sin dejarla sola ni un momento."}
  ],
  legal:null, flow:null
},
{
  id:"salud", kicker:"Paso 3 · ¿Necesita atención médica?", title:"Ese golpe todavía no ha sanado",
  eyebrow:"IPS — Urgencias", art:sceneHospital(), accent:"var(--teal)",
  lines:[
    {who:"valentina", text:"María Catalina, del golpe de hace ocho días, ¿la revisaron en algún centro médico?"},
    {who:"maria", text:"No. Me daba miedo ir, pensé que primero me iban a exigir poner la denuncia. Y la verdad, el cachete todavía no me ha sanado bien."},
    {who:"vivian", text:"Eso no es así. Así hayan pasado varios días, la tienen que atender ya mismo, sin pedirle nada de eso primero."}
  ],
  legal:{title:"Marco normativo", items:[
    "La violencia sexual e intrafamiliar es una <em>urgencia médica</em>, sin importar el tiempo transcurrido (Art. 23, Ley 1719 de 2014).",
    "La salud <em>no puede exigir</em> una denuncia penal como requisito previo para atender a la víctima (Res. 459 de 2012).",
    "El sector salud brinda: valoración médica integral, atención psicológica, prevención de ITS y orientación en derechos sexuales."
  ]},
  flow:{accent:"var(--teal)", branches:[
    {label:"Ruta de salud", nodes:["Espacio Violeta","IPS / Hospital / Urgencias","Valoración médica y psicológica"]}
  ]}
},
{
  id:"riesgo", kicker:"Paso 4 · ¿Existe riesgo actual?", title:"El nudo más apretado: la seguridad",
  eyebrow:"Comisaría de Familia", art:sceneComisaria(), accent:"var(--terracotta)",
  lines:[
    {who:"valentina", text:"Necesito preguntarle algo importante, con toda la calma: ¿usted cree que él puede volver a hacerle daño, a usted o a su familia?"},
    {who:"maria", text:"Sí, doctora. Después de lo de la galería y de lo que intentó donde mi mamá, yo de verdad siento que corremos peligro las tres."},
    {who:"narrador", text:"Ahí quedó clara la prioridad número uno: la seguridad de María Catalina, de Sofía y de la abuela. Y esa, óigame bien, no tiene que esperar a que se resuelva ningún proceso penal."}
  ],
  legal:{title:"Marco normativo", items:[
    "La protección puede solicitarse <em>antes</em> de presentar la denuncia penal (Ley 1719 de 2014).",
    "Si el riesgo ocurre en el contexto familiar, aplica la <em>Comisaría de Familia</em> (Ley 2126 de 2021 y Ley 1257 de 2008).",
    "Si el riesgo es grave o inmediato — como un intento de ingreso a la vivienda —, se activa la <em>Línea 123 — Policía Nacional</em>, sin perjuicio de activar Fiscalía y Salud simultáneamente.",
    "La misma Comisaría de Familia es competente para fijar, de manera independiente, la <em>cuota de alimentos</em> de Sofía."
  ]},
  flow:{accent:"var(--terracotta)", branches:[
    {label:"Contexto familiar", nodes:["Comisaría de Familia","Órdenes: alejamiento, desalojo, protección policial","Fijación de cuota de alimentos"]},
    {label:"Riesgo grave o inmediato", nodes:["Policía Nacional · Línea 123","Activa Fiscalía + Salud + Protección"]}
  ]}
},
{
  id:"hija", kicker:"Paso 5 · ¿Hay una niña, niño o adolescente?", title:"Sofía, doce años, también tiene miedo",
  eyebrow:"Ruta de restablecimiento de derechos", art:sceneRoute("var(--gold)"), accent:"var(--gold)",
  lines:[
    {who:"maria", text:"Mi hija Sofía tiene doce años y vive conmigo donde mi mamá desde que nos separamos. La dejé allá hoy pa' venir sola hasta acá."},
    {who:"maria", text:"Ella estaba en la casa la noche que él intentó entrar a la fuerza. Desde entonces no se quiere despegar de mí, y le da miedo hasta ir sola al colegio."},
    {who:"vivian", text:"Gracias por contarnos eso. Sofía también necesita una ruta propia de atención, no solo usted."},
    {who:"narrador", text:"Y así, lo que llegó como una cuota de alimentos, resultó siendo el caso de una familia entera. Una misma historia puede necesitar tocar varias puertas al mismo tiempo."}
  ],
  legal:{title:"Marco normativo", items:[
    "Cuando hay un niño, niña o adolescente involucrado existe un <em>deber reforzado</em> de protección.",
    "Puede acudirse directamente a la <em>Línea 141 del ICBF</em> para activación integral entre salud, protección y justicia.",
    "No debe manejarse como una consulta jurídica ordinaria: el Consultorio debe promover la activación institucional inmediata."
  ]},
  flow:{accent:"var(--gold)", branches:[
    {label:"Ruta para Sofía", nodes:["Espacio Violeta","Sector salud (atención urgente)","ICBF / Defensoría de Familia","Fiscalía (denuncia penal)"]}
  ]}
},
{
  id:"penal", kicker:"Paso 6 · Ruta penal", title:"Golpes, amenazas y una puerta forzada: ¿eso es delito?",
  eyebrow:"Fiscalía General de la Nación", art:sceneFiscalia(), accent:"var(--rose)",
  lines:[
    {who:"maria", text:"¿Y lo de la galería, y lo de esa noche que intentó entrar donde mi mamá, eso es delito? ¿Toca ir derechito a la Fiscalía?"},
    {who:"valentina", text:"Eso se valora jurídicamente según los hechos: la agresión, las amenazas y el intento de ingreso a la vivienda pueden constituir varios delitos distintos. Le vamos a explicar el camino completo, no solo a dónde ir."},
    {who:"narrador", text:"Porque el papel del Consultorio no es soltar un «vaya a la Fiscalía» y ya. Es orientar, explicar despacio, acompañar de la mano, y jamás hacerla sentir culpable de nada."}
  ],
  legal:{title:"Canales para la denuncia", items:["URI, SAU, CAIVAS, CAPIV o Policía Judicial.", "El ICBF identifica estas mismas autoridades como puntos para poner en conocimiento hechos de violencia sexual."]},
  flow:{accent:"var(--rose)", branches:[
    {label:"Proceso penal", nodes:["1 · Denuncia","2 · Investigación penal","3 · Actos investigativos","4 · Eventual imputación","5 · Acusación","6 · Juicio"]}
  ]}
},
{
  id:"derechos", kicker:"Paso 7 · Orientación jurídica individual", title:"Lo que a María Catalina le pertenece",
  eyebrow:"Derechos de la víctima", art:scenePrivateRoom("var(--gold)"), accent:"var(--gold)",
  lines:[
    {who:"valentina", text:"María Catalina, usted tiene derecho a recibir información clara, a su intimidad y dignidad, a la atención integral y a la protección."},
    {who:"valentina", text:"También tiene derecho a acceder a la justicia sin que nadie la haga sentir culpable de lo que le pasó — ni por el miedo, ni por la plata, ni por los años que aguantó callada."},
    {who:"narrador", text:"Y por primera vez en toda la tarde, María Catalina respiró distinto. No estaba resolviendo su vida entera ese viernes, pero ya no estaba cargando el peso ella sola."}
  ],
  legal:{title:"Derechos de la víctima (Ley 1257 de 2008)", items:["Recibir información","Intimidad y dignidad","Atención integral","Protección","Acceder a la justicia","No ser revictimizada"]},
  flow:null
},
{
  id:"seguimiento", kicker:"Paso 8 · Acompañamiento y seguimiento", title:"Que ningún caso se quede a medias",
  eyebrow:"Después de la remisión", art:sceneTeam(), accent:"var(--teal)",
  lines:[
    {who:"equipo", text:"Registremos la actuación de hoy, y confirmemos que la remisión a salud y a la Comisaría sí llegó a buen puerto."},
    {who:"valentina", text:"O sea que esto no es solo remitirla y ya."},
    {who:"equipo", text:"No, para nada. Hay que verificar qué pasó con la remisión, si le otorgaron medidas de protección, cómo va la cuota de alimentos, y qué necesitan ella y Sofía de aquí en adelante."}
  ],
  legal:null,
  flow:{accent:"var(--teal)", branches:[
    {label:"Ruta de seguimiento", nodes:["Registrar la actuación realizada","Confirmar que la remisión fue recibida","Verificar medidas de protección","Determinar si se requiere nueva actuación","Hacer seguimiento dentro de las competencias del Consultorio"]}
  ]}
},
{
  id:"cierre", kicker:"Cierre del caso", title:"María Catalina sale del Consultorio, ya no sola",
  eyebrow:"Espacio Violeta · Consultorio Jurídico FUP", art:sceneClosing(), accent:"var(--rose)",
  lines:[
    {who:"narrador", text:"Cae la tarde sobre Santander de Quilichao, y María Catalina sale por la misma puerta por donde entró con un pie adentro y otro afuera… pero ya no sale igual."},
    {who:"narrador", text:"Ella llegó pensando que solo necesitaba arreglar una cuota de alimentos. Y terminó enseñándole al equipo algo mucho más grande: que detrás de un trámite sencillo, a veces, se esconde una vida entera en riesgo."},
    {who:"narrador", text:"Porque en el Consultorio Jurídico no basta con saberse la ley de memoria. Hay que saber qué preguntar, en qué momento, y cómo caminar al lado de alguien sin soltarle la mano."}
  ],
  legal:null, flow:null, closing:true
}
];

/* ============ STATE ============ */
let current = 0;
let muted = false;
let speaking = false;
let speechQueue = [];

const railEl = document.getElementById('rail');
const stageEl = document.getElementById('stage');
const muteBtn = document.getElementById('muteToggle');
const themeBtn = document.getElementById('themeToggle');

try{
  const savedTheme = localStorage.getItem('ev_theme');
  if(savedTheme){ document.documentElement.setAttribute('data-theme', savedTheme); }
  const savedMute = localStorage.getItem('ev_muted');
  if(savedMute === '1'){ muted = true; }
}catch(e){}

/* ============ RAIL ============ */
function renderRail(){
  railEl.innerHTML = chapters.map((c,i)=>{
    const cls = i===current ? 'is-active' : (i<current ? 'is-done' : '');
    const num = c.id==='hook' ? '·' : (c.id==='cierre' ? '✓' : (i));
    return `<button class="rail__item ${cls}" data-i="${i}" aria-current="${i===current?'true':'false'}">
      <b>${c.id==='hook'?'○':(c.id==='cierre'?'●':i)}</b>${escapeHtml(c.kicker.replace(/^Paso \d+ · /,''))}
    </button>`;
  }).join('');
  railEl.querySelectorAll('.rail__item').forEach(btn=>{
    btn.addEventListener('click', ()=> goTo(parseInt(btn.dataset.i,10)) );
  });
  const active = railEl.querySelector('.is-active');
  if(active) active.scrollIntoView({inline:'center', block:'nearest', behavior:'smooth'});
}

function escapeHtml(s){ return s.replace(/[&<>]/g, c=>({'&':'&amp;','<':'&lt;','>':'&gt;'}[c])); }

/* ============ STAGE RENDER ============ */
function chapterHtml(c, i){
  if(i===0 && c.id==='hook'){
    return `
    <div class="cover">
      <div class="cover__content">
        <span class="cover__eyebrow">Ruta Jurídica · Espacio Violeta</span>
        <h1>El caso de <i>María Catalina</i></h1>
        <p>Una historia ficticia, pensada para que los estudiantes del Consultorio Jurídico aprendan, paso a paso, cómo activar la ruta de atención frente a un caso de violencia intrafamiliar.</p>
        <div class="cover__meta">
          <span>Consultorio Jurídico FUP · Sede Norte</span>
          <span>Santander de Quilichao, Cauca</span>
          <span>8 pasos de la ruta</span>
        </div>
        <div class="cover__actions">
          <button class="btn btn--primary" id="startBtn">Entrar al caso ${arrowIcon()}</button>
          <span class="cover__hint">Incluye narración en voz alta — actívala cuando quieras desde el ícono de sonido.</span>
        </div>
      </div>
    </div>`;
  }
  return `
  <div class="scene">
    <div class="scene__art" style="background:linear-gradient(200deg, ${c.accent}22, transparent 60%)">
      <span class="scene__eyebrow">${escapeHtml(c.eyebrow)}</span>
      ${c.art}
    </div>
    <div class="scene__body">
      <p class="scene__kicker">${escapeHtml(c.kicker)}</p>
      <h2 class="scene__title">${escapeHtml(c.title)}</h2>
      <div class="dialogue">
        ${c.lines.map(l=>`
          <div class="line line--${l.who}">
            <div class="line__avatar">${AVA[l.who]}</div>
            <div class="line__text"><span class="line__who">${WHO[l.who]}</span>${escapeHtml(l.text)}</div>
          </div>`).join('')}
      </div>
      ${c.legal ? `
        <div class="legalbox">
          <h4>${legalIcon()} ${escapeHtml(c.legal.title)}</h4>
          <ul>${c.legal.items.map(t=>`<li>${t}</li>`).join('')}</ul>
        </div>` : ``}
      ${c.flow ? `
        <div class="flow">
          <div class="flow__branches">
            ${c.flow.branches.map(b=>`
              <div class="flow__branch">
                <h5>${escapeHtml(b.label)}</h5>
                ${b.nodes.map((n,idx)=>`<div class="flow__node ${idx===b.nodes.length-1?'accent':''}" style="--accent:${c.flow.accent}">${escapeHtml(n)}</div>`).join('')}
              </div>`).join('')}
          </div>
        </div>` : ``}
      ${c.closing ? closingBlock() : ``}
    </div>
  </div>`;
}

function closingBlock(){
  return `
  <div class="closing-grid">
    <div><b>1</b>Recepción segura</div>
    <div><b>2</b>Valoración inicial</div>
    <div><b>3</b>Atención en salud</div>
    <div><b>4</b>Riesgo actual</div>
    <div><b>5</b>NNA involucrado</div>
    <div><b>6</b>Ruta penal</div>
    <div><b>7</b>Orientación jurídica</div>
    <div><b>8</b>Acompañamiento y seguimiento</div>
  </div>
  <div class="reflect">¿Usted, como estudiante del Consultorio, habría sabido qué hacer en ese momento? — Espacio Violeta: te escuchamos, te orientamos, te acompañamos.</div>
  `;
}

function arrowIcon(){return `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M5 12h14M13 6l6 6-6 6" stroke-linecap="round" stroke-linejoin="round"/></svg>`;}
function legalIcon(){return `<svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" style="vertical-align:-2px"><path d="M12 3v18M5 8l-3 6a4 4 0 0 0 6 0L5 8ZM19 8l-3 6a4 4 0 0 0 6 0l-3-6ZM5 8h14M8 21h8" stroke-linecap="round" stroke-linejoin="round"/></svg>`;}

function footHtml(i){
  const c = chapters[i];
  const isCover = i===0 && c.id==='hook';
  return `
  <div class="stage__foot">
    <div class="caption" id="caption">${isCover? 'Toca «Entrar al caso» para comenzar.' : 'Toca reproducir para escuchar la narración de esta escena.'}</div>
    <div class="stage__actions">
      ${isCover? `` : `
      <button class="btn" id="playBtn">${speakerIcon()} Reproducir</button>
      <div class="nav-arrows">
        <button class="btn btn--ghost" id="prevBtn" ${i===0?'disabled':''} aria-label="Anterior">${backIcon()}</button>
        <button class="btn btn--primary" id="nextBtn">${i===chapters.length-1? 'Volver al inicio' : 'Siguiente'} ${i===chapters.length-1?'':arrowIcon()}</button>
      </div>`}
    </div>
  </div>`;
}
function speakerIcon(){return `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M4 9v6h3.6L13 19V5L7.6 9H4z" stroke-linejoin="round"/></svg>`;}
function backIcon(){return `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M19 12H5M11 6l-6 6 6 6" stroke-linecap="round" stroke-linejoin="round"/></svg>`;}

function render(){
  cancelSpeech();
  const c = chapters[current];
  stageEl.innerHTML = chapterHtml(c,current) + footHtml(current);
  renderRail();

  const startBtn = document.getElementById('startBtn');
  if(startBtn) startBtn.addEventListener('click', ()=> goTo(1) );

  const playBtn = document.getElementById('playBtn');
  if(playBtn) playBtn.addEventListener('click', ()=> speakChapter(c) );

  const prevBtn = document.getElementById('prevBtn');
  if(prevBtn) prevBtn.addEventListener('click', ()=> goTo(current-1) );

  const nextBtn = document.getElementById('nextBtn');
  if(nextBtn) nextBtn.addEventListener('click', ()=> {
    if(current===chapters.length-1){ goTo(0); } else { goTo(current+1); }
  });

  stageEl.scrollIntoView({behavior:'smooth', block:'start'});
}

function goTo(i){
  if(i<0 || i>=chapters.length) return;
  current = i;
  render();
}

/* ============ SPEECH ============ */
function pickVoice(){
  if(!('speechSynthesis' in window)) return null;
  const voices = window.speechSynthesis.getVoices();
  if(!voices || !voices.length) return null;
  const latam = ['es-CO','es-419','es-MX','es-US','es-EC','es-PE','es-VE','es-AR','es-CL'];
  let v = voices.find(v=> /colombia/i.test(v.name) || /es[-_]CO/i.test(v.lang));
  if(!v) v = voices.find(v=> latam.includes((v.lang||'').replace('_','-')));
  if(!v) v = voices.find(v=> v.lang && v.lang.toLowerCase().startsWith('es') && !/es[-_]ES/i.test(v.lang));
  if(!v) v = voices.find(v=> v.lang && v.lang.toLowerCase().startsWith('es'));
  return v || null;
}
function cancelSpeech(){
  if('speechSynthesis' in window){ window.speechSynthesis.cancel(); }
  speechQueue = []; speaking = false;
}
function speakChapter(c){
  if(muted) return;
  if(!('speechSynthesis' in window)){
    setCaption('La narración por voz no está disponible en este navegador — el texto ya está en pantalla.');
    return;
  }
  cancelSpeech();
  const voice = pickVoice();
  const items = c.lines.slice();
  let idx = 0;
  function next(){
    if(idx>=items.length){ setCaption('Fin de la narración de esta escena.'); speaking=false; return; }
    const l = items[idx++];
    setCaption(`<b>${WHO[l.who]}:</b> ${l.text}`);
    const u = new SpeechSynthesisUtterance(l.text);
    if(voice) u.voice = voice;
    u.lang = voice ? voice.lang : 'es-ES';
    u.rate = l.who==='narrador' ? 0.9 : 0.98;
    u.pitch = l.who==='maria' ? 0.92 : (l.who==='valentina' ? 1.08 : (l.who==='vivian' ? 1.02 : 0.97));
    u.onend = next;
    u.onerror = next;
    speechSynthesis.speak(u);
  }
  speaking = true;
  next();
}
function setCaption(html){
  const cap = document.getElementById('caption');
  if(cap) cap.innerHTML = html;
}

/* ============ TOGGLES ============ */
function updateMuteIcon(){
  muteBtn.style.opacity = muted ? '.55' : '1';
  muteBtn.setAttribute('aria-pressed', muted ? 'true':'false');
}
muteBtn.addEventListener('click', ()=>{
  muted = !muted;
  if(muted) cancelSpeech();
  try{ localStorage.setItem('ev_muted', muted?'1':'0'); }catch(e){}
  updateMuteIcon();
});
themeBtn.addEventListener('click', ()=>{
  const cur = document.documentElement.getAttribute('data-theme');
  const next = cur==='light' ? 'dark' : 'light';
  document.documentElement.setAttribute('data-theme', next);
  try{ localStorage.setItem('ev_theme', next); }catch(e){}
});

document.addEventListener('keydown', (e)=>{
  if(e.key==='ArrowRight') goTo(Math.min(current+1, chapters.length-1));
  if(e.key==='ArrowLeft') goTo(Math.max(current-1,0));
});

if('speechSynthesis' in window){
  window.speechSynthesis.onvoiceschanged = ()=>{};
}

updateMuteIcon();
render();
})();
</script>
</body>
</html>
