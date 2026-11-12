<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="A customizable homepage concept for a Japan healthcare guide.">
  <title>Hospital Guide Japan</title>

  <style>
    :root {
      --navy: #102746;
      --navy-light: #142B4A;
      --red: #C9363E;
      --red-dark: #A92731;
      --light-blue: #EAF0F7;
      --light-grey: #F3F6FA;
      --white: #FFFFFF;
      --muted: #64748B;
      --line: #DCE3EC;
      --shadow: 0 16px 45px rgba(16, 39, 70, .09);
      --radius: 20px;
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      background: var(--white);
      color: var(--navy-light);
      font-family: Inter, Arial, sans-serif;
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    button {
      font: inherit;
      cursor: pointer;
    }

    .container {
      width: min(1160px, calc(100% - 48px));
      margin: 0 auto;
    }

    /* TOP BAR */

    .topbar {
      background: var(--navy);
      color: white;
      font-size: .78rem;
    }

    .topbar-inner {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 16px;
      padding: 9px 0;
    }

    .topbar a {
      color: #F2A5A9;
      font-weight: 700;
    }

    /* NAVIGATION */

    header {
      position: sticky;
      top: 0;
      z-index: 20;
      background: rgba(255,255,255,.96);
      backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--line);
    }

    .nav {
      min-height: 78px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 12px;
      font-weight: 800;
      letter-spacing: -.04em;
      font-size: 1.12rem;
      white-space: nowrap;
    }

    .brand-mark {
      width: 40px;
      height: 40px;
      display: grid;
      place-items: center;
      border-radius: 13px;
      color: white;
      background: var(--red);
      font-size: 1.35rem;
    }

    .brand small {
      display: block;
      font-size: .62rem;
      letter-spacing: .12em;
      color: var(--muted);
      font-weight: 700;
      text-transform: uppercase;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 27px;
      color: #40536D;
      font-size: .88rem;
      font-weight: 650;
    }

    .nav-links a:hover {
      color: var(--red);
    }

    .language,
    .menu-toggle {
      border: 1px solid var(--line);
      background: white;
      color: var(--navy);
      padding: 9px 12px;
      border-radius: 999px;
    }

    .menu-toggle {
      display: none;
    }

    /* HERO */

    .hero {
      padding: 68px 0 54px;
      overflow: hidden;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.06fr .94fr;
      align-items: center;
      gap: 56px;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 9px;
      color: var(--red);
      font-size: .75rem;
      text-transform: uppercase;
      letter-spacing: .13em;
      font-weight: 800;
    }

    .eyebrow:before {
      content: "";
      width: 24px;
      height: 2px;
      background: var(--red);
    }

    h1 {
      font-family: Georgia, serif;
      font-size: clamp(3rem, 5.4vw, 5.15rem);
      line-height: 1.02;
      letter-spacing: -.055em;
      margin: 19px 0 20px;
      max-width: 680px;
      font-weight: 600;
    }

    h1 em {
      color: var(--red);
      font-weight: 500;
    }

    .hero-copy {
      color: #5B6B80;
      font-size: 1.08rem;
      max-width: 550px;
      margin: 0 0 28px;
    }

    .hero-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
    }

    .btn {
      display: inline-flex;
      justify-content: center;
      align-items: center;
      gap: 10px;
      border-radius: 999px;
      padding: 13px 20px;
      font-weight: 750;
      font-size: .9rem;
      border: 1px solid transparent;
      transition: .2s ease;
    }

    .btn-primary {
      color: white;
      background: var(--red);
      box-shadow: 0 9px 20px rgba(201,54,62,.18);
    }

    .btn-primary:hover {
      background: var(--red-dark);
      transform: translateY(-2px);
    }

    .btn-secondary {
      color: var(--navy);
      background: white;
      border-color: var(--line);
    }

    .btn-secondary:hover {
      border-color: var(--red);
      transform: translateY(-2px);
    }

    /* HERO IMAGE PLACEHOLDER */

    .hero-art {
      min-height: 420px;
      position: relative;
      border-radius: 32px;
      background: linear-gradient(145deg, #EDF2F8 0%, #DCE6F1 100%);
      display: grid;
      place-items: center;
      overflow: hidden;
    }

    .hero-art:before,
    .hero-art:after {
      content: "";
      position: absolute;
      border: 1px solid rgba(16,39,70,.13);
      border-radius: 50%;
    }

    .hero-art:before {
      width: 390px;
      height: 390px;
    }

    .hero-art:after {
      width: 500px;
      height: 500px;
    }

    .art-cross {
      position: absolute;
      top: 42px;
      right: 46px;
      width: 54px;
      height: 54px;
      border-radius: 18px;
      background: white;
      color: var(--red);
      display: grid;
      place-items: center;
      font-size: 2rem;
      box-shadow: var(--shadow);
    }

    .art-card {
      position: relative;
      z-index: 1;
      width: min(300px, 72%);
      background: rgba(255,255,255,.95);
      border: 1px solid white;
      border-radius: 24px;
      padding: 25px;
      box-shadow: var(--shadow);
      transform: rotate(-3deg);
    }

    .art-card-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 22px;
    }

    .art-dot {
      width: 34px;
      height: 34px;
      border-radius: 11px;
      background: var(--light-blue);
      color: var(--red);
      display: grid;
      place-items: center;
      font-weight: 900;
    }

    .art-lines span {
      display: block;
      height: 7px;
      border-radius: 99px;
      background: #E5EAF1;
      margin: 9px 0;
    }

    .art-lines span:nth-child(1) {
      width: 85%;
      background: #C7D5E6;
    }

    .art-lines span:nth-child(2) {
      width: 100%;
    }

    .art-lines span:nth-child(3) {
      width: 68%;
    }

    .art-pill {
      display: inline-block;
      margin-top: 13px;
      background: var(--red);
      color: white;
      border-radius: 99px;
      padding: 7px 14px;
      font-size: .68rem;
      font-weight: 800;
    }

    .floating-note {
      position: absolute;
      z-index: 2;
      left: 7%;
      bottom: 42px;
      background: white;
      border-radius: 15px;
      padding: 13px 16px;
      box-shadow: var(--shadow);
      font-size: .75rem;
      color: var(--muted);
    }

    .floating-note strong {
      display: block;
      color: var(--navy);
      font-size: .88rem;
    }

    /* QUICK ACCESS */

    .quick-wrap {
      padding: 22px 0 72px;
    }

    .section-head {
      display: flex;
      justify-content: space-between;
      align-items: end;
      gap: 24px;
      margin-bottom: 24px;
    }

    .section-kicker {
      color: var(--red);
      text-transform: uppercase;
      letter-spacing: .13em;
      font-size: .7rem;
      font-weight: 850;
    }

    h2 {
      font-family: Georgia, serif;
      letter-spacing: -.035em;
      font-size: clamp(2rem, 3.5vw, 2.8rem);
      line-height: 1.12;
      margin: 7px 0 0;
      font-weight: 600;
    }

    .section-intro {
      color: var(--muted);
      max-width: 410px;
      font-size: .92rem;
      margin: 0;
    }

    .quick-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 14px;
    }

    .quick-card {
      background: white;
      border: 1px solid var(--line);
      border-radius: 19px;
      padding: 22px;
      min-height: 185px;
      transition: .2s ease;
    }

    .quick-card:hover {
      transform: translateY(-4px);
      box-shadow: var(--shadow);
      border-color: #E5A8AC;
    }

    .icon-box {
      width: 43px;
      height: 43px;
      border-radius: 14px;
      display: grid;
      place-items: center;
      background: var(--light-blue);
      color: var(--red);
      font-size: 1.2rem;
      margin-bottom: 18px;
    }

    .quick-card h3 {
      margin: 0 0 7px;
      font-size: 1rem;
    }

    .quick-card p {
      color: var(--muted);
      font-size: .82rem;
      margin: 0 0 15px;
    }

    .text-link {
      color: var(--red);
      font-size: .8rem;
      font-weight: 800;
    }

    /* JOURNEY */

    .journey {
      background: var(--light-grey);
      padding: 76px 0;
    }

    .journey-grid {
      display: grid;
      grid-template-columns: .8fr 1.2fr;
      gap: 70px;
      align-items: center;
    }

    .journey-copy p {
      color: var(--muted);
      max-width: 420px;
    }

    .steps {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 13px;
    }

    .step {
      background: white;
      border: 1px solid var(--line);
      border-radius: 17px;
      padding: 20px;
      min-height: 145px;
    }

    .step-number {
      color: var(--red);
      font-size: .72rem;
      font-weight: 900;
      letter-spacing: .12em;
    }

    .step h3 {
      margin: 10px 0 5px;
      font-size: .98rem;
    }

    .step p {
      margin: 0;
      color: var(--muted);
      font-size: .8rem;
    }

    /* RESOURCES */

    .resources {
      padding: 76px 0;
    }

    .resource-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 18px;
    }

    .resource-card {
      border-radius: 23px;
      padding: 30px;
      min-height: 260px;
      position: relative;
      overflow: hidden;
    }

    .resource-card.dark {
      background: var(--navy);
      color: white;
    }

    .resource-card.pale {
      background: var(--light-blue);
      color: var(--navy);
    }

    .resource-card .big-symbol {
      position: absolute;
      right: 22px;
      bottom: -28px;
      font-size: 10rem;
      opacity: .09;
      line-height: 1;
    }

    .resource-card p {
      max-width: 360px;
      opacity: .78;
      font-size: .9rem;
    }

    .resource-card .btn {
      margin-top: 12px;
    }

    .resource-card.dark .btn {
      background: white;
      color: var(--navy);
    }

    .resource-card.pale .btn {
      background: var(--red);
      color: white;
    }

    /* ABOUT */

    .about {
      padding: 0 0 78px;
    }

    .about-panel {
      background: var(--light-grey);
      border: 1px solid var(--line);
      border-radius: 25px;
      padding: 36px;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 40px;
      align-items: center;
    }

    .about-panel p {
      color: var(--muted);
      margin-bottom: 0;
    }

    .placeholder-list {
      list-style: none;
      margin: 0;
      padding: 0;
      display: grid;
      gap: 12px;
    }

    .placeholder-list li {
      display: flex;
      align-items: center;
      gap: 12px;
      color: #40536D;
      font-size: .88rem;
    }

    .placeholder-list li:before {
      content: "✓";
      display: grid;
      place-items: center;
      width: 23px;
      height: 23px;
      flex: 0 0 23px;
      border-radius: 50%;
      color: var(--red);
      background: #FBE8E9;
      font-size: .75rem;
      font-weight: 900;
    }

    /* FOOTER */

    footer {
      background: var(--navy);
      color: white;
      padding: 42px 0 24px;
    }

    .footer-top {
      display: flex;
      justify-content: space-between;
      gap: 40px;
      padding-bottom: 34px;
    }

    .footer-brand {
      max-width: 310px;
    }

    .footer-brand p {
      color: #C5D0DF;
      font-size: .85rem;
    }

    .footer-links {
      display: flex;
      gap: 55px;
    }

    .footer-links div {
      display: grid;
      align-content: start;
      gap: 10px;
      font-size: .82rem;
      color: #D5DDEA;
    }

    .footer-links strong {
      color: white;
      margin-bottom: 4px;
    }

    .copyright {
      border-top: 1px solid rgba(255,255,255,.16);
      padding-top: 18px;
      color: #B7C4D5;
      font-size: .72rem;
      display: flex;
      justify-content: space-between;
      gap: 20px;
    }

    /* TABLET */

    @media (max-width: 900px) {
      .nav-links {
        gap: 15px;
        font-size: .8rem;
      }

      .hero-grid {
        gap: 30px;
      }

      .quick-grid {
        grid-template-columns: repeat(2, 1fr);
      }

      .journey-grid {
        gap: 35px;
      }
    }

    /* MOBILE */

    @media (max-width: 700px) {
      .container {
        width: min(100% - 34px, 560px);
      }

      .topbar-inner {
        font-size: .68rem;
      }

      .nav {
        min-height: 68px;
      }

      .menu-toggle {
        display: inline-flex;
      }

      .nav-links {
        display: none;
        position: absolute;
        left: 0;
        right: 0;
        top: 68px;
        background: white;
        border-bottom: 1px solid var(--line);
        padding: 18px 24px 22px;
        flex-direction: column;
        align-items: stretch;
        gap: 15px;
      }

      .nav-links.open {
        display: flex;
      }

      .language {
        display: none;
      }

      .hero {
        padding: 45px 0 38px;
      }

      .hero-grid,
      .journey-grid,
      .about-panel {
        grid-template-columns: 1fr;
      }

      .hero-grid {
        gap: 34px;
      }

      h1 {
        font-size: clamp(2.8rem, 13vw, 4.2rem);
      }

      .hero-copy {
        font-size: .98rem;
      }

      .hero-art {
        min-height: 310px;
      }

      .hero-art:before {
        width: 280px;
        height: 280px;
      }

      .hero-art:after {
        width: 360px;
        height: 360px;
      }

      .quick-wrap,
      .resources {
        padding: 48px 0;
      }

      .section-head {
        display: block;
      }

      .section-intro {
        margin-top: 12px;
      }

      .quick-grid {
        gap: 10px;
      }

      .quick-card {
        padding: 16px;
        min-height: 175px;
      }

      .journey {
        padding: 52px 0;
      }

      .steps {
        gap: 10px;
      }

      .step {
        padding: 15px;
        min-height: 145px;
      }

      .resource-grid {
        grid-template-columns: 1fr;
      }

      .resource-card {
        min-height: 235px;
        padding: 25px;
      }

      .about {
        padding-bottom: 52px;
      }

      .about-panel {
        padding: 25px;
        gap: 24px;
      }

      .footer-top {
        flex-direction: column;
      }

      .footer-links {
        gap: 35px;
        flex-wrap: wrap;
      }

      .copyright {
        flex-direction: column;
        gap: 7px;
      }
    }

    @media (max-width: 390px) {
      .brand {
        font-size: .98rem;
      }

      .quick-grid,
      .steps {
        grid-template-columns: 1fr;
      }

      .quick-card {
        min-height: auto;
      }

      .hero-buttons .btn {
        width: 100%;
      }
    }
  </style>
