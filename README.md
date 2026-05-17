<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Madhuva — No effort. Just health.</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,500;0,600;1,400;1,500&family=Instrument+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
<script src="https://tally.so/widgets/embed.js" async></script>
<style>

/* ─── RESET & BASE ─────────────────────────────────────────── */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; font-size: 16px; }

:root {
  --black:    #0f0f0d;
  --dark:     #1c1c19;
  --mid:      #4a4a42;
  --muted:    #7a7a70;
  --border:   #e2ddd6;
  --bg:       #fafaf7;
  --warm:     #f4f0e8;
  --green:    #3a6b4a;
  --green-lt: #eef4f0;
  --green-md: #c2d9c9;

  --serif: 'Lora', Georgia, serif;
  --sans:  'Instrument Sans', sans-serif;
}

body {
  background: var(--bg);
  color: var(--dark);
  font-family: var(--sans);
  font-weight: 300;
  line-height: 1.72;
  -webkit-font-smoothing: antialiased;
}

/* ─── NAV ───────────────────────────────────────────────────── */
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 200;
  display: flex; align-items: center; justify-content: space-between;
  padding: 0 48px;
  height: 64px;
  background: rgba(250,250,247,0.92);
  backdrop-filter: blur(16px);
  border-bottom: 1px solid transparent;
  transition: border-color 0.4s;
}
nav.stuck { border-color: var(--border); }

.logo {
  font-family: var(--serif);
  font-size: 18px;
  font-weight: 500;
  color: var(--black);
  text-decoration: none;
  letter-spacing: -0.01em;
}
.logo span { color: var(--green); }

.nav-btn {
  font-family: var(--sans);
  font-size: 13px;
  font-weight: 500;
  letter-spacing: 0.04em;
  color: var(--bg);
  background: var(--green);
  border: none;
  padding: 9px 22px;
  border-radius: 100px;
  cursor: pointer;
  transition: opacity 0.2s, transform 0.15s;
}
.nav-btn:hover { opacity: 0.82; transform: translateY(-1px); }

/* ─── HERO ──────────────────────────────────────────────────── */
.hero {
  min-height: 100svh;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  padding: 0 48px 80px;
  position: relative;
  overflow: hidden;
}

.hero-bg {
  position: absolute; inset: 0; z-index: 0;
  background:
    radial-gradient(ellipse 60% 55% at 75% 30%, rgba(58,107,74,0.07) 0%, transparent 70%),
    radial-gradient(ellipse 50% 40% at 20% 70%, rgba(194,217,201,0.12) 0%, transparent 65%);
}

/* Grain texture overlay */
.hero-bg::after {
  content: '';
  position: absolute; inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.035'/%3E%3C/svg%3E");
  background-size: 128px;
  opacity: 0.6;
  pointer-events: none;
}

.hero-inner { position: relative; z-index: 1; max-width: 860px; }

.hero-tag {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-size: 12px;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--green);
  margin-bottom: 36px;
  opacity: 0;
  animation: up 0.7s ease forwards 0.1s;
}
.hero-tag::before {
  content: '';
  width: 20px; height: 1px;
  background: var(--green);
}

.hero h1 {
  font-family: var(--serif);
  font-size: clamp(52px, 7.5vw, 92px);
  font-weight: 400;
  line-height: 1.04;
  letter-spacing: -0.025em;
  color: var(--black);
  margin-bottom: 32px;
  opacity: 0;
  animation: up 0.85s ease forwards 0.22s;
}
.hero h1 em {
  font-style: italic;
  color: var(--green);
}

.hero-sub {
  font-size: clamp(16px, 1.6vw, 19px);
  line-height: 1.75;
  color: var(--mid);
  max-width: 560px;
  margin-bottom: 48px;
  opacity: 0;
  animation: up 0.85s ease forwards 0.38s;
}

.hero-sub strong { color: var(--dark); font-weight: 400; }

.hero-actions {
  display: flex;
  align-items: center;
  gap: 24px;
  opacity: 0;
  animation: up 0.85s ease forwards 0.52s;
}

