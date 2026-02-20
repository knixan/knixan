<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GitHub README Preview</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=DM+Sans:wght@300;400;500;600&display=swap');

  :root {
    --bg: #0d0d1a;
    --surface: #13131f;
    --surface2: #1a1a2e;
    --pink: #ff4da6;
    --pink-dim: #c4387a;
    --cyan: #00e5ff;
    --text: #e8e8f0;
    --muted: #7070a0;
    --border: rgba(255,77,166,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    min-height: 100vh;
    padding: 40px 20px;
  }

  .readme {
    max-width: 780px;
    margin: 0 auto;
  }

  /* HEADER */
  .header {
    text-align: center;
    padding: 48px 32px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    margin-bottom: 24px;
    position: relative;
    overflow: hidden;
  }

  .header::before {
    content: '';
    position: absolute;
    top: -80px; left: 50%;
    transform: translateX(-50%);
    width: 400px; height: 200px;
    background: radial-gradient(ellipse, rgba(255,77,166,0.18) 0%, transparent 70%);
    pointer-events: none;
  }

  .typing-bar {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--cyan);
    background: rgba(0,229,255,0.06);
    border: 1px solid rgba(0,229,255,0.2);
    border-radius: 8px;
    padding: 10px 18px;
    display: inline-block;
    margin-bottom: 24px;
    letter-spacing: 0.02em;
  }

  .typing-bar::after {
    content: '|';
    animation: blink 1s infinite;
    color: var(--cyan);
  }

  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  .header h1 {
    font-size: 28px;
    font-weight: 600;
    letter-spacing: -0.02em;
    margin-bottom: 8px;
  }

  .header h1 span { color: var(--pink); }

  .header .role {
    color: var(--muted);
    font-size: 15px;
    margin-bottom: 20px;
  }

  .streak-img {
    border-radius: 8px;
    max-width: 100%;
    opacity: 0.9;
  }

  /* SECTION */
  .section {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px 32px;
    margin-bottom: 24px;
  }

  .section-title {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    font-weight: 700;
    color: var(--pink);
    text-transform: uppercase;
    letter-spacing: 0.12em;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ABOUT */
  .about p {
    color: #b0b0cc;
    line-height: 1.7;
    font-size: 15px;
    margin-bottom: 12px;
  }

  .about p:last-child { margin-bottom: 0; }

  .highlight { color: var(--pink); font-weight: 500; }

  /* STATS */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .stats-grid img {
    width: 100%;
    border-radius: 8px;
  }

  /* TECH STACK */
  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 6px 12px;
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    color: var(--text);
    transition: border-color 0.2s, background 0.2s;
    cursor: default;
  }

  .badge:hover {
    border-color: var(--pink);
    background: rgba(255,77,166,0.08);
  }

  .badge .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--pink);
    flex-shrink: 0;
  }

  /* BADGE categories */
  .cat-design .dot { background: #a78bfa; }
  .cat-frontend .dot { background: var(--cyan); }
  .cat-backend .dot { background: #34d399; }
  .cat-tools .dot { background: #fbbf24; }

  .cat-label {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    margin-top: 12px;
    margin-bottom: 6px;
    letter-spacing: 0.08em;
  }

  /* SITE LINK */
  .site-link {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: linear-gradient(135deg, var(--pink), #c4387a);
    color: white;
    text-decoration: none;
    padding: 10px 20px;
    border-radius: 10px;
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    font-weight: 700;
    transition: opacity 0.2s, transform 0.2s;
  }

  .site-link:hover { opacity: 0.85; transform: translateY(-1px); }

  .readme-md {
    background: var(--surface2);
    border: 1px solid rgba(255,77,166,0.1);
    border-radius: 12px;
    padding: 20px 24px;
    margin-top: 32px;
  }

  .readme-md h3 {
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    margin-bottom: 14px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  pre {
    font-family: 'Space Mono', monospace;
    font-size: 11.5px;
    line-height: 1.65;
    color: #c0c0e0;
    white-space: pre-wrap;
    word-break: break-all;
  }

  .copy-btn {
    background: rgba(255,77,166,0.15);
    border: 1px solid var(--pink);
    color: var(--pink);
    border-radius: 6px;
    padding: 6px 14px;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    cursor: pointer;
    margin-top: 14px;
    transition: background 0.2s;
  }
  .copy-btn:hover { background: rgba(255,77,166,0.25); }
</style>
</head>
<body>
<div class="readme">

  <!-- HEADER -->
  <div class="header">
    <div class="typing-bar">Fullstack Developer · React / Next.js / TypeScript</div>
    <h1>Hi, I'm <span>Josefine Eriksson</span> 👋</h1>
    <p class="role">Fullstack Developer · Mjölby, Östergötland 🇸🇪</p>
    <img class="streak-img"
      src="https://github-readme-streak-stats.herokuapp.com/?user=josefineeriksson&theme=radical&hide_border=true"
      alt="GitHub Streak" />
  </div>

  <!-- ABOUT -->
  <div class="section about">
    <div class="section-title">About me</div>
    <p>
      Currently completing an <span class="highlight">LIA internship at hitract.se</span>, building a solid hands-on foundation in modern web development. Looking for a <span class="highlight">Fullstack / Frontend role starting Spring 2025</span> where I can keep growing and contribute to meaningful projects.
    </p>
    <p>
      My journey in IT started back in <span class="highlight">2007</span> — designing blogs, crafting banners, writing scripts, and running my own webshop for custom digital products. After a break, I'm back where I belong: in the world of tech.
    </p>
    <p>
      As a fullstack developer I get to combine both sides of my passion — design and engineering. I love seeing an idea evolve from a rough sketch into a fully interactive product. For me, code and design are two sides of the same creative process, always aimed at the best possible user experience.
    </p>
  </div>

  <!-- STATS -->
  <div class="section">
    <div class="section-title">GitHub Stats</div>
    <div class="stats-grid">
      <img src="https://github-readme-stats.vercel.app/api?username=josefineeriksson&show_icons=true&theme=radical&hide_border=true" alt="Stats" />
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=josefineeriksson&layout=compact&theme=radical&hide_border=true" alt="Top Langs" />
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section">
    <div class="section-title">Tech Stack</div>

    <div class="cat-label">// Design</div>
    <div class="tech-grid">
      <span class="badge cat-design"><span class="dot"></span>Photoshop</span>
      <span class="badge cat-design"><span class="dot"></span>Illustrator</span>
      <span class="badge cat-design"><span class="dot"></span>InDesign</span>
      <span class="badge cat-design"><span class="dot"></span>Figma</span>
    </div>

    <div class="cat-label" style="margin-top:14px">// Frontend</div>
    <div class="tech-grid">
      <span class="badge cat-frontend"><span class="dot"></span>HTML & CSS</span>
      <span class="badge cat-frontend"><span class="dot"></span>Tailwind CSS</span>
      <span class="badge cat-frontend"><span class="dot"></span>Bootstrap</span>
      <span class="badge cat-frontend"><span class="dot"></span>JavaScript</span>
      <span class="badge cat-frontend"><span class="dot"></span>TypeScript</span>
      <span class="badge cat-frontend"><span class="dot"></span>React</span>
      <span class="badge cat-frontend"><span class="dot"></span>Next.js</span>
      <span class="badge cat-frontend"><span class="dot"></span>Material UI</span>
      <span class="badge cat-frontend"><span class="dot"></span>Zod</span>
      <span class="badge cat-frontend"><span class="dot"></span>Yup</span>
    </div>

    <div class="cat-label" style="margin-top:14px">// Backend & Data</div>
    <div class="tech-grid">
      <span class="badge cat-backend"><span class="dot"></span>Node.js</span>
      <span class="badge cat-backend"><span class="dot"></span>Prisma</span>
      <span class="badge cat-backend"><span class="dot"></span>Sanity CMS</span>
      <span class="badge cat-backend"><span class="dot"></span>PostgreSQL</span>
      <span class="badge cat-backend"><span class="dot"></span>SQL</span>
      <span class="badge cat-backend"><span class="dot"></span>Azure</span>
    </div>

    <div class="cat-label" style="margin-top:14px">// Tools</div>
    <div class="tech-grid">
      <span class="badge cat-tools"><span class="dot"></span>Git</span>
      <span class="badge cat-tools"><span class="dot"></span>GitHub</span>
      <span class="badge cat-tools"><span class="dot"></span>GitHub Copilot</span>
    </div>
  </div>

  <!-- SITE -->
  <div class="section" style="text-align:center">
    <div class="section-title">Live</div>
    <a class="site-link" href="https://kladereftervader.se" target="_blank">
      🌐 kladereftervader.se
    </a>
  </div>

  <!-- README MD CODE -->
  <div class="readme-md">
    <h3>// README.md source — copy & paste into GitHub</h3>
    <pre id="mdcode"><div align="center">
<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=FF4DA6&center=true&vCenter=true&width=650&lines=Fullstack+Developer+%7C+React+%2F+Next.js+%2F+TypeScript;Looking+for+new+challenges+from+Spring+2025;Mjölby%2C+Östergötland+%F0%9F%87%B8%F0%9F%87%AA" alt="Typing SVG" />

### Hi, I'm **Josefine Eriksson** 👋
**Fullstack / Frontend Developer** · Currently on LIA internship at hitract.se

[![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=josefineeriksson&theme=radical&hide_border=true)](https://github.com/josefineeriksson)
</div>

---

## 🙋‍♀️ About Me

Currently completing an **LIA internship at hitract.se**, building a solid hands-on foundation in modern web development.
Looking for a **Fullstack / Frontend role starting Spring 2025** where I can keep growing and contribute to meaningful projects.

My journey in IT started back in **2007** — designing blogs, crafting banners, writing scripts, and running my own webshop for custom digital products.
After a break, I'm back where I belong: in the world of tech.

As a fullstack developer I get to combine both sides of my passion — design and engineering.
I love seeing an idea evolve from a rough sketch into a fully interactive product.
For me, code and design are the same creative process, always aimed at the best user experience.

---

## 📊 GitHub Stats

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=josefineeriksson&show_icons=true&theme=radical&hide_border=true" width="48%" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=josefineeriksson&layout=compact&theme=radical&hide_border=true" width="42%" />
</div>

---

## 🛠 Tech Stack

**Design**

![Photoshop](https://img.shields.io/badge/Photoshop-31A8FF?style=for-the-badge&logo=adobephotoshop&logoColor=white)
![Illustrator](https://img.shields.io/badge/Illustrator-FF9A00?style=for-the-badge&logo=adobeillustrator&logoColor=white)
![InDesign](https://img.shields.io/badge/InDesign-FF3366?style=for-the-badge&logo=adobeindesign&logoColor=white)
![Figma](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white)

**Frontend**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![MUI](https://img.shields.io/badge/MUI-007FFF?style=for-the-badge&logo=mui&logoColor=white)
![Zod](https://img.shields.io/badge/Zod-3E67B1?style=for-the-badge&logo=zod&logoColor=white)

**Backend & Data**

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white)
![Sanity](https://img.shields.io/badge/Sanity_CMS-F03E2F?style=for-the-badge&logo=sanity&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)

**Tools**

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![GitHub Copilot](https://img.shields.io/badge/GitHub_Copilot-000000?style=for-the-badge&logo=githubcopilot&logoColor=white)

---

## 🌐 Live

[![kladereftervader.se](https://img.shields.io/badge/kladereftervader.se-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://kladereftervader.se)</pre>
    <button class="copy-btn" onclick="copyMd()">Copy README.md</button>
  </div>

</div>

<script>
function copyMd() {
  const text = document.getElementById('mdcode').innerText;
  navigator.clipboard.writeText(text).then(() => {
    const btn = document.querySelector('.copy-btn');
    btn.textContent = 'Copied!';
    setTimeout(() => btn.textContent = 'Copy README.md', 2000);
  });
}
</script>
</body>
</html>