</head>

<body>

  <!-- TOP ANNOUNCEMENT BAR -->

  <div class="topbar">
    <div class="container topbar-inner">
      <span>✦ &nbsp;[Short helpful announcement or important notice]</span>
      <a href="#emergency">[Quick-access link] ↗</a>
    </div>
  </div>

  <!-- NAVIGATION -->

  <header>
    <div class="container nav">

      <a class="brand" href="#home">
        <span class="brand-mark">＋</span>
        <span>
          [Website Name]
          <small>[Short tagline]</small>
        </span>
      </a>

      <nav class="nav-links" id="navLinks">
        <a href="#guides">[Guides]</a>
        <a href="#journey">[How it works]</a>
        <a href="#resources">[Resources]</a>
        <a href="#about">[About]</a>
      </nav>

      <div class="nav-actions">
        <button class="language">EN ▾</button>
        <button class="menu-toggle" id="menuToggle">☰ Menu</button>
      </div>

    </div>
  </header>

  <main id="home">

    <!-- HERO SECTION -->

    <section class="hero">
      <div class="container hero-grid">

        <div>
          <span class="eyebrow">[Short introductory label]</span>

          <h1>
            [Main headline goes <em>right here.</em>]
          </h1>

          <p class="hero-copy">
            [Add a short, welcoming introduction. Explain who this website is for and what visitors can find here in one or two sentences.]
          </p>

          <div class="hero-buttons">
            <a class="btn btn-primary" href="#guides">
              [Primary action] →
            </a>

            <a class="btn btn-secondary" href="#about">
              [Secondary action] ↗
            </a>
          </div>
        </div>

        <!-- HERO IMAGE PLACEHOLDER -->

        <div class="hero-art">
          <div class="art-cross">＋</div>

          <div class="art-card">

            <div class="art-card-top">
              <div class="art-dot">＋</div>
              <span style="font-size:.68rem;color:#78908a;font-weight:800;letter-spacing:.1em">
                [CARD LABEL]
              </span>
            </div>

            <div style="font-family:Georgia,serif;font-size:1.5rem;line-height:1.15;margin-bottom:15px">
              [Illustration headline]
            </div>

            <div class="art-lines">
              <span></span>
              <span></span>
              <span></span>
            </div>

            <span class="art-pill">[BUTTON LABEL] →</span>

          </div>

          <div class="floating-note">
            <strong>[Small highlight]</strong>
            [One-line supporting text]
          </div>

        </div>

      </div>
    </section>

    <!-- QUICK ACCESS SECTION -->

    <section class="quick-wrap" id="guides">
      <div class="container">

        <div class="section-head">

          <div>
            <span class="section-kicker">[Section label]</span>
            <h2>[Find what you need]</h2>
          </div>

          <p class="section-intro">
            [A short sentence introducing the main topics or most-used areas of the website.]
          </p>

        </div>

        <div class="quick-grid">

          <a class="quick-card" href="#">
            <div class="icon-box">⌕</div>
            <h3>[Topic / Guide 01]</h3>
            <p>[One-sentence description of this section.]</p>
            <span class="text-link">Explore topic →</span>
          </a>

          <a class="quick-card" href="#">
            <div class="icon-box">▤</div>
            <h3>[Topic / Guide 02]</h3>
            <p>[One-sentence description of this section.]</p>
            <span class="text-link">Explore topic →</span>
          </a>

          <a class="quick-card" href="#">
            <div class="icon-box">◎</div>
            <h3>[Topic / Guide 03]</h3>
            <p>[One-sentence description of this section.]</p>
            <span class="text-link">Explore topic →</span>
          </a>

          <a class="quick-card" href="#">
            <div class="icon-box">⌁</div>
            <h3>[Topic / Guide 04]</h3>
            <p>[One-sentence description of this section.]</p>
            <span class="text-link">Explore topic →</span>
          </a>

        </div>
      </div>
    </section>

    <!-- STEP-BY-STEP SECTION -->

    <section class="journey" id="journey">
      <div class="container journey-grid">

        <div class="journey-copy">

          <span class="section-kicker">[Section label]</span>

          <h2>[A simple step-by-step overview]</h2>

          <p>
            [Explain why this process or sequence is useful. Keep the introduction brief and reassuring.]
          </p>

          <a class="btn btn-primary" href="#">
            [Explore the full guide] →
          </a>

        </div>

        <div class="steps">

          <article class="step">
            <span class="step-number">STEP 01</span>
            <h3>[First step]</h3>
            <p>[Short explanation or bullet-point summary.]</p>
          </article>

          <article class="step">
            <span class="step-number">STEP 02</span>
            <h3>[Second step]</h3>
            <p>[Short explanation or bullet-point summary.]</p>
          </article>

          <article class="step">
            <span class="step-number">STEP 03</span>
            <h3>[Third step]</h3>
            <p>[Short explanation or bullet-point summary.]</p>
          </article>

          <article class="step">
            <span class="step-number">STEP 04</span>
            <h3>[Fourth step]</h3>
            <p>[Short explanation or bullet-point summary.]</p>
          </article>

        </div>
      </div>
    </section>

    <!-- RESOURCES SECTION -->

    <section class="resources" id="resources">
      <div class="container">

        <div class="section-head">

          <div>
            <span class="section-kicker">[Section label]</span>
            <h2>[Tools & resources]</h2>
          </div>

          <p class="section-intro">
            [Introduce useful tools, downloadable resources, or interactive features.]
          </p>

        </div>

        <div class="resource-grid">

          <article class="resource-card dark">

            <span class="section-kicker" style="color:#F2A5A9">
              [FEATURE 01]
            </span>

            <h2>[Featured tool headline]</h2>

            <p>
              [Describe what visitors can do with this tool. Use one or two short sentences.]
            </p>

            <a class="btn" href="#">[Open tool] →</a>

            <span class="big-symbol" aria-hidden="true">＋</span>

          </article>

          <article class="resource-card pale">

            <span class="section-kicker">[FEATURE 02]</span>

            <h2>[Another useful resource]</h2>

            <p>
              [Describe the second resource and why someone might want to use it.]
            </p>

            <a class="btn" href="#">[View resource] →</a>

            <span class="big-symbol" aria-hidden="true">文</span>

          </article>

        </div>
      </div>
    </section>

    <!-- ABOUT SECTION -->

    <section class="about" id="about">
      <div class="container">

        <div class="about-panel">

          <div>
            <span class="section-kicker">[Section label]</span>

            <h2>[A little about this project]</h2>

            <p>
              [Write a short paragraph about the purpose, audience, and motivation behind the website.]
            </p>
          </div>

          <ul class="placeholder-list">
            <li>[Key point or project value one]</li>
            <li>[Key point or project value two]</li>
            <li>[Key point or project value three]</li>
            <li>[Link to more information or project background]</li>
          </ul>

        </div>
      </div>
    </section>

  </main>

  <!-- FOOTER -->

  <footer id="emergency">
    <div class="container">

      <div class="footer-top">

        <div class="footer-brand">

          <a class="brand" href="#home" style="color:white">
            <span class="brand-mark">＋</span>

            <span>
              [Website Name]
              <small style="color:#C5D0DF">[Short tagline]</small>
            </span>
          </a>

          <p>
            [A short footer description or reminder about the purpose of this resource.]
          </p>

        </div>

        <div class="footer-links">

          <div>
            <strong>[Explore]</strong>
            <a href="#guides">[Guide link]</a>
            <a href="#journey">[Process link]</a>
            <a href="#resources">[Resource link]</a>
          </div>

          <div>
            <strong>[Information]</strong>
            <a href="#about">[About this project]</a>
            <a href="#">[Sources]</a>
            <a href="#">[Contact]</a>
          </div>

        </div>

      </div>

      <div class="copyright">
        <span>© [Year] [Website Name]. [Footer note.]</span>
        <span>[Privacy] · [Disclaimer]</span>
      </div>

    </div>
  </footer>

  <!-- MOBILE NAVIGATION SCRIPT -->

  <script>
    const toggle = document.getElementById('menuToggle');
    const nav = document.getElementById('navLinks');

    toggle.addEventListener('click', () => {
      const isOpen = nav.classList.toggle('open');

      toggle.setAttribute('aria-expanded', String(isOpen));
      toggle.textContent = isOpen ? '✕ Close' : '☰ Menu';
    });

    nav.querySelectorAll('a').forEach(link => {
      link.addEventListener('click', () => {
        nav.classList.remove('open');
        toggle.setAttribute('aria-expanded', 'false');
        toggle.textContent = '☰ Menu';
      });
    });
  </script>

</body>
</html>
