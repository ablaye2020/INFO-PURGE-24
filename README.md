# INFO-PURGE-24
Joyboy 
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>INFO PURGE 24 - LIVE</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;500;700&display=swap');

    :root {
      --bg: #000000;
      --bg-alt: #0d0d0d;
      --text: #f0f0f0;
      --accent: #ff0000;
      --accent2: #8b0000;
      --border: #1a1a1a;
      --news: #ffcc00;
      --live: #00ff00;
    }

  .light-mode {
      --bg: #f0f0f0;
      --bg-alt: #ffffff;
      --text: #0d0d0d;
      --accent: #c00000;
      --accent2: #ff3333;
      --border: #ddd;
      --news: #d4a000;
      --live: #00aa00;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Rajdhani', sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.6;
      overflow-x: hidden;
      transition: all 0.4s ease;
    }

    /* TRANSITION GLITCH ENTRE PAGES */
   .glitch-transition {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: var(--bg);
      z-index: 9999;
      display: none;
      pointer-events: none;
    }

   .glitch-transition.active {
      display: block;
      animation: glitchFlash 0.4s steps(2, end);
    }

    @keyframes glitchFlash {
      0% { opacity: 0; }
      20% { opacity: 1; background: #ff0000; transform: skew(5deg); }
      40% { opacity: 1; background: #00ffff; transform: skew(-5deg); }
      60% { opacity: 1; background: var(--bg); transform: skew(3deg); }
      80% { opacity: 1; background: #ffffff; transform: skew(-3deg); }
      100% { opacity: 0; transform: skew(0); }
    }

    /* BREAKING NEWS TICKER */
   .breaking-news {
      background: var(--accent);
      color: #fff;
      padding: 0.5rem 0;
      position: sticky;
      top: 0;
      z-index: 200;
      overflow: hidden;
      white-space: nowrap;
      box-shadow: 0 2px 10px rgba(255,0,0,0.5);
    }

   .breaking-news-content {
      display: inline-block;
      padding-left: 100%;
      animation: scroll-left 25s linear infinite;
      font-weight: 700;
      font-family: 'Orbitron', sans-serif;
    }

   .breaking-news-content span {
      margin: 0 3rem;
    }

    @keyframes scroll-left {
      0% { transform: translateX(0); }
      100% { transform: translateX(-100%); }
    }

    /* Vidéo YouTube en fond */
   .video-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -2;
      pointer-events: none;
      opacity: 0.2;
    }

   .video-bg iframe {
      width: 100vw;
      height: 100vh;
      transform: scale(1.5);
      filter: blur(3px) grayscale(80%);
    }

  .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle, transparent 0%, var(--bg) 90%);
      z-index: -1;
      pointer-events: none;
    }

    #particles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      pointer-events: none;
    }

    header {
      background: rgba(13, 13, 13, 0.85);
      backdrop-filter: blur(10px);
      border-bottom: 2px solid var(--accent);
      position: sticky;
      top: 40px;
      z-index: 100;
    }

  .container {
      max-width: 1400px;
      margin: 0 auto;
      padding: 0 20px;
    }

    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 0;
    }

  .logo-wrapper {
      display: flex;
      align-items: center;
      gap: 1rem;
    }

  .logo {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.8rem;
      font-weight: 900;
      color: var(--accent);
      text-shadow: 0 0 10px var(--accent);
      animation: glitch 3s infinite;
    }

  .live-badge {
      background: var(--live);
      color: #000;
      padding: 0.2rem 0.6rem;
      border-radius: 4px;
      font-weight: 900;
      font-size: 0.8rem;
      animation: pulse 1.5s infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; box-shadow: 0 0 10px var(--live); }
      50% { opacity: 0.6; box-shadow: 0 0 5px var(--live); }
    }

    @keyframes glitch {
      0%, 100% { text-shadow: 0 0 10px var(--accent); }
      25% { text-shadow: -2px 0 var(--accent), 2px 0 cyan; }
      50% { text-shadow: 2px 0 var(--accent), -2px 0 lime; }
    }

  .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

  .nav-links a {
      color: var(--text);
      text-decoration: none;
      font-weight: 700;
      font-size: 1.1rem;
      cursor: pointer;
      position: relative;
      transition: 0.3s;
    }

  .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -5px;
      left: 0;
      width: 0;
      height: 2px;
      background: var(--accent);
      transition: width 0.3s;
    }

  .nav-links a:hover::after,.nav-links a.active::after {
      width: 100%;
    }

  .nav-links a:hover {
      color: var(--accent);
      text-shadow: 0 0 8px var(--accent);
    }

  .controls {
      display: flex;
      gap: 0.5rem;
      align-items: center;
    }

  .btn {
      background: var(--accent);
      color: white;
      border: none;
      padding: 0.6rem 1rem;
      border-radius: 4px;
      cursor: pointer;
      font-weight: 700;
      font-family: 'Rajdhani', sans-serif;
      transition: all 0.3s;
      text-transform: uppercase;
      font-size: 0.9rem;
    }

  .btn:hover {
      background: var(--accent2);
      transform: scale(1.05);
      box-shadow: 0 0 15px var(--accent);
    }

  .hamburger {
      display: none;
      flex-direction: column;
      gap: 4px;
      cursor: pointer;
    }

  .hamburger span {
      width: 25px;
      height: 3px;
      background: var(--text);
      transition: 0.3s;
    }

    main {
      display: grid;
      grid-template-columns: 1fr 350px;
      gap: 2rem;
      margin-top: 2rem;
    }

    section {
      padding: 2rem 0;
      display: none;
      animation: fadeIn 0.6s ease;
    }

    section.active {
      display: block;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    h1 {
      font-family: 'Orbitron', sans-serif;
      font-size: 3rem;
      margin-bottom: 1rem;
      color: var(--accent);
      text-transform: uppercase;
      text-shadow: 0 0 20px var(--accent);
    }

    h2 {
      font-family: 'Orbitron', sans-serif;
      font-size: 2rem;
      margin-bottom: 1.5rem;
      border-left: 4px solid var(--accent);
      padding-left: 1rem;
    }

    /* TCHAT LIVE */
  .live-chat {
      background: rgba(13, 13, 13, 0.9);
      border: 2px solid var(--accent);
      border-radius: 8px;
      position: sticky;
      top: 120px;
      height: calc(100vh - 140px);
      display: flex;
      flex-direction: column;
      backdrop-filter: blur(10px);
    }

  .chat-header {
      background: var(--accent);
      padding: 0.8rem;
      font-weight: 900;
      font-family: 'Orbitron', sans-serif;
      text-align: center;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

  .chat-messages {
      flex: 1;
      overflow-y: auto;
      padding: 1rem;
      display: flex;
      flex-direction: column;
      gap: 0.8rem;
    }

  .chat-msg {
      animation: slideInMsg 0.3s ease;
    }

    @keyframes slideInMsg {
      from { opacity: 0; transform: translateX(-20px); }
      to { opacity: 1; transform: translateX(0); }
    }

  .chat-msg.author {
      font-weight: 700;
      color: var(--accent);
      font-size: 0.9rem;
    }

  .chat-msg.text {
      font-size: 0.95rem;
    }

  .chat-msg.system {
      text-align: center;
      color: var(--news);
      font-style: italic;
      font-size: 0.85rem;
    }

  .chat-input {
      border-top: 1px solid var(--border);
      padding: 1rem;
      display: flex;
      gap: 0.5rem;
    }

  .chat-input input {
      flex: 1;
      background: var(--bg);
      border: 1px solid var(--border);
      color: var(--text);
      padding: 0.5rem;
      border-radius: 4px;
      font-family: inherit;
    }

  .hero {
      text-align: center;
      padding: 4rem 0;
    }

  .team {
      display: flex;
      justify-content: center;
      gap: 1.5rem;
      flex-wrap: wrap;
      margin: 3rem 0;
    }

  .member {
      background: rgba(13, 13, 13, 0.7);
      border: 1px solid var(--border);
      padding: 1.5rem;
      border-radius: 8px;
      text-align: center;
      min-width: 140px;
      transition: all 0.3s;
      animation: float 3s ease-in-out infinite;
    }

  .member:nth-child(2) { animation-delay: 0.2s; }
  .member:nth-child(3) { animation-delay: 0.4s; }
  .member:nth-child(4) { animation-delay: 0.6s; }
  .member:nth-child(5) { animation-delay: 0.8s; }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }

  .member:hover {
      border-color: var(--accent);
      transform: scale(1.1) translateY(-10px);
      box-shadow: 0 0 20px var(--accent);
    }

  .member h3 {
      color: var(--accent);
      font-family: 'Orbitron', sans-serif;
    }

  .countdown {
      background: rgba(13, 13, 13, 0.9);
      border: 2px solid var(--accent);
      padding: 2rem;
      border-radius: 12px;
      margin: 2rem auto;
      max-width: 600px;
      box-shadow: 0 0 30px rgba(255, 0, 0, 0.3);
    }

    #timer {
      font-size: 3.5rem;
      font-weight: 700;
      color: var(--accent);
      font-family: 'Orbitron', monospace;
      text-shadow: 0 0 15px var(--accent);
    }

  .cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2rem;
      margin-top: 2rem;
    }

  .card {
      background: rgba(13, 13, 13, 0.8);
      border: 1px solid var(--border);
      padding: 2rem;
      border-radius: 8px;
      transition: all 0.4s;
      backdrop-filter: blur(5px);
    }

  .card:hover {
      transform: translateY(-8px) scale(1.02);
      border-color: var(--accent);
      box-shadow: 0 10px 30px rgba(255, 0, 0, 0.4);
    }

  .card h3 {
      color: var(--accent);
      margin-bottom: 1rem;
      font-family: 'Orbitron', sans-serif;
    }

  .luffy-player {
      background: rgba(13, 13, 13, 0.9);
      border: 2px solid var(--accent);
      padding: 2rem;
      border-radius: 12px;
      margin: 3rem auto;
      text-align: center;
      max-width: 800px;
    }

  .luffy-player iframe {
      width: 100%;
      height: 450px;
      border-radius: 8px;
      margin-top: 1rem;
    }

    footer {
      background: rgba(13, 13, 13, 0.9);
      border-top: 1px solid var(--border);
      text-align: center;
      padding: 2rem 0;
      margin-top: 4rem;
      grid-column: 1 / -1;
    }

    @media (max-width: 1024px) {
      main {
        grid-template-columns: 1fr;
      }
    .live-chat {
        position: relative;
        top: 0;
        height: 400px;
        order: -1;
      }
    }

    @media (max-width: 768px) {
      header { top: 32px; }
    .nav-links {
        display: none;
        position: absolute;
        top: 100%;
        left: 0;
        right: 0;
        background: rgba(13, 13, 13, 0.95);
        flex-direction: column;
        padding: 1rem;
        border-bottom: 2px solid var(--accent);
      }
    .nav-links.show { display: flex; }
    .hamburger { display: flex; }
      h1 { font-size: 2rem; }
      #timer { font-size: 2rem; }
    .luffy-player iframe { height: 250px; }
    .breaking-news { font-size: 0.8rem; }
    }
  </style>
