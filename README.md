<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Madhuva — No effort. Just health.</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
<script src="https://tally.so/widgets/embed.js" async></script>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --ink: #111010;
    --ink-soft: #4a4745;
    --ink-faint: #9b9794;
    --paper: #faf9f7;
    --warm: #f0ebe3;
    --accent: #c8a97e;
    --rule: #e5e0d8;
    --serif: 'Playfair Display', Georgia, serif;
    --sans: 'DM Sans', sans-serif;
  }
  html { scroll-behavior: smooth; }
  body {
    background: var(--paper);
    color: var(--ink);
    font-family: var(--sans);
    font-size: 17px;
    line-height: 1.7;
    font-weight: 300;
    -webkit-font-smoothing: antialiased;
  }

  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 22px 48px;
    background: rgba(250,249,247,0.9);
    backdrop-filter: blur(14px);
    border-bottom: 1px solid transparent;
    transition: border-color 0.3s;
  }
  nav.scrolled { border-color: var(--rule); }
  .logo { font-family: var(--serif); font-size: 20px; font-weight: 400; color: var(--ink); text-decoration: none; letter-spacing: -0.01em; }
  .nav-cta {
    font-size: 13px; font-weight: 500; letter-spacing: 0.06em; text-transform: uppercase;
    color: var(--ink); text-decoration: none; border-bottom: 1px solid var(--ink);
    padding-bottom: 1px; transition: opacity 0.2s; cursor: pointer; background: none; border-left: none; border-right: none; border-top: none;
  }
  .nav-cta:hover { opacity: 0.45; }

  .wrap { max-width: 720px; margin: 0 auto; padding: 0 40px; }

  .hero { padding: 200px 40px 140px; max-width: 720px; margin: 0 auto; }
  .eyebrow { font-size: 12px; font-weight: 500; letter-spacing: 0.12em; text-transform: uppercase; color: var(--accent); margin-bottom: 32px; opacity: 0; animation: fadeUp 0.8s ease forwards 0.1s; }
  .hero h1 { font-family: var(--serif); font-size: clamp(52px, 8vw, 84px); font-weight: 400; line-height: 1.05; letter-spacing: -0.02em; margin-bottom: 36px; opacity: 0; animation: fadeUp 0.9s ease forwards 0.25s; }
  .hero h1 em { font-style: italic; color: var(--ink-soft); }
  .hero-sub { font-size: 18px; line-height: 1.8; color: var(--ink-soft); max-width: 520px; margin-bottom: 20px; opacity: 0; animation: fadeUp 0.9s ease forwards 0.38s; }
  .hero-sub2 { font-size: 18px; line-height: 1.8; color: var(--ink-soft); max-width: 520px; margin-bottom: 56px; opacity: 0; animation: fadeUp 0.9s ease forwards 0.48s; }
  .hero-sub2 strong { color: var(--ink); font-weight: 500; }
  .cta-row { display: flex; align-items: center; gap: 28px; opacity: 0; animation: fadeUp 0.9s ease forwards 0.58s; }
  .btn {
    display: inline-block; background: var(--ink); color: var(--paper);
    font-size: 14px; font-weight: 500; letter-spacing: 0.04em;
    padding: 16px 36px; text-decoration: none; border-radius: 2px;
    transition: opacity 0.2s, transform 0.2s; cursor: pointer;
    border: none; font-family: var(--sans);
  }
  .btn:hover { opacity: 0.78; transform: translateY(-1px); }
  .cta-note { font-size: 13px; color: var(--ink-faint); }

  .section { padding: 112px 40px; }
  .section.warm { background: var(--warm); border-top: 1px solid var(--rule); border-bottom: 1px solid var(--rule); }
  .s-label { font-size: 11px; font-weight: 500; letter-spacing: 0.14em; text-transform: uppercase; color: var(--ink-faint); margin-bottom: 44px; display: flex; align-items: center; gap: 14px; }
  .s-label::after { content: ''; flex: 1; height: 1px; background: var(--rule); max-width: 56px; }
  h2 { font-family: var(--serif); font-size: clamp(30px, 4.5vw, 46px); font-weight: 400; line-height: 1.15; letter-spacing: -0.015em; margin-bottom: 28px; }
  h2 em { font-style: italic; color: var(--ink-soft); }
  .body-text p { color: var(--ink-soft); margin-bottom: 18px; max-width: 540px; line-height: 1.78; }
  .body-text p:last-child { margin-bottom: 0; }
  .body-text p strong { color: var(--ink); font-weight: 500; }

  .pullquote { border-left: 2px solid var(--accent); padding: 4px 0 4px 28px; margin: 48px 0 0; }
  .pullquote p { font-family: var(--serif); font-size: 21px; font-style: italic; line-height: 1.55; color: var(--ink); max-width: 460px; }

  .adapt-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1px; background: var(--rule); margin-top: 56px; border: 1px solid var(--rule); }
  .adapt-cell { padding: 32px 28px; background: var(--warm); transition: background 0.22s; }
  .adapt-cell:hover { background: #e8e0d4; }
  .cell-label { font-size: 11px; font-weight: 500; letter-spacing: 0.11em; text-transform: uppercase; color: var(--accent); margin-bottom: 10px; }
  .adapt-cell p { font-size: 15px; color: var(--ink-soft); line-height: 1.65; max-width: 100%; margin: 0; }

  .vision-list { margin-top: 44px; }
  .vision-item { display: flex; gap: 22px; padding: 28px 0; border-bottom: 1px solid var(--rule); }
  .vision-item:first-child { padding-top: 0; }
  .vision-item:last-child { border-bottom: none; padding-bottom: 0; }
  .v-num { font-family: var(--serif); font-size: 13px; color: var(--ink-faint); padding-top: 3px; flex-shrink: 0; width: 20px; }
  .v-text { font-size: 16px; line-height: 1.72; color: var(--ink-soft); }
  .v-text strong { color: var(--ink); font-weight: 500; }

  .final-cta { text-align: center; padding: 140px 40px; }
  .final-cta h2 { max-width: 420px; margin: 0 auto 20px; }
  .final-cta .body-text p { max-width: 380px; margin: 0 auto 48px; text-align: center; }
  .final-cta .cta-row { justify-content: center; opacity: 1; animation: none; }

  footer { border-top: 1px solid var(--rule); padding: 30px 48px; display: flex; justify-content: space-between; align-items: center; }
  .footer-logo { font-family: var(--serif); font-size: 16px; color: var(--ink); }
  .footer-meta { font-size: 12px; color: var(--ink-faint); line-height: 1.9; text-align: right; }

  .reveal { opacity: 0; transform: translateY(22px); transition: opacity 0.72s ease, transform 0.72s ease; }
  .reveal.visible { opacity: 1; transform: none; }
  .reveal-d1 { transition-delay: 0.08s; }
  .reveal-d2 { transition-delay: 0.18s; }

  @keyframes fadeUp { from { opacity:0; transform:translateY(20px); } to { opacity:1; transform:none; } }

  @media (max-width: 620px) {
    nav { padding: 18px 22px; }
    .hero, .section, .final-cta { padding-left: 22px; padding-right: 22px; }
    .hero { padding-top: 130px; }
    .adapt-grid { grid-template-columns: 1fr; }
    footer { flex-direction: column; gap: 10px; text-align: center; }
    .footer-meta { text-align: center; }
  }
</style>
</head>
<body>

<nav id="nav">
  <a href="#" class="logo">Madhuva</a>
  <button class="nav-cta" data-tally-open="jaJyXx" data-tally-overlay="1" data-tally-emoji-text="👋" data-tally-emoji-animation="wave">Join waitlist</button>
</nav>

<!-- HERO -->
<div class="hero">
  <p class="eyebrow">Early access · Building in public</p>
  <h1>No effort.<br><em>Just health.</em></h1>
  <p class="hero-sub">You already know what to do. The problem is everything else — the job, the family, the Tuesday that went sideways. Health knowledge isn't rare. Time and structure are.</p>
  <p class="hero-sub2">Madhuva is a system that <strong>works even when you don't.</strong></p>
  <div class="cta-row">
    <button class="btn" data-tally-open="jaJyXx" data-tally-overlay="1" data-tally-emoji-text="👋" data-tally-emoji-animation="wave">Join the waitlist</button>
    <span class="cta-note">Free · No spam</span>
  </div>
</div>

<!-- PROBLEM -->
<div class="section">
  <div class="wrap">
    <div class="reveal">
      <p class="s-label">The real problem</p>
      <h2>Health isn't difficult.<br><em>Consistency is.</em></h2>
    </div>
    <div class="body-text reveal reveal-d1">
      <p>Nobody fails at health because the information was hard to find. They fail because life is relentless and routines are fragile.</p>
      <p>The friction isn't the habit — it's everything that has to go right before you even start it. The planning. The remembering. The deciding, over and over, whether today is the day.</p>
      <p>That effort compounds quietly. And eventually, it beats you.</p>
    </div>
  </div>
</div>

<!-- INSIGHT -->
<div class="section warm">
  <div class="wrap">
    <div class="reveal">
      <p class="s-label">A different way of thinking</p>
      <h2>Willpower is<br><em>not a strategy.</em></h2>
    </div>
    <div class="body-text reveal reveal-d1">
      <p>Every health product is secretly a bet on your discipline. Eat this. Track that. Don't break the streak. They dress it up differently, but the model is the same: you provide the effort, the app provides the nudge.</p>
      <p>That model works until it doesn't. Willpower has a daily limit. Motivation has a half-life. A system built on either one will fail you — usually when things are already hard.</p>
      <p><strong>The question isn't how to make you more disciplined. It's how to make discipline unnecessary.</strong></p>
    </div>
    <div class="pullquote reveal reveal-d2">
      <p>"The friction isn't in the habit itself. It's in deciding to do it, every single day."</p>
    </div>
  </div>
</div>

<!-- SOLUTION -->
<div class="section">
  <div class="wrap">
    <div class="reveal">
      <p class="s-label">What Madhuva is</p>
      <h2>A system that holds<br><em>the structure for you.</em></h2>
    </div>
    <div class="body-text reveal reveal-d1">
      <p>Madhuva isn't an app that tracks what you do. It's a system that reduces how much you have to do in the first place — fewer decisions, fewer reminders, less overhead.</p>
      <p>We're starting with diabetes management — a condition where the gap between knowing and doing has real consequences. Where consistency isn't optional.</p>
      <p>The goal is simple: make staying on track feel like doing nothing at all.</p>
    </div>
  </div>
</div>

<!-- INTELLIGENCE -->
<div class="section warm">
  <div class="wrap">
    <div class="reveal">
      <p class="s-label">How it works</p>
      <h2>Built to adapt,<br><em>not just deliver.</em></h2>
    </div>
    <div class="body-text reveal reveal-d1">
      <p>Most systems hand you a plan and wait to see if you follow it. Madhuva watches what actually happens — and adjusts.</p>
      <p>It learns when you eat, when you slip, what your week actually looks like. Over time, it builds a picture that no fixed plan could anticipate. And it uses that to do the work of staying on track, so you don't have to.</p>
      <p><strong>You don't adapt to it. It adapts to you.</strong></p>
    </div>
    <div class="adapt-grid reveal reveal-d2">
      <div class="adapt-cell">
        <p class="cell-label">Learns patterns</p>
        <p>Understands your actual rhythms — not the ones you planned for.</p>
      </div>
      <div class="adapt-cell">
        <p class="cell-label">Adjusts automatically</p>
        <p>When your week changes, the system changes with it.</p>
      </div>
      <div class="adapt-cell">
        <p class="cell-label">Reduces decisions</p>
        <p>Fewer things to remember means fewer things to skip.</p>
      </div>
      <div class="adapt-cell">
        <p class="cell-label">Gets better over time</p>
        <p>The longer you use it, the less effort it takes from you.</p>
      </div>
    </div>
  </div>
</div>

<!-- VISION -->
<div class="section">
  <div class="wrap">
    <div class="reveal">
      <p class="s-label">Where this is going</p>
      <h2>Health that runs<br><em>in the background.</em></h2>
    </div>
    <div class="body-text reveal reveal-d1">
      <p>The version of health we're building toward doesn't ask much of you. No new habit, no new mindset, no changed identity.</p>
    </div>
    <div class="vision-list reveal reveal-d2">
      <div class="vision-item">
        <span class="v-num">01</span>
        <p class="v-text">Just a system that handles it — reliably, without fanfare — for the long term.</p>
      </div>
      <div class="vision-item">
        <span class="v-num">02</span>
        <p class="v-text">We're starting focused and going deep. <strong>Diabetes first</strong> — because the stakes are clear and the need is real. Then further.</p>
      </div>
      <div class="vision-item">
        <span class="v-num">03</span>
        <p class="v-text"><strong>The endgame:</strong> a version of your life where managing your health doesn't feel like a second job.</p>
      </div>
    </div>
  </div>
</div>

<!-- FINAL CTA -->
<div class="section warm">
  <div class="final-cta">
    <div class="reveal">
      <h2>We're building early.<br><em>Come be part of it.</em></h2>
      <div class="body-text">
        <p>The waitlist is free. We share openly as we build, and we want input from people who know this problem firsthand.</p>
      </div>
      <div class="cta-row">
        <button class="btn" data-tally-open="jaJyXx" data-tally-overlay="1" data-tally-emoji-text="👋" data-tally-emoji-animation="wave">Join the waitlist</button>
        <span class="cta-note">No pressure, ever.</span>
      </div>
    </div>
  </div>
</div>

<footer>
  <span class="footer-logo">Madhuva</span>
  <div class="footer-meta">
    Early stage &nbsp;·&nbsp; Building in public<br>
    <span style="color: var(--accent);">© 2026</span>
  </div>
</footer>

<script>
  const nav = document.getElementById('nav');
  window.addEventListener('scroll', () => {
    nav.classList.toggle('scrolled', window.scrollY > 40);
  }, { passive: true });

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>
</body>
</html>