.btn-primary {
  font-family: var(--sans);
  font-size: 14px;
  font-weight: 500;
  letter-spacing: 0.03em;
  color: var(--bg);
  background: var(--black);
  border: none;
  padding: 15px 34px;
  border-radius: 3px;
  cursor: pointer;
  transition: background 0.2s, transform 0.15s;
}
.btn-primary:hover { background: var(--green); transform: translateY(-1px); }

.btn-ghost {
  font-size: 13px;
  color: var(--muted);
  display: flex;
  align-items: center;
  gap: 6px;
}
.btn-ghost svg { opacity: 0.5; }

.hero-scroll {
  position: absolute;
  bottom: 80px; right: 48px;
  z-index: 1;
  writing-mode: vertical-lr;
  font-size: 11px;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--muted);
  display: flex;
  align-items: center;
  gap: 10px;
  opacity: 0;
  animation: fade 1s ease forwards 1s;
}
.hero-scroll::after {
  content: '';
  width: 1px; height: 40px;
  background: var(--border);
}

/* ─── LAYOUT HELPERS ────────────────────────────────────────── */
.container { max-width: 760px; margin: 0 auto; padding: 0 40px; }
.container-wide { max-width: 1040px; margin: 0 auto; padding: 0 40px; }

section { padding: 100px 0; }
section.tinted { background: var(--warm); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
section.green-tint { background: var(--green-lt); border-top: 1px solid var(--green-md); border-bottom: 1px solid var(--green-md); }

.section-tag {
  font-size: 11px;
  font-weight: 500;
  letter-spacing: 0.13em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 40px;
  display: flex;
  align-items: center;
  gap: 12px;
}
.section-tag::before {
  content: '';
  width: 24px; height: 1px;
  background: var(--border);
  flex-shrink: 0;
}

h2 {
  font-family: var(--serif);
  font-size: clamp(28px, 4vw, 44px);
  font-weight: 400;
  line-height: 1.18;
  letter-spacing: -0.018em;
  color: var(--black);
  margin-bottom: 24px;
}
h2 em { font-style: italic; color: var(--mid); }

p.body { color: var(--mid); line-height: 1.78; margin-bottom: 18px; }
p.body:last-child { margin-bottom: 0; }
p.body strong { color: var(--dark); font-weight: 400; }

/* ─── PROBLEM ───────────────────────────────────────────────── */
.problem-split {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2px;
  margin-top: 56px;
  background: var(--border);
  border: 1px solid var(--border);
}
.prob-cell {
  background: var(--bg);
  padding: 36px 32px;
  transition: background 0.25s;
}
.prob-cell:hover { background: var(--green-lt); }
.prob-num {
  font-family: var(--serif);
  font-size: 36px;
  font-weight: 400;
  color: var(--border);
  line-height: 1;
  margin-bottom: 16px;
}
.prob-cell h3 {
  font-family: var(--serif);
  font-size: 18px;
  font-weight: 500;
  color: var(--black);
  margin-bottom: 10px;
  line-height: 1.3;
}
.prob-cell p { font-size: 15px; color: var(--mid); line-height: 1.68; }

/* ─── INSIGHT ───────────────────────────────────────────────── */
.insight-quote {
  border-left: 2px solid var(--green);
  padding: 8px 0 8px 32px;
  margin: 48px 0;
}
.insight-quote p {
  font-family: var(--serif);
  font-size: clamp(20px, 2.5vw, 26px);
  font-style: italic;
  line-height: 1.5;
  color: var(--dark);
}

/* ─── FOUNDER STORY ─────────────────────────────────────────── */
.story-wrapper {
  display: grid;
  grid-template-columns: 1fr 280px;
  gap: 64px;
  align-items: start;
}

.story-aside {
  background: var(--green-lt);
  border: 1px solid var(--green-md);
  border-radius: 4px;
  padding: 28px;
  position: sticky;
  top: 88px;
}
.aside-label {
  font-size: 10px;
  font-weight: 500;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: var(--green);
  margin-bottom: 20px;
}
.stat-row {
  display: flex;
  flex-direction: column;
  gap: 18px;
}
.stat {
  padding-bottom: 18px;
  border-bottom: 1px solid var(--green-md);
}
.stat:last-child { border-bottom: none; padding-bottom: 0; }
.stat-num {
  font-family: var(--serif);
  font-size: 32px;
  font-weight: 400;
  color: var(--green);
  line-height: 1;
  margin-bottom: 4px;
}
.stat-desc { font-size: 13px; color: var(--mid); line-height: 1.5; }

/* ─── SOLUTION ──────────────────────────────────────────────── */
.solution-list {
  margin-top: 48px;
  display: flex;
  flex-direction: column;
  gap: 0;
}
.sol-item {
  display: flex;
  gap: 24px;
  padding: 28px 0;
  border-bottom: 1px solid var(--border);
  align-items: flex-start;
}
.sol-item:first-child { padding-top: 0; border-top: 1px solid var(--border); }
.sol-icon {
  width: 36px; height: 36px;
  border-radius: 50%;
  background: var(--green-lt);
  border: 1px solid var(--green-md);
  display: flex; align-items: center; justify-content: center;
  flex-shrink: 0;
  margin-top: 2px;
  color: var(--green);
  font-size: 15px;
}
.sol-text h4 {
  font-family: var(--serif);
  font-size: 18px;
  font-weight: 500;
  color: var(--black);
  margin-bottom: 6px;
  line-height: 1.3;
}
.sol-text p { font-size: 15px; color: var(--mid); line-height: 1.68; }

/* ─── AI SECTION ────────────────────────────────────────────── */
.ai-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2px;
  background: var(--green-md);
  border: 1px solid var(--green-md);
  margin-top: 48px;
  border-radius: 4px;
  overflow: hidden;
}
.ai-cell {
  background: var(--green-lt);
  padding: 28px 24px;
  transition: background 0.22s;
}
.ai-cell:hover { background: #e4eee8; }
.ai-cell-label {
  font-size: 10px;
  font-weight: 500;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--green);
  margin-bottom: 10px;
}
.ai-cell p { font-size: 14px; color: var(--mid); line-height: 1.65; }