</head>
<body>
  <!-- TRANSITION GLITCH -->
  <div class="glitch-transition" id="glitchTransition"></div>

  <!-- AUDIO POUR ALERTES -->
  <audio id="alertSound" preload="auto">
    <source src="data:audio/wav;base64,UklGRiQAAABXQVZFZm10IBAAAAABAAEAQB8AAEAfAAABAAgAZGF0YQAAAAA=" type="audio/wav">
  </audio>

  <!-- BREAKING NEWS TICKER -->
  <div class="breaking-news">
    <div class="breaking-news-content" id="newsTicker">
      <span>🔴 BREAKING: JOYBOY DÉCLARE L'ÉTAT D'URGENCE MÉDIATIQUE</span>
      <span>⚠️ NIGHT SIGNALE DES MOUVEMENTS SUSPECTS SECTEUR 7</span>
      <span>📡 𝚂𝙷𝙰𝙳𝙾𝚆 A PIRATÉ LES FRÉQUENCES DU GOUVERNEMENT</span>
      <span>🚨 DIANNY INFILTRE LE BUNKER DES NOUVEAUX PÈRES FONDATEURS</span>
      <span>📊 SHIRO: 87% DES CITOYENS NE FONT PAS CONFIANCE AUX CHIFFRES OFFICIELS</span>
    </div>
  </div>

  <!-- Vidéo YouTube en fond -->
  <div class="video-bg">
    <iframe
      src="https://www.youtube.com/embed/zE2c03IOy_I?autoplay=1&mute=1&loop=1&playlist=zE2c03IOy_I&controls=0&showinfo=0&rel=0&modestbranding=1"
      frameborder="0"
      allow="autoplay; encrypted-media"
      allowfullscreen>
    </iframe>
  </div>
  <div class="overlay"></div>
  <canvas id="particles"></canvas>

  <header>
    <div class="container">
      <nav>
        <div class="logo-wrapper">
          <div class="logo">INFO PURGE 24</div>
          <div class="live-badge">● LIVE</div>
        </div>
        <ul class="nav-links" id="navLinks">
          <li><a data-page="accueil" class="active">DIRECT</a></li>
          <li><a data-page="equipe">L'ÉQUIPE</a></li>
          <li><a data-page="debats">DÉBATS</a></li>
          <li><a data-page="archives">ARCHIVES</a></li>
        </ul>
        <div class="controls">
          <button class="btn" id="themeBtn">☀️</button>
          <button class="btn" id="unmuteBtn">🔇</button>
          <div class="hamburger" id="hamburger">
            <span></span><span></span><span></span>
          </div>
        </div>
      </nav>
    </div>
  </header>

  <div class="container">
    <main>
      <div>
        <!-- Page Accueil -->
        <section id="accueil" class="active">
          <div class="hero">
            <h1>LA VOIX DE LA PURGE</h1>
            <p>Info en continu. Sans filtre. Sans pitié. Dirigé par Joyboy, accompagné de Night, Dianny, SHIRO et 𝚂𝙷𝙰𝙳𝙾𝚆.</p>

            <div class="luffy-player">
              <h3>☠️ LE CRI DU FUTUR ROI DES PIRATES ☠️</h3>
              <p>"Je deviendrai le roi des pirates!" - Luffy</p>
              <iframe
                src="https://www.youtube.com/embed/zE2c03IOy_I?autoplay=0&controls=1&modestbranding=1&rel=0"
                title="Luffy - Roi des Pirates"
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                allowfullscreen>
              </iframe>
            </div>

            <div class="countdown">
              <h3>PROCHAINE PURGE DANS :</h3>
              <div id="timer">00:00:00:00</div>
            </div>
          </div>

          <h2>FLASH INFO</h2>
          <div class="cards">
            <div class="card">
              <h3>ALERTE NIGHT</h3>
              <p>Night rapporte une hausse de 300% des ventes d'armes blanches. Le gouvernement parle de "préparation citoyenne".</p>
            </div>
            <div class="card">
              <h3>ENQUÊTE DIANNY</h3>
              <p>Dianny a infiltré un bunker de luxe. Prix d'entrée : 2 millions. Champagne inclus, mais pas de garantie de survie.</p>
            </div>
            <div class="card">
              <h3>ANALYSE SHIRO</h3>
              <p>SHIRO décrypte : Les riches ne purgent pas, ils sous-traitent. Le marché du mercenariat explose.</p>
            </div>
          </div>
        </section>

        <!-- Page Équipe -->
        <section id="equipe">
          <h1>L'ÉQUIPE INFO PURGE 24</h1>
          <p>Les 5 voix que le gouvernement veut faire taire.</p>

          <div class="team">
            <div class="member">
              <h3>JOYBOY</h3>
              <p>Rédac Chef</p>
              <small>"Le rire est une arme"</small>
            </div>
            <div class="member">
              <h3>NIGHT</h3>
              <p>Terrain</p>
              <small>"Je vois tout dans le noir"</small>
            </div>
            <div class="member">
              <h3>DIANNY</h3>
              <p>Infiltration</p>
              <small>"Aucune porte ne me résiste"</small>
            </div>
            <div class="member">
              <h3>SHIRO</h3>
              <p>Analyse</p>
              <small>"Les chiffres ne mentent pas"</small>
            </div>
            <div class="member">
              <h3>𝚂𝙷𝙰𝙳𝙾𝚆</h3>
              <p>Cybersécurité</p>
              <small>"Invisible, invincible"</small>
            </div>
          </div>
        </section>

        <!-- Page Débats -->
        <section id="debats">
          <h1>DÉBATS INTERDITS</h1>
          <p>Les questions que Joyboy pose et que personne n'ose répondre.</p>

          <div class="cards">
            <div class="card">
              <h3>DÉBAT JOYBOY</h3>
              <p>Si la Purge rend la société meilleure, pourquoi les Nouveaux Pères Fondateurs se cachent dans des bunkers?</p>
            </div>
            <div class="card">
              <h3>DÉBAT 𝚂𝙷𝙰𝙳𝙾𝚆</h3>
              <p>Le dark web pendant la Purge : anarchie totale ou dernier espace de loi? Nos hackers ont la réponse.</p>
            </div>
            <div class="card">
              <h3>DÉBAT NIGHT + DIANNY</h3>
              <p>Reportage croisé : Une nuit avec les purgeurs vs une nuit avec ceux qui se cachent. Qui dort le mieux?</p>
            </div>
          </div>
        </section>

        <!-- Page Archives -->
        <section id="archives">
          <h1>ARCHIVES CLASSÉES</h1>
          <p>Ce qu'on a filmé et que l'État a voulu censurer. Merci 𝚂𝙷𝙰𝙳𝙾𝚆 pour la sauvegarde.</p>

          <div class="cards">
            <div class="card">
              <h3>PURGE 2023</h3>
              <p>Documentaire SHIRO : 12h dans le quartier le plus pauvre de la ville. 0 survivant. 0 média sur place. Sauf nous.</p>
            </div>
            <div class="card">
              <h3>INTERVIEW CHOC</h3>
              <p>Dianny face à un "nettoyeur" du gouvernement. "On m'a payé pour tuer 20 personnes. J'en ai fait 23. Bonus."</p>
            </div>
            <div class="card">
              <h3>FUITE NIGHT</h3>
              <p>Night a volé les plans des bunkers gouvernementaux. Spoiler : y'a de la place pour eux, pas pour toi.</p>
            </div>
          </div>
        </section>
      </div>

      <!-- TCHAT LIVE -->
      <aside class="live-chat">
        <div class="chat-header">
          <span>💬 TCHAT LIVE</span>
          <span id="viewerCount">1,247</span>
        </div>
        <div class="chat-messages" id="chatMessages">
          <div class="chat-msg system">Joyboy a lancé le direct</div>
        </div>
        <div class="chat-input">
          <input type="text" id="chatInput" placeholder="Message..." maxlength="200">
          <button class="btn" id="sendChat">➤</button>
        </div>
      </aside>
    </main>
  </div>

  <footer>
    <div class="container">
      <p>&copy; 2026 INFO PURGE 24 - Dirigé par Joyboy, Night, Dianny, SHIRO, 𝚂𝙷𝙰𝙳𝙾𝚆</p>
      <p><small>"Ils peuvent couper le signal. Pas la vérité."</small></p>
    </div>
  </footer>

  <script>
    // TRANSITION GLITCH
    function triggerGlitch() {
      const glitch = document.getElementById('glitchTransition');
      glitch.classList.add('active');
      setTimeout(() => glitch.classList.remove('active'), 400);
    }

    // Navigation avec transition
    const navLinks = document.querySelectorAll('[data-page]');
    const sections = document.querySelectorAll('section');
    navLinks.forEach(link => {
      link.addEventListener('click', (e) => {
        e.preventDefault();
        triggerGlitch();
        setTimeout(() => {
          const page = link.getAttribute('data-page');
          navLinks.forEach(l => l.classList.remove('active'));
          link.classList.add('active');
          sections.forEach(s => s.classList.remove('active'));
          document.getElementById(page).classList.add('active');
          document.getElementById('navLinks').classList.remove('show');
          window.scrollTo(0, 0);
        }, 200);
      });
    });

    // Hamburger
    document.getElementById('hamburger').addEventListener('click', () => {
      document.getElementById('navLinks').classList.toggle('show');
    });

    // Thème
    const themeBtn = document.getElementById('themeBtn');
    themeBtn.addEventListener('click', () => {
      document.body.classList.toggle('light-mode');
      themeBtn.textContent = document.body.classList.contains('light-mode')? '🌙' : '☀️';
    });

    // Unmute vidéo
    let isMuted = true;
    document.getElementById('unmuteBtn').addEventListener('click', () => {
      const iframe = document.querySelector('.video-bg iframe');
      isMuted =!isMuted;
      const src = iframe.src;
      if (isMuted) {
        iframe.src = src.replace('mute=0', 'mute=1');
        document.getElementById('unmuteBtn').textContent = '🔇';
      } else {
        iframe.src = src.replace('mute=1', 'mute=0');
        document.getElementById('unmuteBtn').textContent = '🔊';
      }
    });

    // Compte à rebours
    function updateCountdown() {
      const purgeDate = new Date('2027-03-21T19:00:00').getTime();
      const now = new Date().getTime();
      const diff = purgeDate - now;
      if (diff <= 0) {
        document.getElementById('timer').textContent = 'EN COURS';
        return;
      }
      const d = Math.floor(diff / (1000 * 60 * 60 * 24));
      const h = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const m = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
      const s = Math.floor((diff % (1000 * 60)) / 1000);
      document.getElementById('timer').textContent =
        `${String(d).padStart(2, '0')}:${String(h).padStart(2, '0')}:${String(m).padStart(2, '0')}:${String(s).padStart(2, '0')}`;
    }
    setInterval(updateCountdown, 1000);
    updateCountdown();

    // BREAKING NEWS DYNAMIQUE + ALERTE SONORE
    const newsArray = [
      "🔴 BREAKING: JOYBOY DÉCLARE L'ÉTAT D'URGENCE MÉDIATIQUE",
      "⚠️ NIGHT SIGNALE DES MOUVEMENTS SUSPECTS SECTEUR 7",
      "📡 𝚂𝙷𝙰𝙳𝙾𝚆 A PIRATÉ LES FRÉQUENCES DU GOUVERNEMENT",
      "🚨 DIANNY INFILTRE LE BUNKER DES NOUVEAUX PÈRES FONDATEURS",
      "📊 SHIRO: 87% DES CITOYENS NE FONT PAS CONFIANCE AUX CHIFFRES OFFICIELS",
      "🔥 ALERTE: STOCK DE MASQUES ANTI-GAZ ÉPUISÉ EN 12 MINUTES",
      "💀 LE TAUX DE SURVIE CHUTE À 23% DANS LE DISTRICT NORD",
      "📢 JOYBOY: 'ILS VEULENT NOUS FAIRE TAIRE. ON CRIE PLUS FORT.'"
    ];

    function playAlert() {
      const audio = document.getElementById('alertSound');
      // Bip sonore généré
      const ctx = new (window.AudioContext || window.webkitAudioContext)();
      const osc = ctx.createOscillator();
      const gain = ctx.createGain();
      osc.connect(gain);
      gain.connect(ctx.destination);
      osc.frequency.value = 800;
      gain.gain.setValueAtTime(0.3, ctx.currentTime);
      gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.2);
      osc.start(ctx.currentTime);
      osc.stop(ctx.currentTime + 0.2);
    }

    let newsIndex = 0;
    setInterval(() => {
      newsIndex = (newsIndex + 1) % newsArray.length;
      const ticker = document.getElementById('newsTicker');
      ticker.innerHTML = newsArray.map(n => `<span>${n}</span>`).join('');
      playAlert(); // Joue le bip à chaque nouvelle news

      // Ajoute aussi au tchat
      addChatMessage('SYSTÈME', newsArray[newsIndex], true);
    }, 20000);

    // TCHAT LIVE SIMULÉ
    const chatMessages = document.getElementById('chatMessages');
    const chatInput = document.getElementById('chatInput');
    const sendChat = document.getElementById('sendChat');
    const fakeUsers = ['Night', 'Dianny', 'SHIRO', '𝚂𝙷𝙰𝙳𝙾𝚆', 'Anon_447', 'Survivor_23', 'Joyboy'];
    const fakeMessages = [
      "Ils mentent sur les chiffres",
      "J'ai vu les camions entrer dans le secteur 9",
      "Restez cachés ce soir",
      "𝚂𝙷𝙰𝙳𝙾𝚆 a leak les fréquences",
      "C'est un massacre organisé",
      "Mon voisin a disparu hier",
      "Joyboy dit vrai depuis le début",
      "Ils coupent internet à 18h",
      "Dianny est une légende",
      "SHIRO avait raison sur tout"
    ];

    function addChatMessage(author, text, isSystem = false) {
      const msg = document.createElement('div');
      msg.className = isSystem? 'chat-msg system' : 'chat-msg';
      if (!isSystem) {
        msg.innerHTML = `<div class="author">${author}:</div><div class="text">${text}</div>`;
      } else {
        msg.textContent = text;
      }
      chatMessages.appendChild(msg);
      chatMessages.scrollTop = chatMessages.scrollHeight;

      // Limite à 50 messages
      if (chatMessages.children.length > 50) {
        chatMessages.removeChild(chatMessages.firstChild);
      }
    }

    // Messages auto du tchat
    setInterval(() => {
      const user = fakeUsers[Math.floor(Math.random()
