<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🎰 Lucky 7 Casino</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;500;700&display=swap" rel="stylesheet">
<style>
  :root {
    --gold: #FFD700;
    --gold-dark: #B8860B;
    --red: #FF2244;
    --bg: #0a0a0f;
    --panel: #12121a;
    --neon-green: #39ff14;
    --neon-blue: #00e5ff;
    --text: #f0e6c8;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

<body> {
    background: var(--bg);
    font-family: 'Rajdhani', sans-serif;
    color: var(--text);
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    overflow-x: hidden;
    position: relative;
    padding: 16px;
  } </body>

  <body>::before {
    content: '';
    position: fixed;
    inset: 0;
    background:
      radial-gradient(ellipse at 20% 50%, rgba(255,34,68,0.07) 0%, transparent 60%),
      radial-gradient(ellipse at 80% 50%, rgba(255,215,0,0.07) 0%, transparent 60%),
      radial-gradient(ellipse at 50% 100%, rgba(0,229,255,0.05) 0%, transparent 50%);
    pointer-events: none;
    z-index: 0;
  }</body>

  .stars {
    position: fixed;
    inset: 0;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
  }

  .star {
    position: absolute;
    background: rgba(255,215,0,0.4);
    border-radius: 50%;
    animation: twinkle var(--d, 3s) ease-in-out infinite;
    animation-delay: var(--delay, 0s);
  }

  @keyframes twinkle {
    0%, 100% { opacity: 0.2; transform: scale(1); }
    50% { opacity: 1; transform: scale(1.6); }
  }

  .casino-wrapper {
    position: relative;
    z-index: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 18px;
    max-width: 500px;
    width: 100%;
  }

  /* TITLE */
  .casino-title { text-align: center; }

  .casino-title h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(2.8rem, 9vw, 4.2rem);
    letter-spacing: 0.15em;
    background: linear-gradient(135deg, #B8860B 0%, #FFD700 30%, #fff9c0 50%, #FFD700 70%, #B8860B 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    filter: drop-shadow(0 0 18px rgba(255,215,0,0.55));
    line-height: 1;
  }

  .casino-title .sub {
    font-family: 'Orbitron', monospace;
    font-size: 0.6rem;
    letter-spacing: 0.45em;
    color: var(--red);
    text-shadow: 0 0 10px var(--red);
    text-transform: uppercase;
    margin-top: 3px;
  }

  /* MACHINE */
  .machine {
    width: 100%;
    background: linear-gradient(160deg, #1e1e30 0%, #14142a 60%, #1c1c2e 100%);
    border: 2px solid rgba(255,215,0,0.2);
    border-radius: 22px;
    padding: 22px 18px 18px;
    box-shadow:
      0 0 0 1px rgba(255,215,0,0.08),
      0 0 50px rgba(255,215,0,0.07),
      inset 0 1px 0 rgba(255,255,255,0.04),
      0 25px 70px rgba(0,0,0,0.7);
    position: relative;
    overflow: hidden;
  }

  .machine::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(255,215,0,0.5), transparent);
  }

  /* BALANCE ROW */
  .balance-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 16px;
    padding: 10px 14px;
    background: rgba(0,0,0,0.35);
    border-radius: 10px;
    border: 1px solid rgba(255,215,0,0.12);
  }

  .bal-block { display: flex; flex-direction: column; gap: 2px; }
  .bal-block.right { align-items: flex-end; }

  .bal-label {
    font-family: 'Orbitron', monospace;
    font-size: 0.55rem;
    letter-spacing: 0.2em;
    color: rgba(255,215,0,0.5);
    text-transform: uppercase;
  }

  .bal-value {
    font-family: 'Orbitron', monospace;
    font-size: 1.25rem;
    font-weight: 700;
    color: var(--gold);
    text-shadow: 0 0 12px rgba(255,215,0,0.4);
    transition: color 0.2s;
  }

  .bal-value.small { font-size: 0.95rem; color: rgba(255,255,255,0.5); text-shadow: none; }

  @keyframes flashGold {
    0%, 100% { color: var(--gold); }
    50% { color: #fff; text-shadow: 0 0 30px var(--gold); }
  }

  .bal-value.flash { animation: flashGold 0.4s ease; }

  /* BET */
  .bet-row {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    margin-bottom: 16px;
  }

  .bet-label {
    font-family: 'Orbitron', monospace;
    font-size: 0.58rem;
    letter-spacing: 0.2em;
    color: rgba(255,255,255,0.35);
  }

  .bet-btn {
    width: 30px; height: 30px;
    border-radius: 50%;
    border: 1px solid rgba(255,215,0,0.35);
    background: rgba(255,215,0,0.07);
    color: var(--gold);
    font-size: 1.1rem;
    font-weight: 700;
    cursor: pointer;
    transition: all 0.15s;
    display: flex; align-items: center; justify-content: center;
    padding: 0; line-height: 1;
  }

  .bet-btn:hover:not(:disabled) {
    background: rgba(255,215,0,0.18);
    border-color: var(--gold);
    box-shadow: 0 0 10px rgba(255,215,0,0.25);
    transform: scale(1.1);
  }

  .bet-btn:disabled { opacity: 0.25; cursor: not-allowed; transform: none; }

  .bet-val {
    font-family: 'Orbitron', monospace;
    font-size: 1.05rem;
    font-weight: 700;
    color: var(--gold);
    min-width: 52px;
    text-align: center;
  }

  /* GRID */
  .reels-wrap {
    background: rgba(0,0,0,0.55);
    border-radius: 16px;
    padding: 10px;
    border: 1px solid rgba(255,255,255,0.04);
    box-shadow: inset 0 2px 25px rgba(0,0,0,0.6);
    margin-bottom: 16px;
  }

  .reels-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 1fr);
    gap: 8px;
  }

  .cell {
    background: linear-gradient(145deg, #0c0c1e, #181830);
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: clamp(2rem, 6.5vw, 2.8rem);
    border: 1px solid rgba(255,255,255,0.05);
    box-shadow: inset 0 2px 8px rgba(0,0,0,0.5);
    aspect-ratio: 1;
    user-select: none;
    transition: border-color 0.3s, box-shadow 0.3s;
    position: relative;
    overflow: hidden;
  }

  .cell.spinning {
    animation: cellSpin 0.1s linear infinite;
  }

  @keyframes cellSpin {
    0%   { transform: translateY(-5px) scale(0.95); opacity: 0.6; }
    50%  { transform: translateY(5px) scale(1.02); opacity: 1; }
    100% { transform: translateY(-5px) scale(0.95); opacity: 0.6; }
  }

  .cell.land {
    animation: cellLand 0.35s cubic-bezier(0.34, 1.56, 0.64, 1);
  }

  @keyframes cellLand {
    0%   { transform: scale(1.4) rotate(-5deg); }
    60%  { transform: scale(0.9) rotate(2deg); }
    100% { transform: scale(1) rotate(0deg); }
  }

  .cell.win-glow {
    border-color: var(--gold) !important;
    box-shadow:
      0 0 0 2px rgba(255,215,0,0.3),
      0 0 25px rgba(255,215,0,0.6),
      inset 0 0 15px rgba(255,215,0,0.12) !important;
    animation: winPulse 0.9s ease-in-out infinite;
  }

  @keyframes winPulse {
    0%, 100% { box-shadow: 0 0 0 2px rgba(255,215,0,0.3), 0 0 20px rgba(255,215,0,0.5), inset 0 0 10px rgba(255,215,0,0.1); }
    50%       { box-shadow: 0 0 0 2px rgba(255,215,0,0.5), 0 0 40px rgba(255,215,0,0.85), inset 0 0 20px rgba(255,215,0,0.2); }
  }

  /* MESSAGE */
  .msg-box {
    min-height: 54px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 14px;
  }

  .msg {
    font-family: 'Orbitron', monospace;
    font-size: clamp(0.68rem, 2.3vw, 0.9rem);
    font-weight: 700;
    letter-spacing: 0.1em;
    text-align: center;
    opacity: 0;
    transform: translateY(8px) scale(0.95);
    transition: opacity 0.3s, transform 0.3s;
  }

  .msg.show {
    opacity: 1;
    transform: translateY(0) scale(1);
  }

  .msg.t-jackpot {
    color: var(--gold);
    text-shadow: 0 0 25px var(--gold);
    font-size: clamp(1rem, 3.5vw, 1.35rem);
    animation: msgShake 0.35s ease infinite;
  }

  @keyframes msgShake {
    0%, 100% { transform: translateX(0) scale(1.03); }
    30% { transform: translateX(-3px) scale(1.06); }
    70% { transform: translateX(3px) scale(1.06); }
  }

  .msg.t-mega   { color: #FFB300; text-shadow: 0 0 18px #FFB300; }
  .msg.t-bigwin { color: #00E5FF; text-shadow: 0 0 15px #00E5FF; }
  .msg.t-win    { color: var(--neon-green); text-shadow: 0 0 12px var(--neon-green); }
  .msg.t-lose   { color: rgba(255,255,255,0.3); }
  .msg.t-info   { color: rgba(255,215,0,0.6); }

  /* SPIN BTN */
  .spin-btn {
    width: 100%;
    height: 60px;
    border: none;
    border-radius: 13px;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.7rem;
    letter-spacing: 0.22em;
    cursor: pointer;
    background: linear-gradient(135deg, #aa001a 0%, #ff2244 35%, #ff5870 55%, #cc0022 100%);
    color: #fff;
    box-shadow: 0 4px 24px rgba(255,34,68,0.45), inset 0 1px 0 rgba(255,255,255,0.15);
    text-shadow: 0 1px 3px rgba(0,0,0,0.5);
    position: relative;
    overflow: hidden;
    transition: all 0.2s;
  }

  .spin-btn::after {
    content: '';
    position: absolute;
    top: 0; left: -120%;
    width: 60%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.14), transparent);
    transition: left 0.45s ease;
  }

  .spin-btn:hover:not(:disabled)::after { left: 160%; }
  .spin-btn:hover:not(:disabled) {
    transform: translateY(-2px);
    box-shadow: 0 8px 32px rgba(255,34,68,0.6), inset 0 1px 0 rgba(255,255,255,0.15);
  }
  .spin-btn:active:not(:disabled) { transform: translateY(1px); }
  .spin-btn:disabled {
    opacity: 0.55;
    cursor: not-allowed;
    transform: none;
  }

  /* REFILL */
  .refill-btn {
    display: none;
    margin-top: 8px;
    width: 100%;
    height: 42px;
    border: 1px solid rgba(0,229,255,0.35);
    border-radius: 10px;
    background: rgba(0,229,255,0.05);
    color: var(--neon-blue);
    font-family: 'Orbitron', monospace;
    font-size: 0.68rem;
    letter-spacing: 0.18em;
    cursor: pointer;
    transition: all 0.2s;
  }

  .refill-btn.show { display: block; }
  .refill-btn:hover {
    background: rgba(0,229,255,0.1);
    border-color: var(--neon-blue);
    box-shadow: 0 0 15px rgba(0,229,255,0.18);
  }

  /* STATS */
  .stats-row {
    display: flex;
    justify-content: center;
    gap: 28px;
  }

  .stat { text-align: center; }
  .stat-num {
    font-family: 'Orbitron', monospace;
    font-size: 1rem;
    font-weight: 700;
    color: var(--text);
  }
  .stat-name {
    font-size: 0.58rem;
    letter-spacing: 0.18em;
    color: rgba(255,255,255,0.28);
    text-transform: uppercase;
    margin-top: 2px;
  }

  /* PAYTABLE */
  .paytable {
    width: 100%;
    background: rgba(0,0,0,0.2);
    border: 1px solid rgba(255,215,0,0.1);
    border-radius: 14px;
    padding: 14px 16px;
  }

  .pt-title {
    font-family: 'Orbitron', monospace;
    font-size: 0.53rem;
    letter-spacing: 0.38em;
    color: rgba(255,215,0,0.45);
    text-align: center;
    text-transform: uppercase;
    margin-bottom: 10px;
  }

  .pt-grid {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .pt-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 5px 8px;
    border-radius: 7px;
    transition: background 0.15s;
  }
  .pt-row:hover { background: rgba(255,255,255,0.03); }

  .pt-emojis { font-size: 0.9rem; }
  .pt-desc { font-size: 0.68rem; color: rgba(255,255,255,0.4); flex: 1; padding: 0 8px; }
  .pt-mult {
    font-family: 'Orbitron', monospace;
    font-size: 0.72rem;
    font-weight: 700;
    color: var(--gold);
    white-space: nowrap;
  }
  .pt-mult.red { color: rgba(255,255,255,0.25); }

  /* JACKPOT OVERLAY */
  .jk-overlay {
    position: fixed;
    inset: 0;
    z-index: 1000;
    display: flex;
    align-items: center;
    justify-content: center;
    pointer-events: none;
    opacity: 0;
    transition: opacity 0.35s;
  }

  .jk-overlay.active {
    opacity: 1;
    pointer-events: auto;
  }

  .jk-overlay::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse at center, rgba(255,215,0,0.18) 0%, rgba(0,0,0,0.88) 70%);
  }

  .jk-content {
    position: relative;
    text-align: center;
    animation: jkIn 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  }

  @keyframes jkIn {
    from { transform: scale(0.2) rotate(-15deg); opacity: 0; }
    to   { transform: scale(1) rotate(0deg); opacity: 1; }
  }

  .jk-content h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(4.5rem, 18vw, 9rem);
    background: linear-gradient(135deg, #B8860B 0%, #FFD700 30%, #ffffff 55%, #FFD700 75%, #B8860B 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    filter: drop-shadow(0 0 35px rgba(255,215,0,0.85));
    letter-spacing: 0.05em;
    line-height: 0.95;
  }

  .jk-amount {
    font-family: 'Orbitron', monospace;
    font-size: clamp(1.5rem, 5.5vw, 2.5rem);
    font-weight: 900;
    color: var(--gold);
    text-shadow: 0 0 30px var(--gold);
    margin-top: 10px;
  }

  .jk-tap {
    margin-top: 24px;
    font-family: 'Orbitron', monospace;
    font-size: 0.72rem;
    letter-spacing: 0.22em;
    color: rgba(255,255,255,0.45);
    animation: tapBlink 1.1s ease infinite;
  }

  @keyframes tapBlink {
    0%, 100% { opacity: 0.4; }
    50% { opacity: 1; }
  }

  /* CONFETTI */
  .confetti-bit {
    position: fixed;
    pointer-events: none;
    z-index: 998;
    animation: confettiFall linear forwards;
  }

  @keyframes confettiFall {
    0%   { transform: translateY(-30px) rotate(0deg) scale(1); opacity: 1; }
    80%  { opacity: 0.8; }
    100% { transform: translateY(105vh) rotate(900deg) scale(0.5); opacity: 0; }
  }

  @media (max-width: 380px) {
    .casino-wrapper { gap: 14px; }
    .machine { padding: 16px 12px 14px; }
  }
