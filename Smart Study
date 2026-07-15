<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Smart Study Generator</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: -apple-system, "Segoe UI", system-ui, sans-serif;
      background: #f4f6fb;
      color: #1f2328;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    /* ── HEADER ── */
    header {
      background: #1e3a8a;
      color: #fff;
      padding: 0 32px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 68px;
      position: sticky;
      top: 0;
      z-index: 100;
      box-shadow: 0 2px 10px rgba(0,0,0,0.2);
    }
    .header-brand { display: flex; align-items: center; gap: 14px; }
    .header-logo {
      width: 44px; height: 44px; border-radius: 10px;
      background: #fff; display: flex; align-items: center;
      justify-content: center; font-size: 24px; flex-shrink: 0;
    }
    .header-brand h1 { font-size: 21px; font-weight: 800; letter-spacing: 0.3px; }
    .header-brand p  { font-size: 12px; opacity: 0.8; margin-top: 2px; }
    .header-badge {
      background: rgba(255,255,255,0.15);
      border: 1px solid rgba(255,255,255,0.4);
      color: #fff; font-size: 11px; padding: 5px 14px;
      border-radius: 20px; font-weight: 700; letter-spacing: 0.5px;
    }

    /* ── HERO ── */
    .hero {
      background: #1e3a8a;
      color: #fff;
      text-align: center;
      padding: 76px 24px 64px;
      position: relative;
      overflow: hidden;
    }
    .hero-bg-pattern {
      position: absolute; inset: 0; opacity: 0.05;
      background-image: repeating-linear-gradient(
        0deg, #fff 0, #fff 1px, transparent 0, transparent 40px),
        repeating-linear-gradient(90deg, #fff 0, #fff 1px, transparent 0, transparent 40px);
    }
    .hero-content { position: relative; z-index: 1; }
    .hero h2 {
      font-size: 42px; font-weight: 900; line-height: 1.15;
      margin-bottom: 18px; letter-spacing: -0.5px;
    }
    .hero h2 span { color: #93c5fd; }
    .hero p {
      font-size: 17px; max-width: 580px; margin: 0 auto 36px;
      opacity: 0.9; line-height: 1.65;
    }
    .hero-pills { display: flex; flex-wrap: wrap; justify-content: center; gap: 10px; }
    .pill {
      background: rgba(255,255,255,0.15);
      border: 1px solid rgba(255,255,255,0.35);
      color: #fff; padding: 7px 18px;
      border-radius: 24px; font-size: 13px; font-weight: 600;
    }

    /* ── MAIN ── */
    main {
      flex: 1; max-width: 1120px; width: 100%;
      margin: 0 auto; padding: 56px 24px 44px;
    }

    .section-title    { font-size: 23px; font-weight: 800; color: #1f2328; margin-bottom: 6px; }
    .section-subtitle { font-size: 14px; color: #57606a; margin-bottom: 30px; line-height: 1.55; }

    /* ── FEATURE CARDS ── */
    .features-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
      gap: 20px; margin-bottom: 60px;
    }
    .feature-card {
      background: #fff; border: 1px solid #e5e7eb;
      border-radius: 14px; padding: 28px 22px;
      display: flex; flex-direction: column; gap: 12px;
    }
    .feature-icon {
      width: 52px; height: 52px; border-radius: 12px;
      background: #eff6ff; display: flex;
      align-items: center; justify-content: center; font-size: 26px;
    }
    .feature-card h3 { font-size: 16px; font-weight: 800; color: #1f2328; }
    .feature-card p  { font-size: 13px; color: #57606a; line-height: 1.6; }
    .feature-tag {
      display: inline-block; background: #eff6ff; color: #1e3a8a;
      font-size: 11px; font-weight: 700; padding: 3px 10px;
      border-radius: 6px; border: 1px solid #bfdbfe; margin-top: auto;
      align-self: flex-start;
    }

    /* ── HOW IT WORKS ── */
    .how-section {
      background: #f7f8fa; border: 1px solid #e5e7eb;
      border-radius: 14px; padding: 36px 32px; margin-bottom: 56px;
    }
    .steps {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 28px; margin-top: 28px;
    }
    .step { display: flex; gap: 14px; align-items: flex-start; }
    .step-num {
      width: 38px; height: 38px; border-radius: 50%;
      background: #1e3a8a; color: #fff; font-size: 17px;
      font-weight: 900; display: flex; align-items: center;
      justify-content: center; flex-shrink: 0;
    }
    .step h4 { font-size: 14px; font-weight: 700; color: #1f2328; margin-bottom: 4px; }
    .step p  { font-size: 13px; color: #57606a; line-height: 1.55; }

    /* ── USE CASES ── */
    .usecases-section { margin-bottom: 56px; }
    .usecases-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
      gap: 14px;
    }
    .usecase-card {
      background: #fff; border: 1px solid #e5e7eb;
      border-radius: 12px; padding: 20px 14px; text-align: center;
    }
    .usecase-card .icon  { font-size: 30px; margin-bottom: 10px; display: block; }
    .usecase-card .title { font-size: 13px; font-weight: 700; color: #1f2328; }
    .usecase-card .desc  { font-size: 11px; color: #57606a; margin-top: 4px; line-height: 1.4; }

    /* ── STATS STRIP ── */
    .stats-strip {
      background: #1e3a8a; border-radius: 14px;
      padding: 32px 28px; margin-bottom: 56px;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
      gap: 24px; text-align: center;
    }
    .stat-item {}
    .stat-value { font-size: 32px; font-weight: 900; color: #93c5fd; }
    .stat-label { font-size: 13px; color: rgba(255,255,255,0.75); margin-top: 4px; }

    /* ── TIPS ── */
    .tips-strip {
      background: #fff; border: 1px solid #e5e7eb;
      border-left: 5px solid #3b82f6; border-radius: 10px;
      padding: 20px 22px; margin-bottom: 56px;
    }
    .tips-strip h3 { font-size: 15px; font-weight: 700; color: #1f2328; margin-bottom: 12px; }
    .tips-strip ul { list-style: none; display: flex; flex-wrap: wrap; gap: 8px 32px; }
    .tips-strip ul li { font-size: 13px; color: #57606a; line-height: 1.6; }
    .tips-strip ul li::before { content: "▸ "; color: #3b82f6; font-weight: 900; }

    /* ── CHAT CTA ── */
    .chat-cta {
      background: #1e3a8a; border-radius: 14px;
      padding: 44px 28px; text-align: center; color: #fff; margin-bottom: 8px;
    }
    .chat-cta h3 { font-size: 26px; font-weight: 900; margin-bottom: 12px; }
    .chat-cta p  { font-size: 15px; opacity: 0.88; max-width: 520px; margin: 0 auto; line-height: 1.65; }

    /* ── FOOTER ── */
    footer {
      text-align: center; padding: 18px;
      font-size: 12px; color: #57606a;
      border-top: 1px solid #e5e7eb; background: #fff;
    }

    @media (max-width: 600px) {
      .hero h2  { font-size: 28px; }
      header    { padding: 0 16px; }
      main      { padding: 36px 16px 32px; }
      .how-section { padding: 24px 18px; }
    }
  </style>
</head>
<body>

  <!-- HEADER -->
  <header>
    <div class="header-brand">
      <div class="header-logo">📚</div>
      <div>
        <h1>Smart Study Generator</h1>
        <p>Powered by IBM watsonx Orchestrate</p>
      </div>
    </div>
    <div class="header-badge">AI Agent</div>
  </header>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-bg-pattern"></div>
    <div class="hero-content">
      <h2>Study <span>Smarter</span>, Not Harder</h2>
      <p>Your AI-powered study companion — generate summaries, flashcards, quizzes, study plans, and explanations for any topic instantly.</p>
      <div class="hero-pills">
        <span class="pill">📝 Summaries</span>
        <span class="pill">🃏 Flashcards</span>
        <span class="pill">❓ Quizzes</span>
        <span class="pill">📅 Study Plans</span>
        <span class="pill">💡 Explanations</span>
        <span class="pill">🔍 Deep Dives</span>
      </div>
    </div>
  </section>

  <!-- MAIN -->
  <main>

    <!-- FEATURES -->
    <div class="section-title">What the Agent Can Do</div>
    <div class="section-subtitle">Ask the AI study agent for any of the following — powered by IBM watsonx Orchestrate.</div>
    <div class="features-grid">
      <div class="feature-card">
        <div class="feature-icon">📄</div>
        <h3>Smart Summaries</h3>
        <p>Paste any text, paste a topic, or describe a chapter — get a concise, well-structured summary in seconds.</p>
        <span class="feature-tag">Instant Output</span>
      </div>
      <div class="feature-card">
        <div class="feature-icon">🃏</div>
        <h3>Flashcard Generator</h3>
        <p>Turn any topic or notes into ready-to-use Q&amp;A flashcards optimised for spaced-repetition learning.</p>
        <span class="feature-tag">Active Recall</span>
      </div>
      <div class="feature-card">
        <div class="feature-icon">❓</div>
        <h3>Quiz Builder</h3>
        <p>Generate multiple-choice, true/false, or short-answer quizzes on any subject at any difficulty level.</p>
        <span class="feature-tag">Self-Testing</span>
      </div>
      <div class="feature-card">
        <div class="feature-icon">📅</div>
        <h3>Study Plan Creator</h3>
        <p>Provide your exam date and topics — get a personalised, day-by-day study schedule tailored to your goals.</p>
        <span class="feature-tag">Personalised</span>
      </div>
      <div class="feature-card">
        <div class="feature-icon">💡</div>
        <h3>Concept Explainer</h3>
        <p>Struggling with a concept? Ask the agent to explain it simply, with analogies and real-world examples.</p>
        <span class="feature-tag">Plain English</span>
      </div>
      <div class="feature-card">
        <div class="feature-icon">🔍</div>
        <h3>Deep Dive Mode</h3>
        <p>Request an in-depth breakdown of complex topics with structured notes, diagrams in text, and key takeaways.</p>
        <span class="feature-tag">Advanced</span>
      </div>
      <div class="feature-card">
        <div class="feature-icon">📊</div>
        <h3>Mind Map Outline</h3>
        <p>Get a hierarchical mind-map-style outline of any subject to visualise how concepts connect together.</p>
        <span class="feature-tag">Visual Learning</span>
      </div>
      <div class="feature-card">
        <div class="feature-icon">✍️</div>
        <h3>Essay Guidance</h3>
        <p>Ask for essay structures, thesis suggestions, or argument outlines for any academic subject or prompt.</p>
        <span class="feature-tag">Academic Writing</span>
      </div>
    </div>

    <!-- HOW IT WORKS -->
    <div class="how-section">
      <div class="section-title">How It Works</div>
      <div class="section-subtitle" style="margin-bottom:0">Four simple steps to smarter studying — no sign-up, no setup, just chat.</div>
      <div class="steps">
        <div class="step">
          <div class="step-num">1</div>
          <div><h4>Open the Chat</h4><p>Click the chat bubble in the bottom-right corner to launch the AI study agent.</p></div>
        </div>
        <div class="step">
          <div class="step-num">2</div>
          <div><h4>Describe Your Need</h4><p>Tell the agent your subject, topic, or paste your notes. Be as specific or general as you like.</p></div>
        </div>
        <div class="step">
          <div class="step-num">3</div>
          <div><h4>Get Your Material</h4><p>Receive summaries, flashcards, quizzes, or a study plan — formatted and ready to use.</p></div>
        </div>
        <div class="step">
          <div class="step-num">4</div>
          <div><h4>Refine &amp; Iterate</h4><p>Ask follow-up questions, request harder quizzes, or adjust the difficulty and depth at any time.</p></div>
        </div>
      </div>
    </div>

    <!-- USE CASES -->
    <div class="usecases-section">
      <div class="section-title">Who Is It For?</div>
      <div class="section-subtitle">The Smart Study Generator helps learners at every level and in every field.</div>
      <div class="usecases-grid">
        <div class="usecase-card"><span class="icon">🎓</span><div class="title">University Students</div><div class="desc">Ace exams with AI-generated revision materials</div></div>
        <div class="usecase-card"><span class="icon">🏫</span><div class="title">High Schoolers</div><div class="desc">Simplify complex subjects with clear explanations</div></div>
        <div class="usecase-card"><span class="icon">💼</span><div class="title">Professionals</div><div class="desc">Upskill fast with focused study plans</div></div>
        <div class="usecase-card"><span class="icon">👩‍🏫</span><div class="title">Teachers</div><div class="desc">Generate quizzes and lesson summaries quickly</div></div>
        <div class="usecase-card"><span class="icon">🌍</span><div class="title">Language Learners</div><div class="desc">Vocabulary flashcards and grammar quizzes</div></div>
        <div class="usecase-card"><span class="icon">📜</span><div class="title">Certification Prep</div><div class="desc">Targeted prep for professional certifications</div></div>
      </div>
    </div>

    <!-- STATS -->
    <div class="stats-strip">
      <div class="stat-item"><div class="stat-value">10x</div><div class="stat-label">Faster Study Prep</div></div>
      <div class="stat-item"><div class="stat-value">100+</div><div class="stat-label">Supported Subjects</div></div>
      <div class="stat-item"><div class="stat-value">5</div><div class="stat-label">Output Formats</div></div>
      <div class="stat-item"><div class="stat-value">24/7</div><div class="stat-label">Always Available</div></div>
    </div>

    <!-- TIPS -->
    <div class="tips-strip">
      <h3>Tips for Getting the Best Results</h3>
      <ul>
        <li>Be specific — "Explain photosynthesis for a Year 10 student" works better than "Explain photosynthesis"</li>
        <li>Paste your actual notes for the most targeted summaries and flashcards</li>
        <li>Ask for a specific number of flashcards or quiz questions</li>
        <li>Specify difficulty level: beginner, intermediate, or advanced</li>
        <li>Request output in a specific format — bullet points, tables, or numbered lists</li>
        <li>Use the agent to check your own answers by pasting them back in</li>
      </ul>
    </div>

    <!-- CHAT CTA -->
    <div class="chat-cta">
      <h3>Ready to Study? Start a Chat!</h3>
      <p>Click the chat icon in the bottom-right corner to launch your personal AI Study Generator — powered by IBM watsonx Orchestrate.</p>
    </div>

  </main>

  <!-- FOOTER -->
  <footer>Made with IBM Bob &nbsp;·&nbsp; Smart Study Generator &nbsp;·&nbsp; Powered by IBM watsonx Orchestrate</footer>

  <!-- IBM WATSONX ORCHESTRATE CHAT AGENT -->
  <div id="root"></div>
  <script>
    window.wxOConfiguration = {
      orchestrationID: "undefined",
      hostURL: "https://au-syd.watson-orchestrate.cloud.ibm.com",
      rootElementID: "root",
      deploymentPlatform: "ibmcloud",
      crn: "crn:v1:bluemix:public:watsonx-orchestrate:au-syd:a/0e04832d9c8f4c17aabac7c3a98826e3:2cfefe97-5b80-429f-a9f6-729742fdcd2d::",
      chatOptions: {
        agentId: "7e9c2beb-a3e7-453e-a045-b1093404b4c4"
      }
    };
    setTimeout(function () {
      const script = document.createElement('script');
      script.src = window.wxOConfiguration.hostURL + '/wxochat/wxoLoader.js?embed=true';
      script.addEventListener('load', function () {
        wxoLoader.init();
      });
      document.head.appendChild(script);
    }, 0);
  </script>

</body>
</html>
