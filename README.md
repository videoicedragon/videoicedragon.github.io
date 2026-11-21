<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="theme-color" content="#10110f">
    <meta name="description" content="VideoIceDragon — Python and Linux developer building reliable desktop applications and practical tools.">
    <title>VideoIceDragon — Python &amp; Linux Developer</title>
    <style>
      :root {
        color-scheme: dark;
        --bg: #10110f;
        --surface: #181a17;
        --surface-raised: #1e211d;
        --text: #f0f0e9;
        --muted: #9c9f96;
        --line: rgba(235, 239, 223, .12);
        --lime: #d3f36b;
        --orange: #ff865e;
        --mono: "SFMono-Regular", Consolas, "Liberation Mono", monospace;
        --sans: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      }

      * { box-sizing: border-box; }
      html { scroll-behavior: smooth; scroll-padding-top: 6rem; }
      body {
        margin: 0;
        background:
          radial-gradient(ellipse at 82% 17%, rgba(108, 126, 54, .12), transparent 30rem),
          var(--bg);
        color: var(--text);
        font-family: var(--sans);
        -webkit-font-smoothing: antialiased;
      }

      a { color: inherit; text-decoration: none; }
      button { font: inherit; }
      .wrap { width: min(1120px, calc(100% - 48px)); margin-inline: auto; }
      .eyebrow {
        color: var(--lime);
        font: 500 .75rem/1.4 var(--mono);
        letter-spacing: .13em;
        text-transform: uppercase;
      }

      .site-header {
        position: sticky;
        z-index: 5;
        top: 0;
        border-bottom: 1px solid var(--line);
        background: rgba(16, 17, 15, .82);
        backdrop-filter: blur(18px);
      }
      .nav {
        min-height: 76px;
        display: flex;
        align-items: center;
        justify-content: space-between;
      }
      .brand { display: inline-flex; align-items: center; gap: 11px; font-weight: 680; letter-spacing: -.035em; }
      .brand-mark {
        display: grid;
        width: 31px;
        aspect-ratio: 1;
        place-items: center;
        border: 1px solid rgba(211, 243, 107, .38);
        border-radius: 9px;
        color: var(--lime);
        font: 700 .88rem var(--mono);
        transform: rotate(-5deg);
      }
      .nav-links { display: flex; align-items: center; gap: 34px; color: var(--muted); font-size: .88rem; }
      .nav-links a { transition: color .2s ease; }
      .nav-links a:hover, .nav-links a:focus-visible { color: var(--text); }
      .nav-links .nav-contact {
        padding: 10px 15px;
        border: 1px solid var(--line);
        border-radius: 7px;
        color: var(--text);
      }
      .menu-toggle {
        display: none;
        padding: 8px 10px;
        border: 1px solid var(--line);
        border-radius: 7px;
        background: transparent;
        color: var(--text);
        cursor: pointer;
      }

      .hero {
        position: relative;
        display: grid;
        min-height: min(740px, calc(100svh - 76px));
        grid-template-columns: 1.15fr .85fr;
        align-items: center;
        gap: 42px;
        padding-block: 88px 100px;
      }
      .hero-copy { position: relative; z-index: 1; }
      .availability { display: inline-flex; align-items: center; gap: 9px; margin-bottom: 28px; color: var(--muted); font: .76rem var(--mono); }
      .availability::before {
        width: 7px;
        height: 7px;
        border-radius: 50%;
        background: var(--lime);
        box-shadow: 0 0 13px rgba(211, 243, 107, .7);
        content: "";
      }
      h1 {
        max-width: 720px;
        margin: 0;
        font-size: clamp(3.5rem, 8.1vw, 7.4rem);
        font-weight: 620;
        letter-spacing: -.085em;
        line-height: .94;
      }
      h1 span { color: var(--lime); }
      .hero-copy > p {
        max-width: 470px;
        margin: 27px 0 0;
        color: var(--muted);
        font-size: clamp(1rem, 1.35vw, 1.12rem);
        line-height: 1.8;
      }
      .hero-actions { display: flex; flex-wrap: wrap; align-items: center; gap: 22px; margin-top: 34px; }
      .button {
        display: inline-flex;
        min-height: 48px;
        align-items: center;
        justify-content: center;
        gap: 11px;
        padding: 0 17px;
        border: 1px solid var(--lime);
        border-radius: 7px;
        background: var(--lime);
        color: #16190f;
        font-size: .88rem;
        font-weight: 650;
        transition: transform .2s ease, background .2s ease;
      }
      .button:hover { background: #e0ff7d; transform: translateY(-2px); }
      .text-link { color: var(--muted); font-size: .88rem; transition: color .2s ease; }
      .text-link:hover { color: var(--text); }
      .arrow { font-size: 1.1em; }

      .hero-art {
        position: relative;
        display: grid;
        min-height: 400px;
        place-items: center;
        isolation: isolate;
      }
      .hero-art::before, .hero-art::after {
        position: absolute;
        z-index: -1;
        width: min(30vw, 370px);
        aspect-ratio: 1;
        border: 1px solid rgba(211, 243, 107, .13);
        border-radius: 50%;
        content: "";
      }
      .hero-art::after { width: min(22vw, 270px); border-color: rgba(255, 134, 94, .2); }
      .orb {
        position: relative;
        display: grid;
        width: min(18vw, 210px);
        min-width: 165px;
        aspect-ratio: 1;
        place-items: center;
        overflow: hidden;
        border: 1px solid rgba(211, 243, 107, .6);
        border-radius: 36% 64% 57% 43% / 48% 38% 62% 52%;
        background: linear-gradient(145deg, #303925, #171b16 68%);
        box-shadow: 0 0 90px rgba(154, 189, 74, .13), inset 0 0 40px rgba(211, 243, 107, .08);
        animation: float 8s ease-in-out infinite;
      }
      .orb svg { width: 57%; color: var(--lime); filter: drop-shadow(0 0 20px rgba(211, 243, 107, .25)); }
      .orbit-label {
        position: absolute;
        padding: 8px 11px;
        border: 1px solid var(--line);
        border-radius: 6px;
        background: rgba(24, 26, 23, .88);
        color: #c8c9c1;
        font: .68rem var(--mono);
        letter-spacing: .03em;
      }
      .orbit-label.one { top: 17%; right: 2%; }
      .orbit-label.two { bottom: 17%; left: 0; color: var(--lime); }
      .orbit-label.three { right: 2%; bottom: 19%; color: var(--orange); }
      @keyframes float { 50% { transform: translateY(-12px) rotate(3deg); } }

      .section { padding-block: 105px; border-top: 1px solid var(--line); }
      .section-heading { display: flex; align-items: end; justify-content: space-between; gap: 30px; margin-bottom: 43px; }
      h2 { margin: 12px 0 0; font-size: clamp(2.2rem, 4vw, 3.5rem); font-weight: 570; letter-spacing: -.065em; line-height: 1.08; }
      .section-heading > p { max-width: 370px; margin: 0 0 4px; color: var(--muted); font-size: .95rem; line-height: 1.7; }

      .about-grid { display: grid; grid-template-columns: .8fr 1.2fr; gap: 80px; }
      .about-note { color: var(--muted); font: .78rem/1.8 var(--mono); }
      .about-copy { max-width: 650px; color: #c5c7be; font-size: 1.12rem; line-height: 1.9; }
      .about-copy p { margin: 0 0 20px; }
      .about-copy strong { color: var(--text); font-weight: 550; }
      .skill-list { display: flex; flex-wrap: wrap; gap: 9px; margin: 25px 0 0; padding: 0; list-style: none; }
      .skill-list li {
        padding: 8px 11px;
        border: 1px solid var(--line);
        border-radius: 6px;
        background: rgba(255, 255, 255, .025);
        color: #d3d5cb;
        font: .75rem var(--mono);
      }

      .cards { display: grid; grid-template-columns: repeat(3, 1fr); gap: 15px; }
      .card {
        min-height: 248px;
        padding: 25px;
        border: 1px solid var(--line);
        border-radius: 9px;
        background: linear-gradient(155deg, rgba(255,255,255,.025), transparent 60%), var(--surface);
        transition: border-color .2s ease, transform .2s ease;
      }
      .card:hover { transform: translateY(-4px); border-color: rgba(211, 243, 107, .38); }
      .card-index { color: var(--lime); font: .75rem var(--mono); }
      .card h3 { margin: 42px 0 10px; font-size: 1.17rem; font-weight: 570; letter-spacing: -.03em; }
      .card p { margin: 0; color: var(--muted); font-size: .9rem; line-height: 1.7; }

      .contact {
        position: relative;
        display: flex;
        min-height: 300px;
        align-items: center;
        justify-content: space-between;
        gap: 30px;
        overflow: hidden;
        padding: 48px;
        border: 1px solid var(--line);
        border-radius: 12px;
        background: radial-gradient(ellipse at 85% 50%, rgba(134, 158, 68, .15), transparent 42%), var(--surface);
      }
      .contact h2 { max-width: 570px; font-size: clamp(2.4rem, 5vw, 4.25rem); }
      .contact .button { flex: 0 0 auto; }
      .contact-note { margin: 16px 0 0; color: var(--muted); font-size: .92rem; }

      footer { padding-block: 27px; color: var(--muted); font: .72rem var(--mono); }
      .footer-inner { display: flex; align-items: center; justify-content: space-between; gap: 18px; }
      .footer-inner a { transition: color .2s ease; }
      .footer-inner a:hover { color: var(--lime); }

      :focus-visible { outline: 2px solid var(--lime); outline-offset: 4px; }
      @media (max-width: 760px) {
        .wrap { width: min(100% - 36px, 560px); }
        .nav { min-height: 68px; }
        .menu-toggle { display: inline-flex; }
        .nav-links {
          position: absolute;
          top: calc(100% + 1px);
          right: 0;
          left: 0;
          display: none;
          align-items: stretch;
          gap: 0;
          padding: 10px 18px 18px;
          border-bottom: 1px solid var(--line);
          background: var(--bg);
        }
        .nav-links.open { display: flex; flex-direction: column; }
        .nav-links a { padding: 13px 0; }
        .nav-links .nav-contact { margin-top: 6px; padding: 12px; text-align: center; }
        .hero { min-height: auto; grid-template-columns: 1fr; gap: 12px; padding-block: 78px 67px; }
        .hero-art { min-height: 290px; }
        .hero-art::before { width: 270px; }
        .hero-art::after { width: 205px; }
        .orb { width: 155px; min-width: 155px; }
        .orbit-label.one { right: 7%; }
        .orbit-label.two { left: 7%; }
        .orbit-label.three { right: 8%; }
        .section { padding-block: 75px; }
        .section-heading { align-items: start; flex-direction: column; gap: 15px; margin-bottom: 30px; }
        .about-grid { grid-template-columns: 1fr; gap: 22px; }
        .cards { grid-template-columns: 1fr; }
        .card { min-height: 210px; }
        .card h3 { margin-top: 31px; }
        .contact { align-items: start; flex-direction: column; padding: 30px 24px; }
      }
      @media (prefers-reduced-motion: reduce) {
        *, *::before, *::after { scroll-behavior: auto !important; animation-duration: .01ms !important; animation-iteration-count: 1 !important; transition-duration: .01ms !important; }
      }
    </style>
  </head>
  <body>
    <header class="site-header">
      <nav class="nav wrap" aria-label="Main navigation">
        <a class="brand" href="#top" aria-label="VideoIceDragon, home">
          <span class="brand-mark" aria-hidden="true">V</span>
          <span>VideoIceDragon</span>
        </a>
        <button class="menu-toggle" type="button" aria-expanded="false" aria-controls="nav-links">Menu</button>
        <div class="nav-links" id="nav-links">
          <a href="#about">About</a>
          <a href="#focus">What I do</a>
          <a class="nav-contact" href="#contact">Get in touch <span aria-hidden="true">↗</span></a>
        </div>
      </nav>
    </header>

    <main id="top">
      <section class="hero wrap" aria-labelledby="hero-title">
        <div class="hero-copy">
          <div class="availability">Python &amp; Linux developer</div>
          <h1 id="hero-title">Ideas into<br><span>real things.</span></h1>
          <p>I’m VideoIceDragon — building efficient, reliable software and practical desktop experiences with Python, Qt, and Linux.</p>
          <div class="hero-actions">
            <a class="button" href="#focus">Explore what I do <span class="arrow" aria-hidden="true">↓</span></a>
            <a class="text-link" href="#about">A little about me <span aria-hidden="true">↗</span></a>
          </div>
        </div>
        <div class="hero-art" aria-hidden="true">
          <span class="orbit-label one">curiosity.exe</span>
          <span class="orbit-label two">BUILD / LEARN</span>
          <span class="orbit-label three">v.∞</span>
          <div class="orb">
            <svg viewBox="0 0 120 120" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M22 78c17-3 27-16 31-31 6 8 15 11 25 8-2 9-8 15-17 19 13 3 25-2 34-12-2 20-17 33-38 34-13 1-25-5-35-18Z" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
              <path d="M47 48c-1-12 5-23 16-31-1 12 3 20 12 25M27 78l-8 12 17-4M83 56l16-10-4 19M60 86l-2 17 13-14" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
              <circle cx="71" cy="58" r="2" fill="currentColor"/>
            </svg>
          </div>
        </div>
      </section>

      <section class="section" id="about" aria-labelledby="about-title">
        <div class="wrap">
          <div class="about-grid">
            <div>
              <div class="eyebrow">01 / The person behind the pixels</div>
              <h2 id="about-title">Make it work.<br>Make it matter.</h2>
            </div>
            <div class="about-copy">
              <p>A Python and Linux developer focused on building <strong>efficient, reliable, and maintainable software.</strong> Experienced in desktop applications with Qt and PySide6, and comfortable across Linux environments, Python tooling, and cross-platform development.</p>
              <p>Interested in practical GUI solutions, open-source projects, and combining clean architecture with <strong>native-feeling interfaces.</strong></p>
              <ul class="skill-list" aria-label="Languages and technologies">
                <li>Python</li>
                <li>Linux</li>
                <li>Qt</li>
                <li>PySide6</li>
                <li>Bash</li>
                <li>Git</li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      <section class="section" id="focus" aria-labelledby="focus-title">
        <div class="wrap">
          <div class="section-heading">
            <div>
              <div class="eyebrow">02 / Areas of focus</div>
              <h2 id="focus-title">Things I like to make.</h2>
            </div>
            <p>From practical desktop interfaces to the tools and code that make them dependable.</p>
          </div>
          <div class="cards">
            <article class="card">
              <div class="card-index">01 — DESKTOP</div>
              <h3>Desktop applications</h3>
              <p>Practical Qt and PySide6 interfaces that feel at home on the desktop.</p>
            </article>
            <article class="card">
              <div class="card-index">02 — TOOLING</div>
              <h3>Python &amp; Linux tools</h3>
              <p>Useful scripts and applications designed to make everyday workflows smoother.</p>
            </article>
            <article class="card">
              <div class="card-index">03 — ENGINEERING</div>
              <h3>Reliable, maintainable code</h3>
              <p>Clean architecture and cross-platform thinking, with care for the details.</p>
            </article>
          </div>
        </div>
      </section>

      <section class="section" id="contact" aria-labelledby="contact-title">
        <div class="wrap">
          <div class="contact">
            <div>
              <div class="eyebrow">03 / Your turn</div>
              <h2 id="contact-title">Got an idea?<br>Let’s make it real.</h2>
              <p class="contact-note">I’m always up for a good idea and a new challenge.</p>
            </div>
            <a class="button" href="https://github.com/videoicedragon" target="_blank" rel="noopener noreferrer">
              Find me on GitHub <span class="arrow" aria-hidden="true">↗</span>
            </a>
          </div>
        </div>
      </section>
    </main>

    <footer>
      <div class="wrap footer-inner">
        <span>© <span id="year"></span> VideoIceDragon</span>
        <a href="#top">Back to the top ↑</a>
      </div>
    </footer>
    <script>
      const menuToggle = document.querySelector(".menu-toggle");
      const navLinks = document.querySelector(".nav-links");

      menuToggle.addEventListener("click", () => {
        const isOpen = menuToggle.getAttribute("aria-expanded") === "true";
        menuToggle.setAttribute("aria-expanded", String(!isOpen));
        navLinks.classList.toggle("open", !isOpen);
      });

      navLinks.addEventListener("click", (event) => {
        if (event.target.closest("a")) {
          menuToggle.setAttribute("aria-expanded", "false");
          navLinks.classList.remove("open");
        }
      });

      document.querySelector("#year").textContent = new Date().getFullYear();
    </script>
  </body>
</html>
