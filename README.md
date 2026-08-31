<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>Waiz | Developer</title>

  <meta
    name="description"
    content="Waiz — developer focused on Python, TypeScript, AI-assisted development, APIs and full-stack systems."
  />

  <style>
    /* ================================
       RESET
    ================================= */

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background:
        radial-gradient(circle at 50% -20%, #252525 0%, transparent 40%),
        #070707;

      color: #f5f5f5;

      font-family:
        Inter,
        system-ui,
        -apple-system,
        BlinkMacSystemFont,
        "Segoe UI",
        sans-serif;

      min-height: 100vh;
      overflow-x: hidden;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    /* ================================
       BACKGROUND
    ================================= */

    .background {
      position: fixed;
      inset: 0;
      pointer-events: none;
      z-index: -2;
    }

    .grid {
      position: absolute;
      inset: 0;

      background-image:
        linear-gradient(rgba(255,255,255,.025) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,.025) 1px, transparent 1px);

      background-size: 70px 70px;

      mask-image: linear-gradient(
        to bottom,
        rgba(0,0,0,.9),
        transparent 90%
      );
    }

    .glow {
      position: absolute;

      width: 800px;
      height: 800px;

      top: -500px;
      left: 50%;

      transform: translateX(-50%);

      background:
        radial-gradient(
          circle,
          rgba(255,255,255,.08),
          transparent 65%
        );

      filter: blur(30px);
    }

    /* ================================
       NAVBAR
    ================================= */

    nav {
      width: min(1100px, calc(100% - 40px));

      margin: 20px auto;

      padding: 14px 18px;

      display: flex;
      align-items: center;
      justify-content: space-between;

      position: sticky;
      top: 16px;
      z-index: 100;

      border: 1px solid rgba(255,255,255,.08);

      background: rgba(10,10,10,.65);

      backdrop-filter: blur(22px);
      -webkit-backdrop-filter: blur(22px);

      border-radius: 16px;
    }

    .brand {
      font-size: 14px;
      font-weight: 700;
      letter-spacing: .7px;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 24px;

      font-size: 13px;
      color: #8e8e8e;
    }

    .nav-links a {
      transition: .25s ease;
    }

    .nav-links a:hover {
      color: #fff;
    }

    /* ================================
       HERO
    ================================= */

    .hero {
      width: min(1050px, calc(100% - 40px));

      margin: 0 auto;

      min-height: 76vh;

      display: flex;
      flex-direction: column;
      justify-content: center;

      padding-top: 80px;
      padding-bottom: 80px;
    }

    .status {
      display: inline-flex;
      align-items: center;
      gap: 10px;

      width: max-content;

      padding: 7px 12px;

      border: 1px solid rgba(255,255,255,.1);
      border-radius: 999px;

      color: #aaa;

      background: rgba(255,255,255,.025);

      font-size: 12px;

      margin-bottom: 30px;

      animation: fade-up .8s ease both;
    }

    .status-dot {
      height: 7px;
      width: 7px;

      border-radius: 100%;

      background: #b7ffbc;

      box-shadow: 0 0 12px rgba(183,255,188,.7);

      animation: pulse 2s infinite;
    }

    .eyebrow {
      font-size: 14px;
      color: #737373;

      margin-bottom: 16px;

      animation: fade-up .8s .05s ease both;
    }

    h1 {
      max-width: 930px;

      font-size: clamp(52px, 8vw, 106px);

      font-weight: 600;

      line-height: .95;

      letter-spacing: -5px;

      color: #f4f4f4;

      animation: fade-up .8s .1s ease both;
    }

    .hero-gradient {
      color: transparent;

      background:
        linear-gradient(
          90deg,
          #fff,
          #858585,
          #fff
        );

      background-size: 200% auto;

      background-clip: text;
      -webkit-background-clip: text;

      animation:
        shine 6s linear infinite;
    }

    .hero-description {
      margin-top: 32px;

      max-width: 680px;

      font-size: clamp(17px, 2vw, 21px);

      color: #858585;

      line-height: 1.65;

      animation: fade-up .8s .15s ease both;
    }

    .hero-description strong {
      color: #d5d5d5;
      font-weight: 500;
    }

    .hero-actions {
      display: flex;
      gap: 12px;

      margin-top: 40px;

      animation: fade-up .8s .2s ease both;
    }

    .button {
      padding: 12px 18px;

      border-radius: 10px;

      font-size: 13px;

      border: 1px solid rgba(255,255,255,.1);

      transition:
        transform .2s ease,
        background .2s ease,
        border-color .2s ease;
    }

    .button-primary {
      background: #f2f2f2;
      color: #111;
    }

    .button-secondary {
      background: rgba(255,255,255,.03);
      color: #aaa;
    }

    .button:hover {
      transform: translateY(-2px);
    }

    .button-secondary:hover {
      color: white;
      background: rgba(255,255,255,.07);
    }

    /* ================================
       SECTION
    ================================= */

    section {
      width: min(1050px, calc(100% - 40px));

      margin: 0 auto 130px;
    }

    .section-label {
      font-size: 11px;

      letter-spacing: 2px;

      text-transform: uppercase;

      color: #575757;

      margin-bottom: 28px;
    }

    /* ================================
       TECH GRID
    ================================= */

    .tech-grid {
      display: grid;

      grid-template-columns:
        repeat(3, minmax(0, 1fr));

      gap: 12px;
    }

    .tech-card {
      min-height: 200px;

      position: relative;

      padding: 24px;

      border-radius: 18px;

      border: 1px solid rgba(255,255,255,.07);

      background:
        linear-gradient(
          145deg,
          rgba(255,255,255,.035),
          rgba(255,255,255,.012)
        );

      overflow: hidden;

      transition:
        transform .35s cubic-bezier(.2,.8,.2,1),
        border-color .35s ease,
        background .35s ease;
    }

    .tech-card:hover {
      transform: translateY(-5px);

      border-color: rgba(255,255,255,.16);

      background:
        linear-gradient(
          145deg,
          rgba(255,255,255,.07),
          rgba(255,255,255,.015)
        );
    }

    .tech-number {
      color: #444;

      font-family: monospace;

      font-size: 11px;

      margin-bottom: 55px;
    }

    .tech-card h3 {
      font-size: 19px;

      margin-bottom: 10px;

      font-weight: 500;
    }

    .tech-card p {
      color: #6e6e6e;

      font-size: 13px;

      line-height: 1.6;
    }

    .card-light {
      position: absolute;

      width: 250px;
      height: 250px;

      border-radius: 50%;

      background:
        radial-gradient(
          circle,
          rgba(255,255,255,.09),
          transparent 68%
        );

      pointer-events: none;

      opacity: 0;

      transform: translate(-50%, -50%);

      transition: opacity .2s;
    }

    /* ================================
       STACK
    ================================= */

    .stack-wrap {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .stack {
      padding: 9px 13px;

      border-radius: 8px;

      border: 1px solid rgba(255,255,255,.07);

      background: rgba(255,255,255,.02);

      font-family: monospace;

      font-size: 12px;

      color: #9b9b9b;

      transition: .2s ease;
    }

    .stack:hover {
      border-color: rgba(255,255,255,.18);
      color: white;
      transform: translateY(-2px);
    }

    /* ================================
       TERMINAL
    ================================= */

    .terminal {
      border: 1px solid rgba(255,255,255,.08);

      background: #090909;

      border-radius: 18px;

      overflow: hidden;
    }

    .terminal-header {
      padding: 14px 17px;

      display: flex;
      gap: 7px;

      border-bottom: 1px solid rgba(255,255,255,.06);
    }

    .terminal-circle {
      height: 8px;
      width: 8px;

      border-radius: 50%;

      background: #333;
    }

    .terminal-body {
      padding: 24px;

      font-family:
        "SFMono-Regular",
        Consolas,
        monospace;

      font-size: 13px;

      line-height: 2;

      color: #777;
    }

    .terminal-command {
      color: #efefef;
    }

    .terminal-value {
      color: #a0a0a0;
    }

    .cursor {
      display: inline-block;

      width: 7px;
      height: 15px;

      vertical-align: middle;

      margin-left: 5px;

      background: #dedede;

      animation: blink .8s infinite;
    }

    /* ================================
       FOOTER
    ================================= */

    footer {
      width: min(1050px, calc(100% - 40px));

      margin: 0 auto;

      padding: 50px 0;

      display: flex;
      justify-content: space-between;

      border-top: 1px solid rgba(255,255,255,.06);

      font-size: 12px;
      color: #555;
    }

    /* ================================
       SCROLL ANIMATION
    ================================= */

    .reveal {
      opacity: 0;
      transform: translateY(30px);

      transition:
        opacity .8s ease,
        transform .8s cubic-bezier(.2,.8,.2,1);
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* ================================
       ANIMATIONS
    ================================= */

    @keyframes fade-up {
      from {
        opacity: 0;
        transform: translateY(20px);
      }

      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes pulse {
      0%, 100% {
        opacity: .45;
      }

      50% {
        opacity: 1;
      }
    }

    @keyframes shine {
      to {
        background-position: 200% center;
      }
    }

    @keyframes blink {
      0%, 45% {
        opacity: 1;
      }

      46%, 100% {
        opacity: 0;
      }
    }

    /* ================================
       MOBILE
    ================================= */

    @media (max-width: 800px) {

      nav {
        width: calc(100% - 24px);
      }

      .nav-links a:not(:last-child) {
        display: none;
      }

      .hero {
        width: calc(100% - 32px);

        min-height: 80vh;
      }

      h1 {
        letter-spacing: -3px;
      }

      section,
      footer {
        width: calc(100% - 32px);
      }

      .tech-grid {
        grid-template-columns: 1fr;
      }

      .tech-card {
        min-height: 175px;
      }

      .hero-actions {
        flex-wrap: wrap;
      }

      footer {
        flex-direction: column;
        gap: 10px;
      }
    }
  </style>
</head>

<body>

  <!-- BACKGROUND -->

  <div class="background">
    <div class="grid"></div>
    <div class="glow"></div>
  </div>


  <!-- NAVBAR -->

  <nav>
    <div class="brand">
      WAIZ<span style="color:#555">.</span>DEV
    </div>

    <div class="nav-links">
      <a href="#knowledge">Knowledge</a>
      <a href="#stack">Stack</a>
      <a href="#about">About</a>

      <a
        href="https://github.com/YOUR_USERNAME"
        target="_blank"
      >
        GitHub ↗
      </a>
    </div>
  </nav>


  <!-- HERO -->

  <main class="hero">

    <div class="status">
      <div class="status-dot"></div>
      Building & learning
    </div>

    <div class="eyebrow">
      Developer / Problem Solver
    </div>

    <h1>
      I build things
      <span class="hero-gradient">
        that work.
      </span>
    </h1>

    <div class="hero-description">
      I'm <strong>Waiz</strong>, a developer focused on
      <strong>Python, TypeScript, full-stack systems, APIs
      and AI-assisted development.</strong>

      I care more about understanding the logic and shipping
      working systems than collecting buzzwords.
    </div>

    <div class="hero-actions">

      <a
        class="button button-primary"
        href="https://github.com/YOUR_USERNAME"
        target="_blank"
      >
        View GitHub ↗
      </a>

      <a
        class="button button-secondary"
        href="#knowledge"
      >
        Explore knowledge
      </a>

    </div>

  </main>


  <!-- KNOWLEDGE -->

  <section id="knowledge" class="reveal">

    <div class="section-label">
      01 / Technical Knowledge
    </div>

    <div class="tech-grid">

      <div class="tech-card">
        <div class="card-light"></div>

        <div class="tech-number">
          01
        </div>

        <h3>Python</h3>

        <p>
          Programming logic, automation, APIs,
          backend concepts, file handling and
          problem solving.
        </p>
      </div>


      <div class="tech-card">
        <div class="card-light"></div>

        <div class="tech-number">
          02
        </div>

        <h3>JavaScript / TypeScript</h3>

        <p>
          Modern JavaScript, TypeScript,
          asynchronous workflows, frontend logic
          and application development.
        </p>
      </div>


      <div class="tech-card">
        <div class="card-light"></div>

        <div class="tech-number">
          03
        </div>

        <h3>Full Stack</h3>

        <p>
          Connecting interfaces, APIs,
          authentication, application logic
          and databases into complete products.
        </p>
      </div>


      <div class="tech-card">
        <div class="card-light"></div>

        <div class="tech-number">
          04
        </div>

        <h3>APIs</h3>

        <p>
          REST fundamentals, HTTP methods,
          JSON, authentication and integrating
          external services.
        </p>
      </div>


      <div class="tech-card">
        <div class="card-light"></div>

        <div class="tech-number">
          05
        </div>

        <h3>Databases</h3>

        <p>
          SQL fundamentals, relational data,
          CRUD operations, PostgreSQL and
          working with Supabase.
        </p>
      </div>


      <div class="tech-card">
        <div class="card-light"></div>

        <div class="tech-number">
          06
        </div>

        <h3>AI Development</h3>

        <p>
          Using AI as an engineering tool for
          implementation, debugging, architecture,
          research and development workflows.
        </p>
      </div>

    </div>

  </section>


  <!-- STACK -->

  <section id="stack" class="reveal">

    <div class="section-label">
      02 / Technologies
    </div>

    <div class="stack-wrap">

      <div class="stack">Python</div>
      <div class="stack">JavaScript</div>
      <div class="stack">TypeScript</div>

      <div class="stack">React</div>
      <div class="stack">Node.js</div>

      <div class="stack">REST APIs</div>

      <div class="stack">PostgreSQL</div>
      <div class="stack">Supabase</div>

      <div class="stack">Git</div>
      <div class="stack">GitHub</div>

      <div class="stack">Vercel</div>

      <div class="stack">AI Workflows</div>

      <div class="stack">Prompt Engineering</div>

      <div class="stack">Problem Solving</div>

    </div>

  </section>


  <!-- TERMINAL / ABOUT -->

  <section id="about" class="reveal">

    <div class="section-label">
      03 / Developer Profile
    </div>

    <div class="terminal">

      <div class="terminal-header">
        <div class="terminal-circle"></div>
        <div class="terminal-circle"></div>
        <div class="terminal-circle"></div>
      </div>

      <div class="terminal-body">

        <div>
          <span class="terminal-command">
            $ whoami
          </span>
        </div>

        <div class="terminal-value">
          Waiz — developer & builder
        </div>

        <br>

        <div>
          <span class="terminal-command">
            $ cat focus.txt
          </span>
        </div>

        <div class="terminal-value">
          Python · Full Stack · AI · APIs · Automation
        </div>

        <br>

        <div>
          <span class="terminal-command">
            $ cat philosophy.txt
          </span>
        </div>

        <div class="terminal-value">
          Understand the problem. Build the logic.
          Ship the system.
        </div>

        <br>

        <div>
          <span class="terminal-command">
            $ status
          </span>
        </div>

        <div class="terminal-value">
          Learning continuously.
          Building continuously.
          <span class="cursor"></span>
        </div>

      </div>

    </div>

  </section>


  <!-- FOOTER -->

  <footer>

    <div>
      © 2026 Waiz
    </div>

    <div>
      Designed & built from scratch.
    </div>

  </footer>


  <script>

    /* ================================
       SCROLL REVEAL
    ================================= */

    const observer = new IntersectionObserver(
      entries => {

        entries.forEach(entry => {

          if (entry.isIntersecting) {

            entry.target.classList.add("visible");

          }

        });

      },
      {
        threshold: 0.15
      }
    );


    document
      .querySelectorAll(".reveal")
      .forEach(element => observer.observe(element));


    /* ================================
       INTERACTIVE CARD LIGHT
    ================================= */

    document
      .querySelectorAll(".tech-card")
      .forEach(card => {

        const light =
          card.querySelector(".card-light");


        card.addEventListener(
          "mousemove",
          event => {

            const rect =
              card.getBoundingClientRect();

            const x =
              event.clientX - rect.left;

            const y =
              event.clientY - rect.top;

            light.style.left =
              x + "px";

            light.style.top =
              y + "px";

            light.style.opacity =
              "1";

          }
        );


        card.addEventListener(
          "mouseleave",
          () => {

            light.style.opacity =
              "0";

          }
        );

      });

  </script>

</body>
</html>