</style>
</head>
<body>

<!-- Stars -->
<div class="stars" id="starsEl"></div>

<!-- Jackpot overlay -->
<div class="jk-overlay" id="jkOverlay" onclick="closeJackpot()">
  <div class="jk-content">
    <h2>JACKPOT!</h2>
    <div class="jk-amount" id="jkAmount">+5000 💰</div>
    <div class="jk-tap">— НАЖМИТЕ ДЛЯ ПРОДОЛЖЕНИЯ —</div>
  </div>
</div>

<div class="casino-wrapper">

  <!-- Title -->
  <div class="casino-title">
    <h1>🎰 LUCKY 7</h1>
    <div class="sub">Vegas Fortune Casino</div>
  </div>

  <!-- Machine -->
  <div class="machine">

    <!-- Balance -->
    <div class="balance-row">
      <div class="bal-block">
        <span class="bal-label">Баланс</span>
        <span class="bal-value" id="balEl">1000 💰</span>
      </div>
      <div class="bal-block right">
        <span class="bal-label">Выиграно</span>
        <span class="bal-value small" id="wonEl">0 💰</span>
      </div>
    </div>

    <!-- Bet -->
    <div class="bet-row">
      <span class="bet-label">СТАВКА</span>
      <button class="bet-btn" id="betDownBtn">−</button>
      <span class="bet-val" id="betEl">10</span>
      <button class="bet-btn" id="betUpBtn">+</button>
    </div>

    <!-- 3×3 Grid -->
    <div class="reels-wrap">
      <div class="reels-grid" id="gridEl"></div>
    </div>

    <!-- Message -->
    <div class="msg-box">
      <div class="msg t-info" id="msgEl">Нажмите КРУТИТЬ, чтобы начать!</div>
    </div>

    <!-- Buttons -->
    <button class="spin-btn" id="spinBtn">🎰 КРУТИТЬ</button>
    <button class="refill-btn" id="refillBtn">↺ ПОПОЛНИТЬ БАЛАНС (+1000)</button>

  </div>

  <!-- Stats -->
  <div class="stats-row">
    <div class="stat">
      <div class="stat-num" id="sSpins">0</div>
      <div class="stat-name">Спинов</div>
    </div>
    <div class="stat">
      <div class="stat-num" id="sWins">0</div>
      <div class="stat-name">Побед</div>
    </div>
    <div class="stat">
      <div class="stat-num" id="sJack">0</div>
      <div class="stat-name">Джекпотов</div>
    </div>
  </div>

  <!-- Paytable -->
  <div class="paytable">
    <div class="pt-title">⬥ Таблица выплат ⬥</div>
    <div class="pt-grid">
      <div class="pt-row"><span class="pt-emojis">🎰🎰🎰</span><span class="pt-desc">Три слота в ряд</span><span class="pt-mult">×50 JACKPOT</span></div>
      <div class="pt-row"><span class="pt-emojis">7️⃣7️⃣7️⃣</span><span class="pt-desc">Три семёрки</span><span class="pt-mult">×20 MEGA</span></div>
      <div class="pt-row"><span class="pt-emojis">💎💎💎</span><span class="pt-desc">Три бриллианта</span><span class="pt-mult">×15</span></div>
      <div class="pt-row"><span class="pt-emojis">⭐⭐⭐</span><span class="pt-desc">Три звезды</span><span class="pt-mult">×10</span></div>
      <div class="pt-row"><span class="pt-emojis">🍒🍒🍒</span><span class="pt-desc">Три вишни</span><span class="pt-mult">×8</span></div>
      <div class="pt-row"><span class="pt-emojis">🔔🔔🔔</span><span class="pt-desc">Три колокола</span><span class="pt-mult">×6</span></div>
      <div class="pt-row"><span class="pt-emojis">🍋🍋🍋</span><span class="pt-desc">Три лимона</span><span class="pt-mult">×4</span></div>
      <div class="pt-row"><span class="pt-emojis">💰💰💰</span><span class="pt-desc">Три мешка</span><span class="pt-mult">×3</span></div>
      <div class="pt-row"><span class="pt-emojis">🍀🍀🍀</span><span class="pt-desc">Три клевера</span><span class="pt-mult">×2</span></div>
      <div class="pt-row"><span class="pt-emojis">❌❌❌</span><span class="pt-desc">Три крестика</span><span class="pt-mult red">×0 — ПРОВАЛ</span></div>
    </div>
  </div>