/* ─── CTA ───────────────────────────────────────────────────── */
.cta-section {
  text-align: center;
  padding: 120px 40px;
}
.cta-section h2 { max-width: 480px; margin: 0 auto 16px; }
.cta-section p.body { max-width: 400px; margin: 0 auto 44px; text-align: center; }
.cta-badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  font-size: 12px;
  color: var(--muted);
  background: var(--warm);
  border: 1px solid var(--border);
  padding: 6px 14px;
  border-radius: 100px;
  margin-top: 20px;
}
.cta-dot {
  width: 6px; height: 6px;
  border-radius: 50%;
  background: var(--green);
  animation: pulse 2s ease infinite;
}

/* ─── FOOTER ────────────────────────────────────────────────── */
footer {
  border-top: 1px solid var(--border);
  padding: 28px 48px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 12px;
}
.footer-left {
  font-family: var(--serif);
  font-size: 16px;
  color: var(--black);
}
.footer-left span { color: var(--green); }
.footer-right {
  font-size: 12px;
  color: var(--muted);
  text-align: right;
  line-height: 1.8;
}

/* ─── REVEAL ANIMATIONS ─────────────────────────────────────── */
.reveal {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.75s ease, transform 0.75s ease;
}
.reveal.in { opacity: 1; transform: none; }
.d1 { transition-delay: 0.1s; }
.d2 { transition-delay: 0.2s; }
.d3 { transition-delay: 0.3s; }

@keyframes up   { from { opacity:0; transform:translateY(18px); } to { opacity:1; transform:none; } }
@keyframes fade { from { opacity:0; } to { opacity:1; } }
@keyframes pulse {
  0%, 100% { transform: scale(1); opacity: 1; }
  50%       { transform: scale(1.4); opacity: 0.6; }
}

