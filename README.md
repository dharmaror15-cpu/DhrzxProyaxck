<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dharma - Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<style>
/* CSS Dasar */
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family: 'Inter', sans-serif; background:#080000; color:#fff; overflow-x:hidden; }
h1, h2, h3, h4, .logo, .stat h3 { font-family: 'Space Grotesk', sans-serif; }

/* Video Background */
#bgVideo { position:fixed; top:0; left:0; width:100%; height:100%; object-fit:cover; z-index:-3; opacity:0.35; filter:brightness(0.4) saturate(1.5) hue-rotate(-10deg); }
.overlay { position:fixed; inset:0; z-index:-2; background: radial-gradient(circle at 20% 30%, rgba(255,0,48,0.3), transparent 60%), linear-gradient(180deg, rgba(8,0,0,0.7), rgba(20,0,5,0.9)); }

/* Navigasi */
nav { position:fixed; top:0; left:0; width:100%; display:flex; justify-content:space-between; align-items:center; padding:20px 5%; z-index:100; background:rgba(12,0,3,0.8); backdrop-filter:blur(15px); border-bottom:1px solid rgba(255,0,48,0.2); }
.logo { display:flex; align-items:center; gap:10px; font-size:1.5rem; font-weight:700; }
.logo-icon { width:35px; height:35px; background:linear-gradient(135deg,#ff0030,#8b0000); border-radius:10px; display:grid; place-items:center; box-shadow:0 0 15px rgba(255,0,48,0.5); }
.logo-icon svg { width:20px; height:20px; fill:#fff; }
.logo span { background:linear-gradient(90deg,#fff,#ff6680); -webkit-background-clip:text; -webkit-text-fill-color:transparent; }
nav ul { display:flex; list-style:none; gap:20px; }
nav a { color:#c98890; text-decoration:none; font-size:0.9rem; font-weight:500; transition:0.3s; }
nav a:hover { color:#fff; text-shadow:0 0 10px #ff0030; }

/* Hero Section */
.hero { min-height:100vh; display:flex; flex-direction:column; justify-content:center; align-items:center; text-align:center; padding:100px 20px 60px; }
.badge { display:inline-flex; align-items:center; gap:8px; padding:8px 16px; background:rgba(255,0,48,0.1); border:1px solid rgba(255,0,48,0.3); border-radius:30px; font-size:0.8rem; color:#ff99a8; margin-bottom:25px; backdrop-filter:blur(10px); }
.dot { width:8px; height:8px; background:#00ff88; border-radius:50%; box-shadow:0 0 10px #00ff88; animation:pulse 1.5s infinite; }
@keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.5;transform:scale(0.8)} }

.hero h1 { font-size:clamp(2.5rem, 8vw, 4.5rem); font-weight:700; line-height:1.1; margin-bottom:15px; }
.grad { background:linear-gradient(90deg, #ff0030, #ff6680, #ff0030); background-size:200% auto; -webkit-background-clip:text; -webkit-text-fill-color:transparent; animation:shine 3s linear infinite; }
@keyframes shine { to { background-position:200% center; } }
.hero h2 { font-size:clamp(1rem, 4vw, 1.5rem); color:#d4a8ae; margin-bottom:30px; }
.hero p { color:#b07a82; max-width:600px; line-height:1.6; margin-bottom:40px; font-size:1rem; }

.btn { display:inline-flex; align-items:center; gap:8px; padding:14px 28px; border-radius:30px; font-weight:600; text-decoration:none; transition:0.3s; border:none; font-family:inherit; font-size:0.95rem; cursor:pointer; }
.btn-primary { background:linear-gradient(135deg, #ff0030, #d4002a); color:#fff; box-shadow:0 5px 20px rgba(255,0,48,0.4); }
.btn-primary:hover { transform:translateY(-3px); box-shadow:0 10px 30px rgba(255,0,48,0.7); }
.btn-outline { background:rgba(255,0,48,0.1); color:#ff8090; border:1px solid rgba(255,0,48,0.4); }
.btn-outline:hover { background:rgba(255,0,48,0.2); color:#fff; transform:translateY(-3px); }
.hero-btns { display:flex; gap:15px; flex-wrap:wrap; justify-content:center; margin-bottom:50px; }

/* Stats */
.stats { display:flex; gap:20px; justify-content:center; flex-wrap:wrap; }
.stat { background:rgba(255,255,255,0.03); border:1px solid rgba(255,0,48,0.2); padding:15px 30px; border-radius:15px; backdrop-filter:blur(10px); }
.stat h3 { font-size:2rem; color:#ff0030; margin-bottom:5px; }
.stat p { font-size:0.75rem; color:#8a4a52; text-transform:uppercase; letter-spacing:1px; }

/* Bagian Umum */
.section { padding:80px 5%; max-width:1100px; margin:0 auto; }
.section-title { text-align:center; margin-bottom:50px; }
.section-title span { display:inline-block; font-size:0.75rem; color:#ff0030; text-transform:uppercase; letter-spacing:2px; margin-bottom:10px; font-weight:600; }
.section-title h2 { font-size:2rem; font-weight:700; }

/* About */
.about-grid { display:grid; grid-template-columns:1fr 1.5fr; gap:50px; align-items:center; }
.avatar { width:250px; height:250px; margin:0 auto; border-radius:30px; background:rgba(255,0,48,0.1); border:1px solid rgba(255,0,48,0.3); display:grid; place-items:center; box-shadow:0 20px 40px rgba(255,0,48,0.2); }
.avatar svg { width:50%; height:50%; stroke:#ff0030; filter:drop-shadow(0 0 15px #ff0030); }
.about-text h3 { font-size:1.8rem; margin-bottom:15px; }
.about-text p { color:#b07a82; line-height:1.8; margin-bottom:15px; }
.about-text strong { color:#fff; }

/* Sosmed */
.sosmed { display:flex; gap:15px; margin-top:25px; flex-wrap:wrap; }
.sosmed a { display:flex; align-items:center; gap:10px; padding:12px 20px; background:rgba(255,255,255,0.03); border:1px solid rgba(255,0,48,0.3); border-radius:12px; color:#d4a8ae; text-decoration:none; font-weight:600; transition:0.3s; }
.sosmed a:hover { background:rgba(255,0,48,0.15); color:#fff; border-color:#ff0030; transform:translateY(-3px); }
.sosmed svg { width:20px; height:20px; fill:#ff0030; }

/* Skills */
.skills-grid { display:grid; grid-template-columns:repeat(auto-fit, minmax(280px, 1fr)); gap:20px; }
.skill { background:rgba(255,255,255,0.03); border:1px solid rgba(255,0,48,0.2); padding:25px; border-radius:16px; backdrop-filter:blur(10px); }
.skill-header { display:flex; justify-content:space-between; align-items:center; margin-bottom:15px; }
.skill-name { display:flex; align-items:center; gap:10px; font-weight:600; font-size:1.1rem; }
.skill-icon { width:35px; height:35px; background:rgba(0,0,0,0.4); border-radius:8px; display:grid; place-items:center; }
.skill-icon svg { width:22px; height:22px; }
.skill-pct { color:#ff0030; font-weight:700; font-size:1.1rem; }
.progress-bg { height:8px; background:rgba(255,0,48,0.15); border-radius:10px; overflow:hidden; }
.progress-bar { height:100%; background:linear-gradient(90deg, #ff0030, #ff6680); border-radius:10px; }

/* Projects */
.projects-grid { display:grid; grid-template-columns:repeat(auto-fit, minmax(300px, 1fr)); gap:20px; }
.project-card { background:rgba(255,255,255,0.03); border:1px solid rgba(255,0,48,0.2); padding:25px; border-radius:16px; display:flex; flex-direction:column; transition:0.3s; backdrop-filter:blur(10px); }
.project-card:hover { border-color:#ff0030; transform:translateY(-5px); box-shadow:0 10px 30px rgba(255,0,48,0.2); }
.project-card h3 { font-size:1.3rem; margin-bottom:10px; color:#fff; }
.project-card p { color:#b07a82; font-size:0.9rem; line-height:1.6; margin-bottom:20px; flex-grow:1; }
.project-btn { display:inline-block; text-align:center; padding:10px 20px; background:rgba(255,0,48,0.1); color:#ff6680; border:1px solid rgba(255,0,48,0.4); border-radius:10px; text-decoration:none; font-weight:600; font-size:0.9rem; transition:0.3s; }
.project-card:hover .project-btn { background:linear-gradient(135deg, #ff0030, #d4002a); color:#fff; border-color:transparent; }

/* Contact */
.contact-grid { display:grid; grid-template-columns:1fr 1.2fr; gap:40px; }
.contact-info p { color:#b07a82; line-height:1.6; margin-bottom:25px; }
.c-item { display:flex; align-items:center; gap:15px; margin-bottom:15px; color:#d4a8ae; }
.c-icon { width:40px; height:40px; background:rgba(255,0,48,0.1); border:1px solid rgba(255,0,48,0.3); border-radius:10px; display:grid; place-items:center; }
.c-icon svg { width:18px; height:18px; fill:#ff0030; }
.contact-form { background:rgba(255,255,255,0.03); border:1px solid rgba(255,0,48,0.2); padding:30px; border-radius:16px; }
.input-group { margin-bottom:20px; position:relative; }
.input-group input, .input-group textarea { width:100%; padding:15px; background:rgba(0,0,0,0.3); border:1px solid rgba(255,0,48,0.2); border-radius:10px; color:#fff; font-family:inherit; font-size:0.95rem; outline:none; transition:0.3s; }
.input-group input:focus, .input-group textarea:focus { border-color:#ff0030; box-shadow:0 0 10px rgba(255,0,48,0.2); }

/* Footer */
footer { text-align:center; padding:30px; border-top:1px solid rgba(255,0,48,0.1); color:#6a4a4e; font-size:0.85rem; margin-top:50px; }
footer span { color:#ff0030; font-weight:600; }

/* Responsive */
@media (max-width: 850px) {
  .about-grid, .contact-grid { grid-template-columns:1fr; gap:40px; text-align:center; }
  .sosmed { justify-content:center; }
  nav ul { display:none; }
  .hero h1 { font-size:2.5rem; }
}
</style>
</head>
<body>

<!-- Video background -->
<video id="bgVideo" autoplay muted loop playsinline>
  <source src="https://cdn.pixabay.com/video/2023/10/22/185808-877653484_large.mp4" type="video/mp4">
</video>
<div class="overlay"></div>

<!-- Navigasi -->
<nav>
  <div class="logo">
    <div class="logo-icon">
      <svg viewBox="0 0 24 24"><path d="M12 2L2 7l10 5 10-5-10-5zm0 9l2.5-1.25L12 8.5l-2.5 1.25L12 11zm0 2.5l-5-2.5-5 2.5L12 22l10-8.5-5-2.5-5 2.5z"/></svg>
    </div>
    <span>Dharma</span>
  </div>
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#about">Tentang</a></li>
    <li><a href="#skills">Skill</a></li>
    <li><a href="#projects">Proyek</a></li>
    <li><a href="#contact">Kontak</a></li>
  </ul>
</nav>

<!-- Hero -->
<section class="hero" id="home">
  <div class="badge"><span class="dot"></span> Tersedia untuk kolaborasi</div>
  <h1>Halo, saya <br><span class="grad">Dharma</span></h1>
  <h2>Web Developer & Python Enthusiast</h2>
  <p>Membangun project kreatif lewat kode — dari game sederhana sampai simulasi edukatif.</p>
  
  <div class="hero-btns">
    <a href="#projects" class="btn btn-primary">Lihat Proyek</a>
    <a href="#contact" class="btn btn-outline">Hubungi Saya</a>
  </div>

  <div class="stats">
    <div class="stat"><h3>2</h3><p>Bahasa</p></div>
    <div class="stat"><h3>1</h3><p>Tahun Belajar</p></div>
    <div class="stat"><h3>5</h3><p>Project</p></div>
  </div>
</section>

<!-- About -->
<section class="section" id="about">
  <div class="section-title">
    <span>Tentang Saya</span>
    <h2>Kenalan Yuk</h2>
  </div>
  <div class="about-grid">
    <div class="avatar">
      <svg viewBox="0 0 24 24" fill="none" stroke-width="1.5"><circle cx="12" cy="8" r="4"/><path d="M4 21v-1a8 8 0 0 1 16 0v1"/></svg>
    </div>
    <div class="about-text">
      <h3>Halo, saya Dharma 👋</h3>
      <p>Saya seorang <strong>pemula di dunia pemrograman</strong> yang suka bikin project kreatif. Mulai dari game sederhana, simulasi edukatif, sampai aplikasi kuis.</p>
      <p>Fokus saya sekarang adalah <strong>HTML</strong> untuk web dan <strong>Python</strong> untuk logika & simulasi. Saya terus belajar hal baru tiap hari.</p>
      
      <div class="sosmed">
        <!-- TIKTOK @ddhrrmvn -->
        <a href="https://tiktok.com/@ddhrrmvn" target="_blank">
          <svg viewBox="0 0 24 24"><path d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-5.2 1.74 2.89 2.89 0 0 1 2.31-4.64 2.93 2.93 0 0 1 .88.13V9.4a6.84 6.84 0 0 0-1-.05A6.33 6.33 0 0 0 5 20.1a6.34 6.34 0 0 0 10.86-4.43v-7a8.16 8.16 0 0 0 4.77 1.52v-3.4a4.85 4.85 0 0 1-1-.1z"/></svg>
          @ddhrrmvn
        </a>
        <!-- INSTAGRAM @ddhrmma_28 (SUDAH DIPERBAIKI) -->
        <a href="https://instagram.com/ddhrmma_28" target="_blank">
          <svg viewBox="0 0 24 24"><path d="M12 2.16c3.2 0 3.58.01 4.85.07 3.25.15 4.77 1.69 4.92 4.92.06 1.27.07 1.65.07 4.85s-.01 3.58-.07 4.85c-.15 3.23-1.66 4.77-4.92 4.92-1.27.06-1.64.07-4.85.07s-3.58-.01-4.85-.07c-3.26-.15-4.77-1.7-4.92-4.92-.06-1.27-.07-1.64-.07-4.85s.01-3.58.07-4.85C2.38 3.92 3.9 2.38 7.15 2.23 8.42 2.17 8.8 2.16 12 2.16zM12 0C8.74 0 8.33.01 7.05.07 2.7.27.27 2.69.07 7.05.01 8.33 0 8.74 0 12s.01 3.67.07 4.95c.2 4.36 2.62 6.78 6.98 6.98C8.33 23.99 8.74 24 12 24s3.67-.01 4.95-.07c4.35-.2 6.78-2.62 6.98-6.98.06-1.28.07-1.69.07-4.95s-.01-3.67-.07-4.95c-.2-4.35-2.62-6.78-6.98-6.98C15.67.01 15.26 0 12 0zm0 5.84a6.16 6.16 0 1 0 0 12.32 6.16 6.16 0 0 0 0-12.32zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.41-10.85a1.44 1.44 0 1 0 0 2.88 1.44 1.44 0 0 0 0-2.88z"/></svg>
          @ddhrmma_28
        </a>
      </div>
    </div>
  </div>
</section>

<!-- Skills -->
<section class="section" id="skills">
  <div class="section-title">
    <span>Keahlian</span>
    <h2>Skill Saya</h2>
  </div>
  <div class="skills-grid">
    
    <div class="skill">
      <div class="skill-header">
        <div class="skill-name">
          <div class="skill-icon">
            <svg viewBox="0 0 24 24" fill="#e34f26"><path d="M1.5 0h21l-1.91 21.563L11.977 24l-8.564-2.438L1.5 0zm7.031 9.75l-.232-2.718 10.059.003.23-2.622L5.412 4.41l.698 8.01h9.126l-.326 3.426-2.91.804-2.955-.81-.188-2.11H6.248l.33 4.171L12 19.351l5.379-1.443.744-8.157H8.531z"/></svg>
          </div>
          HTML
        </div>
        <div class="skill-pct">85%</div>
      </div>
      <div class="progress-bg"><div class="progress-bar" style="width:85%"></div></div>
    </div>

    <div class="skill">
      <div class="skill-header">
        <div class="skill-name">
          <div class="skill-icon">
            <svg viewBox="0 0 24 24" fill="#3776ab"><path d="M14.25.18l.9.2.73.26.59.3.45.32.34.34.25.34.16.33.1.3.04.26.02.2-.01.13V8.5l-.05.63-.13.55-.21.46-.26.38-.3.31-.33.25-.35.19-.35.14-.33.1-.3.07-.26.04-.21.02H8.77l-.69.05-.59.14-.5.22-.41.27-.33.32-.27.35-.2.36-.15.37-.1.35-.07.32-.04.27-.02.21v3.06H3.17l-.21-.03-.28-.07-.32-.12-.35-.18-.36-.26-.36-.36-.35-.46-.32-.59-.28-.73-.21-.88-.14-1.05-.05-1.23.06-1.22.16-1.04.24-.87.32-.71.36-.57.4-.44.42-.33.42-.24.4-.16.36-.1.32-.05.24-.01h.16l.06.01h8.16v-.83H6.18l-.01-2.75-.02-.37.05-.34.11-.31.17-.28.25-.26.31-.23.38-.2.44-.18.51-.15.58-.12.64-.1.71-.06.77-.04.84-.02 1.27.05zm-6.3 1.98l-.23.33-.08.41.08.41.23.34.33.22.41.09.41-.09.33-.22.23-.34.08-.41-.08-.41-.23-.33-.33-.22-.41-.09-.41.09zm13.09 3.95l.28.06.32.12.35.18.36.27.36.35.35.47.32.59.28.73.21.88.14 1.04.05 1.23-.06 1.23-.16 1.04-.24.86-.32.71-.36.57-.4.45-.42.33-.42.24-.4.16-.36.09-.32.05-.24.02-.16-.01h-8.22v.82h5.84l.01 2.76.02.36-.05.34-.11.31-.17.29-.25.25-.31.24-.38.2-.44.17-.51.15-.58.13-.64.09-.71.07-.77.04-.84.01-1.27-.04-1.07-.14-.9-.2-.73-.25-.59-.3-.45-.33-.34-.34-.25-.34-.16-.33-.1-.3-.04-.25-.02-.2.01-.13v-5.34l.05-.64.13-.54.21-.46.26-.38.3-.32.33-.24.35-.2.35-.14.33-.1.3-.06.26-.04.21-.02.13-.01h5.84l.69-.05.59-.14.5-.21.41-.28.33-.32.27-.35.2-.36.15-.36.1-.35.07-.32.04-.28.02-.21V6.07h2.09l.14.01zm-6.47 14.25l-.23.33-.08.41.08.41.23.33.33.23.41.08.41-.08.33-.23.23-.33.08-.41-.08-.41-.23-.33-.33-.23-.41-.08-.41.08z"/></svg>
          </div>
          Python
        </div>
        <div class="skill-pct">80%</div>
      </div>
      <div class="progress-bg"><div class="progress-bar" style="width:80%"></div></div>
    </div>

    <div class="skill">
      <div class="skill-header">
        <div class="skill-name">
          <div class="skill-icon">
            <svg viewBox="0 0 24 24" fill="#264de4"><path d="M1.5 0h21l-1.91 21.563L11.977 24l-8.564-2.438L1.5 0zm17.09 4.413L5.41 4.41l.213 2.622 10.125.002-.255 2.716h-6.64l.24 2.573h6.182l-.366 3.523-2.91.804-2.956-.81-.188-2.11h-2.61l.29 3.855L12 19.288l5.373-1.53L18.59 4.414z"/></svg>
          </div>
          CSS
        </div>
        <div class="skill-pct">70%</div>
      </div>
      <div class="progress-bg"><div class="progress-bar" style="width:70%"></div></div>
    </div>

    <div class="skill">
      <div class="skill-header">
        <div class="skill-name">
          <div class="skill-icon">
            <svg viewBox="0 0 24 24" fill="#f7df1e"><path d="M0 0h24v24H0V0zm22.034 18.276c-.175-1.095-.888-2.015-3.003-2.873-.736-.345-1.554-.585-1.797-1.14-.091-.33-.105-.51-.046-.705.15-.646.915-.84 1.515-.66.39.12.75.42.976.9 1.034-.676 1.034-.676 1.755-1.125-.27-.42-.404-.601-.586-.78-.63-.705-1.469-1.065-2.834-1.034l-.705.089c-.676.165-1.32.525-1.71 1.005-1.14 1.291-.811 3.541.569 4.471 1.365 1.02 3.361 1.244 3.616 2.205.24 1.17-.87 1.545-1.966 1.41-.811-.18-1.26-.586-1.755-1.336l-1.83 1.051c.21.48.45.689.81 1.109 1.74 1.756 6.09 1.666 6.871-1.004.029-.09.24-.705.074-1.65l.046.067zm-8.983-7.245h-2.248c0 1.938-.009 3.864-.009 5.805 0 1.232.063 2.363-.138 2.711-.33.689-1.18.601-1.566.48-.396-.196-.597-.466-.83-.855-.063-.105-.11-.196-.127-.196l-1.825 1.125c.305.63.75 1.172 1.324 1.517.855.51 2.004.675 3.207.405.783-.226 1.458-.691 1.811-1.411.51-.93.402-2.07.397-3.346.012-2.054 0-4.109 0-6.179l.004-.056z"/></svg>
          </div>
          JavaScript
        </div>
        <div class="skill-pct">60%</div>
      </div>
      <div class="progress-bg"><div class="progress-bar" style="width:60%"></div></div>
    </div>

  </div>
</section>

<!-- Projects -->
<section class="section" id="projects">
  <div class="section-title">
    <h2>Project Saya</h2>
  </div>
  <div class="projects-grid">
    
    <div class="project-card">
      <h3>Penyimpanan Html</h3>
      <p>Project penyimpanan berbasis HTML untuk menyimpan data atau catatan langsung di browser.</p>
      <a href="https://dochost.co/d/knpx46mo?v=c" target="_blank" class="project-btn">Buka Project &rarr;</a>
    </div>

    <div class="project-card">
      <h3>Game Dart</h3>
      <p>Game sederhana yang dibangun menggunakan bahasa pemrograman Dart.</p>
      <a href="https://dochost.co/d/3mxnmtnt?v=c" target="_blank" class="project-btn">Buka Project &rarr;</a>
    </div>

    <div class="project-card">
      <h3>Kuis IPA</h3>
      <p>Aplikasi kuis interaktif mata pelajaran IPA dengan sistem skor otomatis.</p>
      <a href="https://dochost.io/edit/m3cssmme?token=k3ZVGRdcN66HyFASx2mz2O8eyEfll8fM" target="_blank" class="project-btn">Buka Project &rarr;</a>
    </div>

    <div class="project-card">
      <h3>Game Tembak Musuh</h3>
      <p>Game tembak-menembak sederhana dengan kontrol keyboard dan musuh bergerak.</p>
      <a href="https://dochost.co/d/pa26lat4?v=c" target="_blank" class="project-btn">Buka Project &rarr;</a>
    </div>

    <div class="project-card">
      <h3>Surat Cinta</h3>
      <p>Website interaktif bertema romantis untuk mengirim pesan atau surat cinta digital.</p>
      <a href="https://dochost.co/d/rkajgsir?v=c" target="_blank" class="project-btn">Buka Project &rarr;</a>
    </div>

  </div>
</section>

<!-- Contact -->
<section class="section" id="contact">
  <div class="section-title">
    <span>Kontak</span>
    <h2>Hubungi Saya</h2>
  </div>
  <div class="contact-grid">
    <div class="contact-info">
      <h3>Mari Terhubung</h3>
      <p>Punya pertanyaan, saran, atau ingin kolaborasi? Kirim pesan atau hubungi lewat sosial media saya.</p>
      
      <div class="c-item">
        <div class="c-icon"><svg viewBox="0 0 24 24"><path d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-5.2 1.74 2.89 2.89 0 0 1 2.31-4.64 2.93 2.93 0 0 1 .88.13V9.4a6.84 6.84 0 0 0-1-.05A6.33 6.33 0 0 0 5 20.1a6.34 6.34 0 0 0 10.86-4.43v-7a8.16 8.16 0 0 0 4.77 1.52v-3.4a4.85 4.85 0 0 1-1-.1z"/></svg></div>
        <span>TikTok: @ddhrrmvn</span>
      </div>
      <div class="c-item">
        <div class="c-icon"><svg viewBox="0 0 24 24"><path d="M12 2.16c3.2 0 3.58.01 4.85.07 3.25.15 4.77 1.69 4.92 4.92.06 1.27.07 1.65.07 4.85s-.01 3.58-.07 4.85c-.15 3.23-1.66 4.77-4.92 4.92-1.27.06-1.64.07-4.85.07s-3.58-.01-4.85-.07c-3.26-.15-4.77-1.7-4.92-4.92-.06-1.27-.07-1.64-.07-4.85s.01-3.58.07-4.85C2.38 3.92 3.9 2.38 7.15 2.23 8.42 2.17 8.8 2.16 12 2.16zM12 0C8.74 0 8.33.01 7.05.07 2.7.27.27 2.69.07 7.05.01 8.33 0 8.74 0 12s.01 3.67.07 4.95c.2 4.36 2.62 6.78 6.98 6.98C8.33 23.99 8.74 24 12 24s3.67-.01 4.95-.07c4.35-.2 6.78-2.62 6.98-6.98.06-1.28.07-1.69.07-4.95s-.01-3.67-.07-4.95c-.2-4.35-2.62-6.78-6.98-6.98C15.67.01 15.26 0 12 0zm0 5.84a6.16 6.16 0 1 0 0 12.32 6.16 6.16 0 0 0 0-12.32zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.41-10.85a1.44 1.44 0 1 0 0 2.88 1.44 1.44 0 0 0 0-2.88z"/></svg></div>
        <span>Instagram: @ddhrmma_28</span>
      </div>
    </div>

    <form class="contact-form" onsubmit="alert('Pesan berhasil dikirim!'); return false;">
      <div class="input-group">
        <input type="text" placeholder="Nama Lengkap" required>
      </div>
      <div class="input-group">
        <input type="email" placeholder="Email" required>
      </div>
      <div class="input-group">
        <textarea rows="4" placeholder="Pesan" required></textarea>
      </div>
      <button type="submit" class="btn btn-primary" style="width:100%; justify-content:center;">Kirim Pesan</button>
    </form>
  </div>
</section>

<!-- Footer -->
<footer>
  <p>&copy; 2024 <span>Dharma</span>. Dibuat dengan semangat merah menyala.</p>
</footer>

</body>
</html>