</div>

<script>
(function () {
  // ─── CONFIG ───────────────────────────────────────────────────────────────
  const SYMBOLS = [
    { e: '🎰', w: 1,  m: 50  },
    { e: '7️⃣', w: 2,  m: 20  },
    { e: '💎', w: 3,  m: 15  },
    { e: '⭐', w: 5,  m: 10  },
    { e: '🍒', w: 8,  m: 8   },
    { e: '🔔', w: 10, m: 6   },
    { e: '🍋', w: 12, m: 4   },
    { e: '💰', w: 15, m: 3   },
    { e: '🍀', w: 18, m: 2   },
    { e: '❌', w: 30, m: 0   },
  ];

  // Weighted pool
  const POOL = [];
  SYMBOLS.forEach(s => { for (let i = 0; i < s.w; i++) POOL.push(s); });

  // Win lines (indices in the 3×3 grid)
  const LINES = [
    [0,1,2], [3,4,5], [6,7,8],   // rows
    [0,3,6], [1,4,7], [2,5,8],   // cols
    [0,4,8], [2,4,6],             // diags
  ];

  // ─── STATE ────────────────────────────────────────────────────────────────
  let balance  = 1000;
  let bet      = 10;
  let totalWon = 0;
  let spins    = 0;
  let wins     = 0;
  let jackpots = 0;
  let spinning = false;

  // ─── DOM REFS ─────────────────────────────────────────────────────────────
  const balEl      = document.getElementById('balEl');
  const wonEl      = document.getElementById('wonEl');
  const betEl      = document.getElementById('betEl');
  const betDownBtn = document.getElementById('betDownBtn');
  const betUpBtn   = document.getElementById('betUpBtn');
  const gridEl     = document.getElementById('gridEl');
  const msgEl      = document.getElementById('msgEl');
  const spinBtn    = document.getElementById('spinBtn');
  const refillBtn  = document.getElementById('refillBtn');
  const jkOverlay  = document.getElementById('jkOverlay');
  const jkAmount   = document.getElementById('jkAmount');
  const sSpins     = document.getElementById('sSpins');
  const sWins      = document.getElementById('sWins');
  const sJack      = document.getElementById('sJack');

  const cells = [];

  // ─── INIT ─────────────────────────────────────────────────────────────────
  function init() {
    // Build grid
    for (let i = 0; i < 9; i++) {
      const div = document.createElement('div');
      div.className = 'cell';
      div.textContent = '🎲';
      gridEl.appendChild(div);
      cells.push(div);
    }

    // Stars
    const starsEl = document.getElementById('starsEl');
    for (let i = 0; i < 90; i++) {
      const s = document.createElement('div');
      s.className = 'star';
      const size = 1 + Math.random() * 2.5;
      s.style.cssText = `
        left:${Math.random()*100}%;t