/* ─── MOBILE ────────────────────────────────────────────────── */
@media (max-width: 680px) {
  nav { padding: 0 22px; }
  .hero { padding: 0 22px 64px; }
  .hero-scroll { display: none; }
  .container, .container-wide { padding: 0 22px; }
  section { padding: 72px 0; }

  .problem-split { grid-template-columns: 1fr; }
  .story-wrapper { grid-template-columns: 1fr; }
  .story-aside { position: static; }
  .ai-grid { grid-template-columns: 1fr; }

  footer { flex-direction: column; text-align: center; padding: 24px 22px; }
  .footer-right { text-align: center; }
}

@media (max-width: 900px) and (min-width: 681px) {
  .story-wrapper { grid-template-columns: 1fr; }
  .story-aside { position: static; }
  .ai-grid { grid-template-columns: 1fr 1fr; }
}

</style>
</head>
<body>

<!-- ─── NAV ──────────────────────────────────────────────── -->
<nav id="nav">
  <a href="#" class="logo">Madhu<span>va</span></a>
  <button class="nav-btn"
    data-tally-open="jaJyXx"
    data-tally-overlay="1"
    data-tally-emoji-text="👋"
    data-tally-emoji-animation="wave">Get Early Access</button>
</nav>


<!-- ─── HERO ──────────────────────────────────────────────── -->
<div class="hero">
  <div class="hero-bg"></div>

  <div class="hero-inner">
    <p class="hero-tag">Early stage · Building in public</p>

    <h1>No effort.<br><em>Just health.</em></h1>

    <p class="hero-sub">
      Most people already know what to eat, how to move, and when to rest.
      The gap isn't knowledge — it's the <strong>daily effort of remembering and following through.</strong>
      Madhuva is a system built to close that gap, not by making you more disciplined,
      but by making discipline less necessary.
    </p>

    <div class="hero-actions">
      <button class="btn-primary"
        data-tally-open="jaJyXx"
        data-tally-overlay="1"
        data-tally-emoji-text="👋"
        data-tally-emoji-animation="wave">Get Early Access</button>
      <span class="btn-ghost">
        <svg width="14" height="14" viewBox="0 0 14 14" fill="none"><circle cx="7" cy="7" r="6" stroke="currentColor" stroke-width="1.2"/><path d="M7 4v3.5l2 1.5" stroke="currentColor" stroke-width="1.2" stroke-linecap="round"/></svg>
        Free · No obligations
      </span>
    </div>
  </div>

  <div class="hero-scroll">Scroll</div>
</div>


<!-- ─── PROBLEM ───────────────────────────────────────────── -->
<section>
  <div class="container">
    <div class="reveal">
      <p class="section-tag">The problem</p>
      <h2>You already know<br>what to do.</h2>
    </div>
    <div class="reveal d1">
      <p class="body">Eat better. Move more. Sleep well. Manage your stress. There's no shortage of advice — and most people genuinely know the basics.</p>
      <p class="body">The problem is what happens between knowing and actually doing it. Life fills that gap. Work runs late. Plans shift. And the routine you were building quietly disappears.</p>
      <p class="body">This isn't a willpower failure. It's a systems failure. The tools people use to stay healthy still demand too much of them — too much planning, too many decisions, too much energy that most people simply don't have at the end of the day.</p>
    </div>

    <div class="problem-split reveal d2">
      <div class="prob-cell">
        <div class="prob-num">01</div>
        <h3>Consistency, not knowledge</h3>
        <p>People don't fail because they don't know enough. They fail because staying consistent requires more effort than life usually allows.</p>
      </div>
      <div class="prob-cell">
        <div class="prob-num">02</div>
        <h3>Routine is fragile</h3>
        <p>A single bad week can unwind months of habit. And building it back up requires the same effort all over again.</p>
      </div>
      <div class="prob-cell">
        <div class="prob-num">03</div>
        <h3>Friction is the real enemy</h3>
        <p>Most health tools add to your to-do list. They require you to track, log, plan, decide — every single day.</p>
      </div>
      <div class="prob-cell">
        <div class="prob-num">04</div>
        <h3>Discipline has a daily limit</h3>
        <p>Even motivated people run out of it. A system that relies on willpower will eventually fail — usually when you need it most.</p>
      </div>
    </div>
  </div>
