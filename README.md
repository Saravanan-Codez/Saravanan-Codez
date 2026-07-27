<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Canvas GitHub Profile Showcase - Saravanan S</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600;700&family=Inter:wght@300;400;600;700&display=swap');
    
    body {
      font-family: 'Inter', sans-serif;
      background-color: #0f172a;
      color: #f8fafc;
    }
    .font-mono {
      font-family: 'Fira Code', monospace;
    }
    /* Custom Scrollbar */
    ::-webkit-scrollbar {
      width: 6px;
      height: 6px;
    }
    ::-webkit-scrollbar-track {
      background: #1e293b;
    }
    ::-webkit-scrollbar-thumb {
      background: #3b82f6;
      border-radius: 3px;
    }
  </style>
</head>
<body class="h-screen flex flex-col overflow-hidden">

  <!-- Header -->
  <header class="bg-slate-900 border-b border-slate-800 px-6 py-3 flex justify-between items-center z-10">
    <div class="flex items-center space-x-3">
      <div class="w-9 h-9 rounded-lg bg-gradient-to-tr from-blue-600 to-cyan-400 flex items-center justify-center shadow-lg shadow-blue-500/20">
        <i class="fa-solid fa-palette text-white text-lg"></i>
      </div>
      <div>
        <h1 class="font-bold text-lg text-white leading-none">Canvas Profile Studio</h1>
        <p class="text-xs text-slate-400 font-mono mt-1"> Saravanan S (@Saravanan-Codez)</p>
      </div>
    </div>

    <!-- Quick Action Controls -->
    <div class="flex items-center space-x-3">
      <button id="exportPngBtn" class="px-4 py-2 bg-blue-600 hover:bg-blue-500 text-white rounded-lg text-xs font-semibold flex items-center transition-all shadow-md shadow-blue-600/30">
        <i class="fa-solid fa-download mr-2"></i> Export Canvas PNG
      </button>
      <button id="copyMdBtn" class="px-4 py-2 bg-slate-800 hover:bg-slate-700 text-slate-200 border border-slate-700 rounded-lg text-xs font-semibold flex items-center transition-all">
        <i class="fa-solid fa-code mr-2"></i> Copy Markdown
      </button>
    </div>
  </header>

  <!-- Main Grid Layout -->
  <main class="flex-1 flex overflow-hidden">
    
    <!-- Left Controls Panel -->
    <aside class="w-80 bg-slate-900/90 border-r border-slate-800 p-5 overflow-y-auto flex flex-col space-y-6">
      
      <!-- Theme Selection -->
      <div>
        <label class="text-xs font-semibold uppercase tracking-wider text-slate-400 block mb-2">
          <i class="fa-solid fa-paint-brush mr-1"></i> Canvas Theme
        </label>
        <div class="grid grid-cols-2 gap-2" id="themeSelector">
          <button data-theme="tokyonight" class="theme-btn px-3 py-2 rounded-lg border text-left text-xs font-medium transition-all bg-slate-800 border-blue-500 text-white">
            <span class="w-3 h-3 rounded-full bg-[#7aa2f7] inline-block mr-1"></span> Tokyo Night
          </button>
          <button data-theme="radical" class="theme-btn px-3 py-2 rounded-lg border text-left text-xs font-medium transition-all bg-slate-800 border-slate-700 text-slate-400 hover:text-white">
            <span class="w-3 h-3 rounded-full bg-[#fe428e] inline-block mr-1"></span> Radical
          </button>
          <button data-theme="cyberpunk" class="theme-btn px-3 py-2 rounded-lg border text-left text-xs font-medium transition-all bg-slate-800 border-slate-700 text-slate-400 hover:text-white">
            <span class="w-3 h-3 rounded-full bg-[#00ff9f] inline-block mr-1"></span> Cyberpunk
          </button>
          <button data-theme="nord" class="theme-btn px-3 py-2 rounded-lg border text-left text-xs font-medium transition-all bg-slate-800 border-slate-700 text-slate-400 hover:text-white">
            <span class="w-3 h-3 rounded-full bg-[#88c0d0] inline-block mr-1"></span> Nord
          </button>
        </div>
      </div>

      <!-- Animation / Particles Toggle -->
      <div class="p-3 bg-slate-800/50 rounded-lg border border-slate-800 flex items-center justify-between">
        <span class="text-xs font-medium text-slate-300">
          <i class="fa-solid fa-[#000] fa-wand-magic-sparkles text-amber-400 mr-1.5"></i> Canvas Particles
        </span>
        <label class="relative inline-flex items-center cursor-pointer">
          <input type="checkbox" id="particleToggle" class="sr-only peer" checked>
          <div class="w-9 h-5 bg-slate-700 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-slate-300 after:border after:rounded-full after:h-4 after:w-4 after:transition-all peer-checked:bg-blue-600"></div>
        </label>
      </div>

      <!-- Profile Information Form -->
      <div class="space-y-4">
        <label class="text-xs font-semibold uppercase tracking-wider text-slate-400 block">
          <i class="fa-solid fa-user-pen mr-1"></i> Card Details
        </label>

        <div>
          <label class="text-xs text-slate-400 block mb-1">Display Name</label>
          <input type="text" id="inputName" value="Saravanan S" class="w-full bg-slate-800 border border-slate-700 rounded-lg px-3 py-1.5 text-xs text-white focus:outline-none focus:border-blue-500">
        </div>

        <div>
          <label class="text-xs text-slate-400 block mb-1">Title / Headline</label>
          <input type="text" id="inputTitle" value="Systems & Compiler Developer" class="w-full bg-slate-800 border border-slate-700 rounded-lg px-3 py-1.5 text-xs text-white focus:outline-none focus:border-blue-500">
        </div>

        <div>
          <label class="text-xs text-slate-400 block mb-1">Featured Project</label>
          <input type="text" id="inputProject" value="Falkon Language Compiler" class="w-full bg-slate-800 border border-slate-700 rounded-lg px-3 py-1.5 text-xs text-white focus:outline-none focus:border-blue-500">
        </div>

        <div>
          <label class="text-xs text-slate-400 block mb-1">Current Focus</label>
          <input type="text" id="inputFocus" value="Java & Systems Architecture" class="w-full bg-slate-800 border border-slate-700 rounded-lg px-3 py-1.5 text-xs text-white focus:outline-none focus:border-blue-500">
        </div>

        <div>
          <label class="text-xs text-slate-400 block mb-1">Contact Email</label>
          <input type="text" id="inputEmail" value="assfsaravanan@gmail.com" class="w-full bg-slate-800 border border-slate-700 rounded-lg px-3 py-1.5 text-xs text-white focus:outline-none focus:border-blue-500">
        </div>
      </div>

      <!-- Skills Matrix Editor -->
      <div class="space-y-2">
        <label class="text-xs font-semibold uppercase tracking-wider text-slate-400 block">
          <i class="fa-solid fa-code-branch mr-1"></i> Highlighted Tech
        </label>
        <div class="flex flex-wrap gap-1.5" id="skillBadges">
          <span class="px-2 py-1 bg-slate-800 text-blue-400 border border-slate-700 rounded text-[11px] font-mono">C/C++</span>
          <span class="px-2 py-1 bg-slate-800 text-blue-400 border border-slate-700 rounded text-[11px] font-mono">Java</span>
          <span class="px-2 py-1 bg-slate-800 text-blue-400 border border-slate-700 rounded text-[11px] font-mono">Python</span>
          <span class="px-2 py-1 bg-slate-800 text-blue-400 border border-slate-700 rounded text-[11px] font-mono">Rust</span>
          <span class="px-2 py-1 bg-slate-800 text-blue-400 border border-slate-700 rounded text-[11px] font-mono">Go</span>
          <span class="px-2 py-1 bg-slate-800 text-blue-400 border border-slate-700 rounded text-[11px] font-mono">TypeScript</span>
          <span class="px-2 py-1 bg-slate-800 text-blue-400 border border-slate-700 rounded text-[11px] font-mono">Docker</span>
          <span class="px-2 py-1 bg-slate-800 text-blue-400 border border-slate-700 rounded text-[11px] font-mono">Flutter</span>
        </div>
      </div>

    </aside>

    <!-- Canvas Preview Stage -->
    <section class="flex-1 bg-slate-950 flex flex-col items-center justify-center p-6 relative overflow-auto">
      
      <!-- Live Indicator -->
      <div class="absolute top-4 left-6 flex items-center space-x-2 bg-slate-900/80 px-3 py-1.5 rounded-full border border-slate-800 backdrop-blur-sm">
        <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span>
        <span class="text-xs font-mono text-slate-300">HTML5 Canvas Renderer (2K Resolution)</span>
      </div>

      <!-- Main Canvas Canvas Wrapper -->
      <div class="shadow-2xl shadow-blue-950/50 rounded-2xl overflow-hidden border border-slate-800 max-w-full">
        <canvas id="profileCanvas" class="block cursor-pointer"></canvas>
      </div>

      <p class="text-xs text-slate-500 mt-4 font-mono">
        <i class="fa-solid fa-circle-info mr-1"></i> Interactive preview rendered in real-time. Click "Export Canvas PNG" to download directly.
      </p>
    </section>

  </main>

  <!-- Markdown Modal -->
  <div id="mdModal" class="fixed inset-0 bg-black/70 backdrop-blur-sm hidden items-center justify-center z-50 p-4">
    <div class="bg-slate-900 border border-slate-800 rounded-xl w-full max-w-2xl p-6 relative shadow-2xl">
      <button id="closeModalBtn" class="absolute top-4 right-4 text-slate-400 hover:text-white">
        <i class="fa-solid fa-xmark text-lg"></i>
      </button>
      <h3 class="text-base font-bold text-white mb-2 flex items-center">
        <i class="fa-brands fa-markdown text-blue-400 mr-2 text-xl"></i> GitHub Profile Markdown Code
      </h3>
      <p class="text-xs text-slate-400 mb-4">Copy and paste this markdown directly into your GitHub profile <code class="bg-slate-800 px-1 py-0.5 rounded text-blue-300">README.md</code> file.</p>
      
      <textarea id="mdOutput" readonly class="w-full h-64 bg-slate-950 border border-slate-800 rounded-lg p-3 text-xs font-mono text-slate-300 focus:outline-none focus:border-blue-500 resize-none"></textarea>
      
      <div class="mt-4 flex justify-end space-x-3">
        <button id="copyModalCodeBtn" class="px-4 py-2 bg-blue-600 hover:bg-blue-500 text-white rounded-lg text-xs font-semibold flex items-center">
          <i class="fa-solid fa-copy mr-2"></i> Copy Code
        </button>
      </div>
    </div>
  </div>

  <!-- Interactive Canvas Logic Script -->
  <script>
    const canvas = document.getElementById('profileCanvas');
    const ctx = canvas.getContext('2d');

    // Canvas Logic Scaling & Dimensions
    const CANVAS_WIDTH = 900;
    const CANVAS_HEIGHT = 580;
    
    // Set actual canvas resolution for crisp rendering
    const dpr = window.devicePixelRatio || 1;
    canvas.width = CANVAS_WIDTH * dpr;
    canvas.height = CANVAS_HEIGHT * dpr;
    canvas.style.width = `${CANVAS_WIDTH}px`;
    canvas.style.height = `${CANVAS_HEIGHT}px`;
    ctx.scale(dpr, dpr);

    // Color Themes
    const themes = {
      tokyonight: {
        bg: '#1a1b26',
        cardBg: '#24283b',
        border: '#414868',
        accent: '#7aa2f7',
        accentSub: '#bb9af7',
        textPrimary: '#c0caf5',
        textSecondary: '#9aa5ce',
        cardHighlight: '#1f2335',
        bars: ['#7aa2f7', '#bb9af7', '#7dcfff', '#73daca', '#e0af68']
      },
      radical: {
        bg: '#141321',
        cardBg: '#1e1c31',
        border: '#363252',
        accent: '#fe428e',
        accentSub: '#f8d847',
        textPrimary: '#a9b1d6',
        textSecondary: '#8d90a8',
        cardHighlight: '#25233d',
        bars: ['#fe428e', '#f8d847', '#00e5ff', '#a967ff', '#ff6b6b']
      },
      cyberpunk: {
        bg: '#0f051d',
        cardBg: '#1b0c33',
        border: '#3d1c6d',
        accent: '#00ff9f',
        accentSub: '#fdf000',
        textPrimary: '#00e5ff',
        textSecondary: '#ab87ff',
        cardHighlight: '#261245',
        bars: ['#00ff9f', '#fdf000', '#ff0055', '#00e5ff', '#9d00ff']
      },
      nord: {
        bg: '#2e3440',
        cardBg: '#3b4252',
        border: '#4c566a',
        accent: '#88c0d0',
        accentSub: '#81a1c1',
        textPrimary: '#eceff4',
        textSecondary: '#d8dee9',
        cardHighlight: '#434c5e',
        bars: ['#88c0d0', '#81a1c1', '#a3be8c', '#ebcb8b', '#b48ead']
      }
    };

    let currentThemeKey = 'tokyonight';
    let particlesEnabled = true;

    // Form State
    const profileState = {
      name: 'Saravanan S',
      title: 'Systems & Compiler Developer',
      project: 'Falkon Language Compiler',
      focus: 'Java & Systems Architecture',
      email: 'assfsaravanan@gmail.com',
      skills: ['C/C++', 'Java', 'Python', 'Rust', 'Go', 'TypeScript', 'Docker', 'Flutter']
    };

    // Particle System
    const particles = Array.from({ length: 35 }, () => ({
      x: Math.random() * CANVAS_WIDTH,
      y: Math.random() * CANVAS_HEIGHT,
      radius: Math.random() * 2 + 1,
      vx: (Math.random() - 0.5) * 0.4,
      vy: (Math.random() - 0.5) * 0.4,
      alpha: Math.random() * 0.5 + 0.2
    }));

    // Rounded Rectangle Helper
    function drawRoundRect(x, y, w, h, r, fillStyle, strokeStyle, strokeWidth = 1) {
      ctx.beginPath();
      ctx.moveTo(x + r, y);
      ctx.arcTo(x + w, y, x + w, y + h, r);
      ctx.arcTo(x + w, y + h, x, y + h, r);
      ctx.arcTo(x, y + h, x, y, r);
      ctx.arcTo(x, y, x + w, y, r);
      ctx.closePath();

      if (fillStyle) {
        ctx.fillStyle = fillStyle;
        ctx.fill();
      }
      if (strokeStyle) {
        ctx.strokeStyle = strokeStyle;
        ctx.lineWidth = strokeWidth;
        ctx.stroke();
      }
    }

    // Canvas Render Loop
    function render() {
      const theme = themes[currentThemeKey];

      // 1. Canvas Background
      ctx.fillStyle = theme.bg;
      ctx.fillRect(0, 0, CANVAS_WIDTH, CANVAS_HEIGHT);

      // Gradient Accent Overlay Background
      const bgGrad = ctx.createLinearGradient(0, 0, CANVAS_WIDTH, CANVAS_HEIGHT);
      bgGrad.addColorStop(0, `${theme.accent}12`);
      bgGrad.addColorStop(1, 'transparent');
      ctx.fillStyle = bgGrad;
      ctx.fillRect(0, 0, CANVAS_WIDTH, CANVAS_HEIGHT);

      // 2. Render Particles
      if (particlesEnabled) {
        particles.forEach(p => {
          p.x += p.vx;
          p.y += p.vy;

          if (p.x < 0) p.x = CANVAS_WIDTH;
          if (p.x > CANVAS_WIDTH) p.x = 0;
          if (p.y < 0) p.y = CANVAS_HEIGHT;
          if (p.y > CANVAS_HEIGHT) p.y = 0;

          ctx.beginPath();
          ctx.arc(p.x, p.y, p.radius, 0, Math.PI * 2);
          ctx.fillStyle = theme.accent;
          ctx.globalAlpha = p.alpha;
          ctx.fill();
          ctx.globalAlpha = 1.0;
        });
      }

      // 3. Main Glassmorphism Profile Frame
      drawRoundRect(30, 30, CANVAS_WIDTH - 60, CANVAS_HEIGHT - 60, 20, theme.cardBg, theme.border, 1.5);

      // Header Banner Accent Line
      const headerGrad = ctx.createLinearGradient(50, 0, CANVAS_WIDTH - 50, 0);
      headerGrad.addColorStop(0, theme.accent);
      headerGrad.addColorStop(1, theme.accentSub);
      drawRoundRect(30, 30, CANVAS_WIDTH - 60, 6, 3, headerGrad, null);

      // 4. Profile Header Section
      // Avatar Frame
      drawRoundRect(55, 55, 75, 75, 16, theme.cardHighlight, theme.accent, 2);
      
      // Avatar Terminal Icon Symbol
      ctx.font = 'bold 32px "Fira Code"';
      ctx.fillStyle = theme.accent;
      ctx.textAlign = 'center';
      ctx.fillText('>_', 92, 103);

      // User Details Text
      ctx.textAlign = 'left';
      ctx.font = 'bold 24px "Inter"';
      ctx.fillStyle = theme.textPrimary;
      ctx.fillText(profileState.name, 150, 82);

      ctx.font = '500 13px "Inter"';
      ctx.fillStyle = theme.textSecondary;
      ctx.fillText(`@Saravanan-Codez • ${profileState.title}`, 150, 105);

      // Status Pill
      drawRoundRect(150, 115, 190, 22, 11, `${theme.accent}20`, theme.accent, 1);
      ctx.font = '600 10px "Fira Code"';
      ctx.fillStyle = theme.accent;
      ctx.fillText(`⚡ BUILDING: ${profileState.project.split(' ')[0]}`, 160, 130);

      // 5. Featured Highlight Spotlight Card (Falkon Language)
      drawRoundRect(55, 155, 380, 120, 14, theme.cardHighlight, theme.border, 1);
      
      ctx.font = 'bold 12px "Inter"';
      ctx.fillStyle = theme.accentSub;
      ctx.fillText('🚀 FEATURED PROJECT', 75, 180);

      ctx.font = 'bold 16px "Inter"';
      ctx.fillStyle = theme.textPrimary;
      ctx.fillText(profileState.project, 75, 208);

      ctx.font = '400 12px "Inter"';
      ctx.fillStyle = theme.textSecondary;
      ctx.fillText(`Currently mastering ${profileState.focus}.`, 75, 230);
      ctx.fillText(`Portfolio: saravanan-codes.pages.dev`, 75, 250);

      // 6. GitHub Live Stats Metrics Cards (Right Side)
      const renderStatBox = (x, y, w, h, label, val, sub) => {
        drawRoundRect(x, y, w, h, 12, theme.cardHighlight, theme.border, 1);
        ctx.font = 'bold 11px "Inter"';
        ctx.fillStyle = theme.textSecondary;
        ctx.fillText(label, x + 15, y + 25);

        ctx.font = 'bold 22px "Fira Code"';
        ctx.fillStyle = theme.accent;
        ctx.fillText(val, x + 15, y + 55);

        ctx.font = '400 10px "Inter"';
        ctx.fillStyle = theme.textSecondary;
        ctx.fillText(sub, x + 15, y + 73);
      };

      renderStatBox(455, 155, 185, 85, 'TOTAL REPOS', '28+', 'Public repositories');
      renderStatBox(655, 155, 185, 85, 'CONTRIBUTIONS', '1,240+', 'Commits this year');

      // 7. Language Breakdown Visual Bar Chart
      drawRoundRect(455, 255, 385, 115, 14, theme.cardHighlight, theme.border, 1);
      ctx.font = 'bold 12px "Inter"';
      ctx.fillStyle = theme.textPrimary;
      ctx.fillText('📊 TOP LANGUAGES BREAKDOWN', 475, 280);

      const langs = [
        { name: 'C/C++', pct: 40 },
        { name: 'Java', pct: 25 },
        { name: 'Python', pct: 18 },
        { name: 'TypeScript', pct: 10 },
        { name: 'Others', pct: 7 }
      ];

      // Multi-colored bar graph
      let barX = 475;
      const barY = 295;
      const totalBarW = 345;
      const barH = 14;

      langs.forEach((l, idx) => {
        const segW = (l.pct / 100) * totalBarW;
        ctx.fillStyle = theme.bars[idx % theme.bars.length];
        ctx.beginPath();
        ctx.rect(barX, barY, segW, barH);
        ctx.fill();
        barX += segW;
      });

      // Legend
      let legendX = 475;
      let legendY = 332;
      langs.forEach((l, idx) => {
        ctx.fillStyle = theme.bars[idx % theme.bars.length];
        ctx.beginPath();
        ctx.arc(legendX, legendY - 4, 4, 0, Math.PI * 2);
        ctx.fill();

        ctx.font = '500 10px "Inter"';
        ctx.fillStyle = theme.textSecondary;
        ctx.fillText(`${l.name} (${l.pct}%)`, legendX + 8, legendY);
        legendX += 68;
      });

      // 8. Skills Pills Grid (Bottom Left)
      drawRoundRect(55, 290, 380, 200, 14, theme.cardHighlight, theme.border, 1);
      ctx.font = 'bold 12px "Inter"';
      ctx.fillStyle = theme.textPrimary;
      ctx.fillText('🛠 HIGHLIGHTED TECH STACK', 75, 315);

      let pillX = 75;
      let pillY = 335;
      profileState.skills.forEach(skill => {
        ctx.font = '600 11px "Fira Code"';
        const pillWidth = ctx.measureText(skill).width + 24;

        if (pillX + pillWidth > 415) {
          pillX = 75;
          pillY += 32;
        }

        drawRoundRect(pillX, pillY, pillWidth, 24, 6, `${theme.accent}15`, theme.border, 1);
        ctx.fillStyle = theme.accent;
        ctx.fillText(skill, pillX + 12, pillY + 16);

        pillX += pillWidth + 8;
      });

      // 9. Contact Banner Footer (Bottom Right)
      drawRoundRect(455, 385, 385, 105, 14, theme.cardHighlight, theme.border, 1);
      ctx.font = 'bold 12px "Inter"';
      ctx.fillStyle = theme.textPrimary;
      ctx.fillText('📫 DIRECT CONTACT & LINKS', 475, 410);

      ctx.font = '400 12px "Fira Code"';
      ctx.fillStyle = theme.accent;
      ctx.fillText(`✉ Email: ${profileState.email}`, 475, 435);
      ctx.fillText(`🌐 Web  : saravanan-codes.pages.dev`, 475, 458);
      ctx.fillText(`🐙 GitHub: github.com/Saravanan-Codez`, 475, 480);

      // Loop frame for smooth particle animation
      requestAnimationFrame(render);
    }

    // Start Animation Loop
    render();

    // Listeners for UI Inputs
    document.getElementById('inputName').addEventListener('input', e => profileState.name = e.target.value);
    document.getElementById('inputTitle').addEventListener('input', e => profileState.title = e.target.value);
    document.getElementById('inputProject').addEventListener('input', e => profileState.project = e.target.value);
    document.getElementById('inputFocus').addEventListener('input', e => profileState.focus = e.target.value);
    document.getElementById('inputEmail').addEventListener('input', e => profileState.email = e.target.value);

    document.getElementById('particleToggle').addEventListener('change', e => particlesEnabled = e.target.checked);

    // Theme selector handler
    document.querySelectorAll('.theme-btn').forEach(btn => {
      btn.addEventListener('click', () => {
        document.querySelectorAll('.theme-btn').forEach(b => {
          b.classList.remove('border-blue-500', 'text-white');
          b.classList.add('border-slate-700', 'text-slate-400');
        });
        btn.classList.add('border-blue-500', 'text-white');
        btn.classList.remove('border-slate-700', 'text-slate-400');
        currentThemeKey = btn.getAttribute('data-theme');
      });
    });

    // Export Canvas PNG
    document.getElementById('exportPngBtn').addEventListener('click', () => {
      const link = document.createElement('a');
      link.download = `github-profile-canvas-${profileState.name.toLowerCase().replace(/\s+/g, '-')}.png`;
      link.href = canvas.toDataURL('image/png');
      link.click();
    });

    // Markdown Modal Handlers
    const modal = document.getElementById('mdModal');
    const mdOutput = document.getElementById('mdOutput');

    function generateMarkdown() {
      return `<div align="center">

  # Hi, I'm ${profileState.name} 👋

  ![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=7AA2F7&center=true&vCenter=true&width=600&lines=${encodeURIComponent('Building ' + profileState.project)};${encodeURIComponent('Focusing on ' + profileState.focus)})

  [![Profile Views](https://komarev.com/ghpvc/?username=Saravanan-Codez&label=Profile%20Views&color=7aa2f7&style=flat-square)](https://github.com/Saravanan-Codez)
  [![Followers](https://img.shields.io/github/followers/Saravanan-Codez?label=Followers&logo=github&color=3d59a1&style=flat-square)](https://github.com/Saravanan-Codez)

</div>

---

## 👨‍💻 About Me

- 🔭 **Current Focus:** ${profileState.project}
- 🌱 **Learning & Dev:** ${profileState.focus}
- 👨‍💻 **Portfolio:** [saravanan-codes.pages.dev](https://saravanan-codes.pages.dev/)
- 📫 **Contact:** ${profileState.email}

---

## 🛠 Tech Stack

![Skills](https://go-skill-icons.vercel.app/api/icons?perline=9&i=c,cpp,java,py,go,rust,ts,docker,flutter)

---

## 📊 GitHub Stats

<p align="center">
  <img src="https://github-stats-extended.vercel.app/api?username=Saravanan-Codez&show_icons=true&locale=en&theme=${currentThemeKey}" />
  <img src="https://github-stats-extended.vercel.app/api/top-langs/?username=Saravanan-Codez&layout=compact&theme=${currentThemeKey}" />
</p>`;
    }

    document.getElementById('copyMdBtn').addEventListener('click', () => {
      mdOutput.value = generateMarkdown();
      modal.classList.remove('hidden');
      modal.classList.add('flex');
    });

    document.getElementById('closeModalBtn').addEventListener('click', () => {
      modal.classList.add('hidden');
      modal.classList.remove('flex');
    });

    document.getElementById('copyModalCodeBtn').addEventListener('click', () => {
      mdOutput.select();
      navigator.clipboard.writeText(mdOutput.value);
      alert('Markdown copied to clipboard!');
    });
  </script>
</body>
</html>
