<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>README · Othello Chapter 2 · Interactive Learning</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      background: linear-gradient(145deg, #f7f0e8 0%, #e8dfd2 100%);
      font-family: 'Segoe UI', Roboto, system-ui, -apple-system, sans-serif;
      padding: 2rem 1.5rem;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .readme-card {
      max-width: 1000px;
      width: 100%;
      background: rgba(255, 252, 248, 0.92);
      backdrop-filter: blur(6px);
      border-radius: 48px;
      padding: 2.8rem 3rem;
      box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25), 0 0 0 1px rgba(255, 255, 255, 0.5) inset;
      transition: all 0.2s;
      border: 1px solid rgba(255, 245, 235, 0.6);
    }
    .badge-line {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem 1rem;
      margin-bottom: 1.5rem;
      align-items: center;
    }
    .badge {
      background: #1e1e2a;
      color: #faf0e6;
      padding: 0.2rem 1.2rem;
      border-radius: 60px;
      font-size: 0.75rem;
      font-weight: 600;
      letter-spacing: 0.3px;
      text-transform: uppercase;
      box-shadow: 0 2px 6px rgba(0,0,0,0.08);
    }
    .badge.soft {
      background: #d4c9b8;
      color: #2d241b;
    }
    .badge.gold {
      background: #c9a87c;
      color: #1f160e;
    }
    .title {
      font-size: 3.2rem;
      font-weight: 600;
      letter-spacing: -1.5px;
      color: #1f1a14;
      line-height: 1.1;
      margin-bottom: 0.2rem;
      display: flex;
      align-items: center;
      gap: 0.8rem;
      flex-wrap: wrap;
    }
    .title .emoji-big {
      font-size: 3.4rem;
    }
    .subhead {
      font-size: 1.15rem;
      color: #4d4032;
      margin-top: 0.2rem;
      margin-bottom: 2rem;
      border-left: 4px solid #baa992;
      padding-left: 1.2rem;
      font-weight: 400;
      background: #f4ede4;
      border-radius: 0 40px 40px 0;
      padding: 0.5rem 1.5rem;
      display: inline-block;
    }
    .divider {
      width: 100%;
      height: 2px;
      background: linear-gradient(90deg, #d9cdbc, transparent);
      margin: 2rem 0 1.8rem;
    }
    .grid-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.8rem 2.5rem;
    }
    .feature-block {
      background: #faf6f0;
      border-radius: 28px;
      padding: 1.6rem 1.8rem;
      box-shadow: 0 4px 12px rgba(0,0,0,0.02);
      border: 1px solid #e6dbce;
      transition: 0.15s;
    }
    .feature-block:hover {
      border-color: #c9b8a5;
      background: #fcf9f5;
    }
    .feature-block h3 {
      font-weight: 600;
      font-size: 1.2rem;
      color: #2b1f12;
      margin-bottom: 0.5rem;
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }
    .feature-block p, .feature-block li {
      color: #3d352b;
      font-size: 0.98rem;
      line-height: 1.6;
    }
    .feature-block ul {
      list-style: none;
      padding-left: 0;
      margin-top: 0.4rem;
    }
    .feature-block ul li::before {
      content: "✦ ";
      color: #b19b84;
      font-weight: 300;
    }
    .feature-block ul li {
      padding: 0.15rem 0;
    }
    .tech-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem 0.8rem;
      margin-top: 0.6rem;
    }
    .tech-tags span {
      background: #e8dfd2;
      padding: 0.1rem 1.2rem;
      border-radius: 40px;
      font-size: 0.8rem;
      color: #2f261c;
      border: 1px solid #d6cdbe;
    }
    .screenshot-mock {
      background: #1e1a16;
      border-radius: 24px;
      padding: 1.2rem 1.5rem;
      margin: 1.2rem 0 0.8rem;
      color: #d4cdc2;
      font-family: 'Courier New', monospace;
      font-size: 0.85rem;
      border: 1px solid #3f3529;
      box-shadow: 0 8px 18px rgba(0,0,0,0.2);
    }
    .screenshot-mock .line {
      display: flex;
      gap: 1.2rem;
      align-items: center;
      padding: 0.2rem 0;
      border-bottom: 1px solid #2f281f;
    }
    .screenshot-mock .line:last-child { border-bottom: none; }
    .screenshot-mock .prompt { color: #b8a58a; }
    .screenshot-mock .cmd { color: #e6d8c4; }
    .screenshot-mock .output { color: #c9b8a5; }
    .btn-demo {
      display: inline-block;
      margin-top: 0.8rem;
      background: #4d4032;
      color: #faf0e6;
      padding: 0.5rem 2rem;
      border-radius: 60px;
      text-decoration: none;
      font-weight: 500;
      border: 1px solid #6d5d4a;
      transition: 0.15s;
      font-size: 0.95rem;
    }
    .btn-demo:hover {
      background: #2f261c;
      border-color: #8f7b64;
      transform: scale(1.02);
    }
    .footer-note {
      margin-top: 2.2rem;
      padding-top: 1.5rem;
      border-top: 1px solid #d9cdbc;
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 1rem;
      color: #5b4e3e;
      font-size: 0.9rem;
    }
    .footer-note .hearts {
      color: #b35e5e;
    }
    @media (max-width: 720px) {
      .readme-card { padding: 1.8rem; }
      .title { font-size: 2.4rem; }
      .grid-2 { grid-template-columns: 1fr; gap: 1.2rem; }
      .badge-line { gap: 0.3rem; }
    }
    @media (max-width: 480px) {
      .readme-card { padding: 1.2rem; border-radius: 28px; }
      .title { font-size: 1.8rem; }
      .feature-block { padding: 1.2rem; }
    }
  </style>
</head>
<body>
<div class="readme-card">
  <!-- badges -->
  <div class="badge-line">
    <span class="badge">📖 Othello · Chapter 2</span>
    <span class="badge soft">🎯 100 MCQs</span>
    <span class="badge gold">🌸 Flower shower · 💥 Bomb blast</span>
    <span class="badge soft">📚 Word Notes + Analysis</span>
  </div>

  <!-- title -->
  <div class="title">
    <span class="emoji-big">🎭</span> 
    README
    <span style="font-weight:300; font-size:1.8rem; color:#7f6f5c;">·</span>
    <span style="font-weight:300; font-size:1.4rem; color:#7f6f5c;">Interactive Learning</span>
  </div>
  <div class="subhead">
    ⚡ Othello Chapter 2 · full story · word notes · critical analysis · 100 unique MCQs with animations
  </div>

  <div class="divider"></div>

  <!-- grid features -->
  <div class="grid-2">
    <div class="feature-block">
      <h3>📖 Story & Notes</h3>
      <ul>
        <li>Complete retelling of Othello Chapter 2</li>
        <li>15 Word Notes with clickable English → Bengali</li>
        <li>Critical Analysis with 24 key terms & Bengali meanings</li>
        <li>Elegant, responsive design with smooth interactions</li>
      </ul>
      <div class="tech-tags">
        <span>HTML</span><span>CSS</span><span>Vanilla JS</span>
      </div>
    </div>

    <div class="feature-block">
      <h3>🧠 100 Unique MCQs</h3>
      <ul>
        <li>100 hand-crafted questions (no repetition)</li>
        <li>Randomised options for each attempt</li>
        <li>Progress tracking & score display</li>
        <li>Auto-advance after answering</li>
      </ul>
      <div class="tech-tags">
        <span>Interactive</span><span>Randomised</span><span>Self-paced</span>
      </div>
    </div>

    <div class="feature-block">
      <h3>🌸 Flower Shower (Correct)</h3>
      <ul>
        <li>40+ colourful flowers rain down</li>
        <li>Random emojis: 🌸🌺🌻🌷🌹🌼💐</li>
        <li>Gentle floating animation</li>
        <li>Celebratory toast message</li>
      </ul>
      <div class="tech-tags">
        <span>CSS animations</span><span>Emoji</span><span>Positive feedback</span>
      </div>
    </div>

    <div class="feature-block">
      <h3>💥 Bomb Blast (Wrong)</h3>
      <ul>
        <li>Explosive 💥 with shrapnel (💢🔥💫⚡💨)</li>
        <li>6 bombs + 8 shards each</li>
        <li>Dynamic positioning & rotation</li>
        <li>Instant visual feedback</li>
      </ul>
      <div class="tech-tags">
        <span>CSS keyframes</span><span>Dynamic DOM</span><span>Feedback</span>
      </div>
    </div>
  </div>

  <!-- screenshot mock -->
  <div class="screenshot-mock">
    <div class="line"><span class="prompt">📌</span><span class="cmd">Othello · Chapter 2</span><span class="output">│ 100 MCQs</span></div>
    <div class="line"><span class="prompt">📖</span><span class="cmd">Story</span><span class="output">│ Full narrative with word highlights</span></div>
    <div class="line"><span class="prompt">🧠</span><span class="cmd">Analysis</span><span class="output">│ Critical terms + Bengali meanings</span></div>
    <div class="line"><span class="prompt">🌸</span><span class="cmd">Correct →</span><span class="output">Flower shower (40+ flowers)</span></div>
    <div class="line"><span class="prompt">💥</span><span class="cmd">Wrong →</span><span class="output">Bomb blast + shards</span></div>
    <div class="line"><span class="prompt">🏁</span><span class="cmd">Score</span><span class="output">│ Real-time progress & final result</span></div>
  </div>

  <!-- how to use -->
  <div style="margin: 1.8rem 0 0.5rem;">
    <h3 style="font-weight:500; font-size:1.3rem; margin-bottom:0.5rem;">🚀 How to use</h3>
    <div style="display: flex; flex-wrap: wrap; gap: 0.8rem 2rem; background: #f4ede4; padding: 1rem 1.8rem; border-radius: 60px;">
      <span><strong>1.</strong> Read the story</span>
      <span><strong>2.</strong> Click any word for Bengali</span>
      <span><strong>3.</strong> Explore critical analysis</span>
      <span><strong>4.</strong> Answer 100 MCQs</span>
      <span><strong>5.</strong> Enjoy animations!</span>
    </div>
  </div>

  <!-- footer -->
  <div class="footer-note">
    <span>📚 <strong>Othello</strong> · Chapter 2 · Interactive Edition</span>
    <span class="hearts">❤️ crafted with care</span>
    <span>🌐 single HTML · no dependencies</span>
  </div>
</div>
</body>
</html># Othello-
Othello