</section>


<!-- ─── INSIGHT ───────────────────────────────────────────── -->
<section class="tinted">
  <div class="container">
    <div class="reveal">
      <p class="section-tag">The insight</p>
      <h2>Most health systems<br>are built for <em>ideal conditions.</em></h2>
    </div>

    <div class="reveal d1">
      <p class="body">They assume you have time. They assume you have energy. They assume that if you just had the right reminder or the right meal plan, you'd follow through.</p>
      <p class="body">But real life doesn't work in ideal conditions. Real life is messy, inconsistent, and already demanding. Adding a health routine on top of that works for a few weeks, sometimes a few months — and then it doesn't.</p>
    </div>

    <div class="insight-quote reveal d2">
      <p>"The failure isn't the person. It's the system asking too much of them."</p>
    </div>

    <div class="reveal d3">
      <p class="body">Willpower is not a renewable resource. The more decisions a health system requires, the more likely it is to be abandoned. That's not a moral failing — that's just how humans work.</p>
      <p class="body">The systems that actually stick are the ones that ask almost nothing of you after the initial setup. The ones that become invisible. That's what we're building.</p>
    </div>
  </div>
</section>


<!-- ─── FOUNDER STORY ─────────────────────────────────────── -->
<section>
  <div class="container-wide">
    <div class="story-wrapper">

      <div>
        <div class="reveal">
          <p class="section-tag">How this started</p>
          <h2>I ran a small<br>experiment first.</h2>
        </div>

        <div class="reveal d1">
          <p class="body">About a year ago, I started preparing and delivering fresh health drinks to people managing diabetes in my city. I did everything myself — made the drinks each morning, found customers through direct conversations and a few pamphlets, and delivered everything door to door.</p>

          <p class="body">It wasn't a startup. It wasn't even a proper business. It was just me wanting to understand whether something like this could actually work in practice.</p>

          <p class="body">Over about four months, I built up around 20–30 regular paying customers. These weren't people I convinced with a pitch — they were people who tried it, liked it, and kept coming back. When I had to stop, a few of them genuinely asked if I'd restart.</p>

          <p class="body">What I learned wasn't about the drink. It was about what happens when you remove the effort from a healthy habit completely. People didn't have to plan anything, track anything, or decide anything. It just showed up. And because it showed up, they actually used it.</p>

          <p class="body">That's the idea behind Madhuva. Not a subscription box, not an app with streaks — a system that does the remembering and the friction-removal for you, so the healthy choice becomes the easiest choice.</p>
        </div>
      </div>

      <div class="story-aside reveal d2">
        <p class="aside-label">From the experiment</p>
        <div class="stat-row">
          <div class="stat">
            <div class="stat-num">20–30</div>
            <div class="stat-desc">Regular paying customers, all managing diabetes</div>
          </div>
          <div class="stat">
            <div class="stat-num">~4</div>
            <div class="stat-desc">Months of daily operations — production, delivery, and sales, all manual</div>
          </div>
          <div class="stat">
            <div class="stat-num">0</div>
            <div class="stat-desc">Customers who needed convincing to come back — they asked to restart on their own</div>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>


<!-- ─── SOLUTION ──────────────────────────────────────────── -->
<section class="tinted">
  <div class="container">
    <div class="reveal">
      <p class="section-tag">What we're building</p>
      <h2>A system, <em>not just a product.</em></h2>
    </div>

    <div class="reveal d1">
      <p class="body">Madhuva isn't an app that shows you a dashboard and hopes you stay motivated. It's a system designed to hold the structure so you don't have to.</p>
      <p class="body">We're starting with people managing diabetes — a condition where consistency isn't optional and the cost of slipping is real. It's a focused, specific problem, and that's intentional.</p>
    </div>

    <div class="solution-list reveal d2">
      <div class="sol-item">
        <div class="sol-icon">↓</div>
        <div class="sol-text">
          <h4>Fewer decisions, not more reminders</h4>
          <p>More notifications just add noise. We reduce the number of things you have to decide and remember in the first place.</p>
        </div>
      </div>
      <div class="sol-item">
        <div class="sol-icon">⟳</div>
        <div class="sol-text">
          <h4>Consistency without effort</h4>
          <p>The goal is to make the healthy option the default option — not through motivation, but through removing the friction of choosing it.</p>
        </div>
      </div>
      <div class="sol-item">
        <div class="sol-icon">◎</div>
        <div class="sol-text">
          <h4>Built for real life, not ideal conditions</h4>
          <p>No plans that assume perfect weeks. The system adapts to what's actually happening, not what was scheduled.</p>
        </div>
      </div>
      <div class="sol-item">
        <div class="sol-icon">→</div>
        <div class="sol-text">
          <h4>Starting focused, expanding slowly</h4>
          <p>Diabetes management first — because we've tested it, we understand it, and the stakes make it worth getting right before moving on.</p>
        </div>
      </div>
    </div>
  </div>
</section>


<!-- ─── AI SECTION ────────────────────────────────────────── -->
<section class="green-tint">
  <div class="container">
    <div class="reveal">
      <p class="section-tag">How it learns</p>
      <h2>Built to adapt,<br><em>not just deliver.</em></h2>
    </div>

    <div class="reveal d1">
      <p class="body">Over time, the system learns what your days actually look like — when you eat, when things slip, what your week tends to feel like. Not to judge it, but to work around it.</p>
      <p class="body">It's not a fixed plan you have to keep up with. It adjusts. The more you use it, the less you have to think about it.</p>
    </div>

    <div class="ai-grid reveal d2">
      <div class="ai-cell">
        <p class="ai-cell-label">Learns patterns</p>
        <p>Understands your actual rhythms over time — not the ones you intended to have.</p>
      </div>
      <div class="ai-cell">
        <p class="ai-cell-label">Adapts automatically</p>
        <p>When your routine changes, the system adjusts. You don't have to reconfigure anything.</p>
      </div>
      <div class="ai-cell">
        <p class="ai-cell-label">Gets quieter over time</p>
        <p>The longer you use it, the less you hear from it — because it's doing more in the background.</p>
      </div>
    </div>

    <div class="reveal d3" style="margin-top: 32px;">
      <p class="body" style="font-style: italic; color: var(--green); font-family: var(--serif);">You don't adapt to it. It adapts to you.</p>
    </div>
  </div>
</section>


<!-- ─── CTA ───────────────────────────────────────────────── -->
<section>
  <div class="cta-section reveal">
    <p class="section-tag" style="justify-content: center;">Early access</p>
    <h2>We're building this<br>carefully and <em>openly.</em></h2>
    <p class="body">This is early stage. We're looking for a small group of people who understand this problem firsthand and want to help shape how we solve it. No pressure — just an honest conversation about what might actually work.</p>
    <button class="btn-primary"
      data-tally-open="jaJyXx"
      data-tally-overlay="1"
      data-tally-emoji-text="👋"
      data-tally-emoji-animation="wave">Get Early Access</button>
    <div style="margin-top: 16px;">
      <span class="cta-badge">
        <span class="cta-dot"></span>
        Free · No obligations · We share openly as we build
      </span>
    </div>
  </div>
</section>


<!-- ─── FOOTER ────────────────────────────────────────────── -->
<footer>
  <div class="footer-left">Madhu<span>va</span></div>
  <div class="footer-right">
    Early stage &nbsp;·&nbsp; Building in public<br>
    © 2026
  </div>
</footer>


<script>
  // Nav on scroll
  const nav = document.getElementById('nav');
  window.addEventListener('scroll', () => {
    nav.classList.toggle('stuck', window.scrollY > 20);
  }, { passive: true });

  // Scroll reveal
  const els = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.classList.add('in'); io.unobserve(e.target); }
    });
  }, { threshold: 0.1 });
  els.forEach(el => io.observe(el));
</script>

</body>
</html>
