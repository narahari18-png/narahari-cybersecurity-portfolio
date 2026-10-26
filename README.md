# narahari-cybersecurity-portfolio
My personal cybersecurity portfolio showcasing my skills, education, certifications, achievements, and future projects in cybersecurity and ethical hacking.




code

from pathlib import Path
html = r'''<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Narahari Kundaragi | Cybersecurity Portfolio</title>
<style>
:root {
  --site-primary: #35e0a1;
  --site-secondary: #122a2b;
  --site-background: #071110;
  --site-on-primary: #04120d;
  --site-on-secondary: #e7fff5;
  --site-on-background: #e8f5f0;
  --site-font-body: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  --site-font-heading: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  --site-heading-scale: 1;
  --site-spacing-scale: 1;
  --site-radius-scale: 1;
  --site-decoration-opacity: 1;
  color-scheme: dark;
}
* { box-sizing: border-box; }
html { scroll-behavior: smooth; scroll-padding-top: 82px; }
body { margin: 0; font-family: var(--site-font-body); background: var(--site-background); color: var(--site-on-background); }
#app { min-height: 100vh; width: 100%; border-radius: 0; overflow: hidden; background-color: light-dark(var(--site-background), var(--site-background)); }
a { color: inherit; text-decoration: none; }
button, input, textarea { font: inherit; }
button, a { -webkit-tap-highlight-color: transparent; }
.wrap { width: min(1120px, calc(100% - 40px)); margin-inline: auto; }
.topbar { position: sticky; top: 0; z-index: 10; border-bottom: 1px solid #203532; background: #071110ed; backdrop-filter: blur(18px); }
.nav { display:flex; align-items:center; justify-content:space-between; min-height:72px; gap:18px; }
.brand { display:flex; align-items:center; gap:10px; font-weight:800; letter-spacing:-.03em; }
.brand-mark { width:36px;height:36px;display:grid;place-items:center;background:var(--site-primary);color:var(--site-on-primary);border-radius:10px;font-weight:900;font-size:15px; }
.navlinks { display:flex; align-items:center; gap:24px; color:#a6bbb4; font-size:13px; }
.navlinks a:hover { color:var(--site-primary); }
.nav-cta, .btn { display:inline-flex; align-items:center; justify-content:center; gap:9px; border:1px solid var(--site-primary); background:var(--site-primary); color:var(--site-on-primary); border-radius:10px; padding:12px 17px; font-weight:750; font-size:13px; cursor:pointer; transition:transform .2s, background .2s; }
.nav-cta:hover,.btn:hover { transform:translateY(-2px); }
.btn.secondary { background:transparent; color:var(--site-on-background); border-color:#35504a; }
.menu-btn { display:none; background:transparent;color:var(--site-on-background);border:1px solid #35504a;border-radius:9px;padding:8px 10px;cursor:pointer; }
.hero { position:relative; padding:92px 0 78px; }
.hero:before { content:"";position:absolute;right:-120px;top:10px;width:440px;height:440px;border-radius:50%;background:radial-gradient(circle,#1a77564a,transparent 68%);pointer-events:none;opacity:var(--site-decoration-opacity); }
.hero-grid { display:grid;grid-template-columns:1.25fr .75fr;align-items:center;gap:55px;position:relative; }
.eyebrow { display:inline-flex;align-items:center;gap:9px;color:var(--site-primary);font:600 12px ui-monospace, SFMono-Regular, Menlo, monospace;letter-spacing:.12em;text-transform:uppercase; }
.pulse { width:7px;height:7px;border-radius:50%;background:var(--site-primary);box-shadow:0 0 14px var(--site-primary); }
h1,h2,h3,p { margin-top:0; }
h1 { font-family:var(--site-font-heading);font-size:clamp(42px,6vw,72px);line-height:1.02;letter-spacing:-.065em;margin:22px 0 20px; }
h1 span { color:var(--site-primary); }
.lead { max-width:600px;color:#a6bbb4;font-size:17px;line-height:1.8; }
.hero-actions { display:flex;flex-wrap:wrap;gap:12px;margin-top:28px; }
.micro { display:flex;flex-wrap:wrap;gap:17px;margin-top:32px;color:#829b92;font-size:12px; }
.micro span:before { content:"✓";color:var(--site-primary);margin-right:7px; }
.terminal { border:1px solid #24453b;background:linear-gradient(145deg,#10231f,#091513);border-radius:18px;box-shadow:0 24px 70px #0005;overflow:hidden;transform:rotate(1deg); }
.term-head { display:flex;align-items:center;gap:7px;padding:14px 17px;border-bottom:1px solid #244038;color:#88a59a;font:12px ui-monospace,monospace; }
.dot { width:8px;height:8px;border-radius:50%;background:#48665a; }
.term-title { margin-left:auto; }
.term-body { padding:24px 22px 26px;font:13px/2 ui-monospace,SFMono-Regular,monospace;color:#9dbab0; }
.term-body .green { color:var(--site-primary); }
.term-body .muted { color:#54746a; }
.term-line { display:block;overflow-wrap:anywhere; }
.term-gap { height:13px; }
.stats { display:grid;grid-template-columns:repeat(3,1fr);gap:14px;padding-bottom:34px; }
.stat { border:1px solid #203a34;background:#0c1916;border-radius:13px;padding:19px 20px; }
.stat strong { display:block;font-size:24px;letter-spacing:-.04em;color:var(--site-primary); }
.stat span { display:block;color:#829b92;font-size:12px;margin-top:5px; }
section { padding:76px 0; }
.section-top { display:flex;justify-content:space-between;align-items:end;gap:20px;margin-bottom:30px; }
.kicker { color:var(--site-primary);font:600 11px ui-monospace,monospace;letter-spacing:.14em;text-transform:uppercase;margin-bottom:10px; }
h2 { font-size:clamp(28px,4vw,42px);letter-spacing:-.05em;margin-bottom:0; }
.section-desc { color:#8da69d;max-width:390px;font-size:14px;line-height:1.7;margin-bottom:2px; }
.panel { background:#0c1916;border:1px solid #203a34;border-radius:16px;padding:26px; }
.about-grid { display:grid;grid-template-columns:1fr 1fr;gap:18px; }
.about-copy { color:#a6bbb4;line-height:1.9;font-size:15px; }
.focus-list { display:grid;gap:12px; }
.focus-item { display:flex;gap:13px;align-items:flex-start;padding:14px;border:1px solid #203a34;border-radius:12px;background:#0a1512; }
.icon { width:36px;height:36px;flex:0 0 36px;display:grid;place-items:center;border-radius:10px;background:#15372b;color:var(--site-primary);font-size:17px; }
.focus-item strong { display:block;font-size:14px;margin-bottom:4px; }
.focus-item small { color:#8da69d;line-height:1.5;font-size:12px; }
.skills-grid { display:grid;grid-template-columns:repeat(3,1fr);gap:15px; }
.skill-card h3 { font-size:15px;margin:0 0 16px; }
.tags { display:flex;flex-wrap:wrap;gap:8px; }
.tag { display:inline-flex;border:1px solid #2a453d;background:#10211c;color:#b7d1c7;border-radius:7px;padding:7px 10px;font-size:12px; }
.timeline { display:grid;gap:14px; }
.timeline-card { display:grid;grid-template-columns:48px 1fr auto;gap:17px;align-items:start; }
.timeline-icon { width:46px;height:46px;border-radius:12px;background:#15372b;color:var(--site-primary);display:grid;place-items:center;font-size:19px; }
.timeline-card h3 { margin:1px 0 6px;font-size:16px; }
.timeline-card p { margin:0;color:#8da69d;font-size:13px;line-height:1.65; }
.pill { color:var(--site-primary);background:#123326;border:1px solid #245440;border-radius:100px;padding:6px 10px;font-size:10px;white-space:nowrap; }
.cert-grid,.project-grid { display:grid;grid-template-columns:repeat(2,1fr);gap:15px; }
.cert-card { display:flex;gap:15px;align-items:flex-start; }
.cert-logo { flex:0 0 48px;height:48px;border-radius:13px;display:grid;place-items:center;background:#15372b;color:var(--site-primary);font-weight:900;font-size:13px; }
.cert-card h3,.project-card h3 { font-size:15px;margin:2px 0 7px; }
.cert-card p,.project-card p { color:#8da69d;font-size:13px;line-height:1.65;margin:0; }
.project-card { position:relative;overflow:hidden; }
.project-card:before { content:"";position:absolute;top:0;left:0;width:100%;height:3px;background:linear-gradient(90deg,var(--site-primary),transparent);opacity:var(--site-decoration-opacity); }
.project-meta { display:flex;align-items:center;justify-content:space-between;gap:10px;margin-bottom:16px; }
.project-number { color:#507064;font:12px ui-monospace,monospace; }
.project-card h3 { font-size:17px; }
.project-card .tags { margin-top:16px; }
.placeholder { color:#d0e4dc !important; }
.achievement-grid { display:grid;grid-template-columns:repeat(2,1fr);gap:15px; }
.achievement { display:flex;gap:14px;align-items:center; }
.achievement .icon { font-size:20px; }
.achievement strong { font-size:14px;display:block;margin-bottom:4px; }
.achievement small { font-size:12px;color:#8da69d; }
.contact-box { display:grid;grid-template-columns:1fr .9fr;gap:28px;align-items:start;background:linear-gradient(130deg,#10231d,#0b1714);border:1px solid #2b493d;border-radius:20px;padding:34px; }
.contact-box p { color:#9cb4aa;line-height:1.8;font-size:14px;margin:14px 0 0; }
.contact-form { display:grid;gap:12px; }
.field { width:100%;border:1px solid #2b473e;background:#071310;color:#e8f5f0;border-radius:9px;padding:12px 13px;outline:none;font-size:13px; }
.field:focus { border-color:var(--site-primary);box-shadow:0 0 0 3px #35e0a11c; }
textarea.field { min-height:100px;resize:vertical; }
.contact-note { color:#718b81;font-size:11px;line-height:1.5; }
footer { border-top:1px solid #203a34;padding:23px 0;color:#789188;font-size:12px; }
.footer-inner { display:flex;justify-content:space-between;gap:15px;flex-wrap:wrap; }
.toast { position:fixed;bottom:20px;left:50%;transform:translateX(-50%);background:#173a2c;color:#eafff5;border:1px solid #347754;padding:12px 16px;border-radius:10px;font-size:13px;box-shadow:0 10px 30px #0006;display:none;z-index:30;max-width:calc(100% - 30px); }
@media (max-width:800px) {
  .navlinks { display:none;position:absolute;left:0;right:0;top:71px;background:#091512;border-bottom:1px solid #203a34;padding:18px 22px;flex-direction:column;align-items:flex-start;gap:18px; }
  .navlinks.open { display:flex; }
  .menu-btn { display:block; }
  .nav-cta { display:none; }
  .hero { padding:65px 0 45px; }
  .hero-grid { grid-template-columns:1fr;gap:34px; }
  .terminal { max-width:560px;transform:none; }
  .stats { padding-top:6px; }
  .skills-grid { grid-template-columns:repeat(2,1fr); }
  .section-top { align-items:flex-start;flex-direction:column; }
  .contact-box { grid-template-columns:1fr; }
}
@media (max-width:520px) {
  .wrap { width:min(100% - 28px,1120px); }
  .brand { font-size:13px; }
  .hero { padding-top:50px; }
  h1 { font-size:43px; }
  .lead { font-size:15px; }
  .stats { grid-template-columns:1fr;gap:9px; }
  .stat { padding:14px 16px; }
  .stat strong { font-size:21px; }
  section { padding:54px 0; }
  .about-grid,.skills-grid,.cert-grid,.project-grid,.achievement-grid { grid-template-columns:1fr; }
  .panel { padding:20px; }
  .timeline-card { grid-template-columns:42px 1fr;gap:12px; }
  .timeline-icon { width:40px;height:40px; }
  .timeline-card .pill { grid-column:2;justify-self:start; }
  .contact-box { padding:22px; }
  .hero-actions .btn { flex:1; }
}
@media (prefers-reduced-motion: reduce) { html { scroll-behavior:auto; } *,*:before,*:after { transition:none !important; } }
</style>
</head>
<body>
<div id="app" data-sites-preview-theme="custom">
<header class="topbar">
  <div class="wrap nav">
    <a class="brand" href="#home" aria-label="Narahari home"><span class="brand-mark">NK</span><span>Narahari <span style="color:var(--site-primary)">K.</span></span></a>
    <nav class="navlinks" id="navlinks" aria-label="Main navigation">
      <a href="#about">About</a><a href="#skills">Skills</a><a href="#education">Education</a><a href="#certifications">Certifications</a><a href="#projects">Projects</a><a href="#contact">Contact</a>
    </nav>
    <a class="nav-cta" href="#contact">Let's connect <span aria-hidden="true">↗</span></a>
    <button class="menu-btn" id="menuBtn" aria-expanded="false" aria-controls="navlinks">☰ Menu</button>
  </div>
</header>
<main>
<section class="hero" id="home">
  <div class="wrap hero-grid">
    <div>
      <div class="eyebrow"><span class="pulse"></span> Cybersecurity · Student portfolio</div>
      <h1>Curious mind.<br><span>Secure future.</span></h1>
      <p class="lead">I'm <strong style="color:#e8f5f0">Narahari Kundaragi</strong>, a Diploma Computer Science student building my foundation in cybersecurity, web technologies, and secure digital systems.</p>
      <div class="hero-actions">
        <a class="btn" href="#projects">Explore my journey <span aria-hidden="true">↓</span></a>
        <a class="btn secondary" href="#contact">Contact me <span aria-hidden="true">↗</span></a>
      </div>
      <div class="micro"><span>Open to cybersecurity internships</span><span>Learning by doing</span></div>
    </div>
    <div class="terminal" aria-label="Decorative terminal panel">
      <div class="term-head"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="term-title">student@portfolio:~</span></div>
      <div class="term-body">
        <span class="term-line muted"># a little about my mission</span>
        <span class="term-line"><span class="green">$ whoami</span></span>
        <span class="term-line">Narahari Kundaragi</span>
        <span class="term-gap"></span>
        <span class="term-line"><span class="green">$ focus --areas</span></span>
        <span class="term-line">web-security</span>
        <span class="term-line">networking-basics</span>
        <span class="term-line">secure-development</span>
        <span class="term-gap"></span>
        <span class="term-line"><span class="green">$ status</span></span>
        <span class="term-line">Learning &amp; building <span class="green">●</span></span>
        <span class="term-line muted">Stay curious. Stay ethical.</span>
      </div>
    </div>
  </div>
</section>
<div class="wrap stats" aria-label="Portfolio highlights">
  <div class="stat"><strong>Diploma CSE</strong><span>Computer Science &amp; Engineering</span></div>
  <div class="stat"><strong>2</strong><span>Relevant learning certificates</span></div>
  <div class="stat"><strong>Creative</strong><span>Poster design &amp; video editing</span></div>
</div>
<section id="about">
  <div class="wrap">
    <div class="section-top"><div><div class="kicker">01 / About me</div><h2>Tech with a purpose.</h2></div><p class="section-desc">A student mindset, a security-first outlook, and a willingness to keep learning.</p></div>
    <div class="about-grid">
      <div class="panel">
        <p class="about-copy">I'm a Diploma CSE student interested in understanding how digital systems work—and how to make them safer. I'm currently strengthening my cybersecurity fundamentals while building practical technical and communication skills. I'm looking for an internship where I can learn from experienced professionals, contribute responsibly, and grow through real-world exposure.</p>
        <p class="about-copy" style="margin-bottom:0">My creative experience in poster design and video editing has also taught me to communicate ideas visually and pay attention to detail.</p>
      </div>
      <div class="focus-list">
        <div class="focus-item"><div class="icon">⌘</div><div><strong>Security mindset</strong><small>Learning core security concepts, risks, and responsible practices.</small></div></div>
        <div class="focus-item"><div class="icon">⌁</div><div><strong>Web foundations</strong><small>HTML and the fundamentals behind how websites are structured.</small></div></div>
        <div class="focus-item"><div class="icon">✳</div><div><strong>Creative problem-solving</strong><small>Visual storytelling, design thinking, and clear communication.</small></div></div>
      </div>
    </div>
  </div>
</section>
<section id="skills" style="background:#091512">
  <div class="wrap">
    <div class="section-top"><div><div class="kicker">02 / Skills</div><h2>What I'm building.</h2></div><p class="section-desc">A transparent snapshot of my current learning areas—not a claim of professional mastery.</p></div>
    <div class="skills-grid">
      <div class="panel skill-card"><h3>Cybersecurity foundations</h3><div class="tags"><span class="tag">Security fundamentals</span><span class="tag">Threat awareness</span><span class="tag">Risk basics</span><span class="tag">Ethical practice</span></div></div>
      <div class="panel skill-card"><h3>Web &amp; development</h3><div class="tags"><span class="tag">HTML</span><span class="tag">Web fundamentals</span><span class="tag">Programming concepts</span></div></div>
      <div class="panel skill-card"><h3>Professional strengths</h3><div class="tags"><span class="tag">Visual design</span><span class="tag">Video editing</span><span class="tag">Creative thinking</span><span class="tag">Communication</span></div></div>
    </div>
  </div>
</section>
<section id="education">
  <div class="wrap">
    <div class="section-top"><div><div class="kicker">03 / Education</div><h2>Learning in progress.</h2></div><p class="section-desc">Building a solid base in computer science with a growing focus on security.</p></div>
    <div class="timeline">
      <div class="panel timeline-card">
        <div class="timeline-icon">⌘</div>
        <div><h3>Diploma in Computer Science &amp; Engineering</h3><p>Government Polytechnic, Bagalkot · Karnataka<br>5th semester · Current focus: Cybersecurity</p></div>
        <span class="pill">In progress</span>
      </div>
      <div class="panel timeline-card">
        <div class="timeline-icon">▤</div>
        <div><h3>Class 10 / SSLC</h3><p>Kendriya Vidyalaya No. 1, Rajnagar, Hubli · Passed 2023</p></div>
        <span class="pill">Completed</span>
      </div>
    </div>
  </div>
</section>
<section id="certifications" style="background:#091512">
  <div class="wrap">
    <div class="section-top"><div><div class="kicker">04 / Certifications</div><h2>Learning, one step at a time.</h2></div><p class="section-desc">Certificates that support my early journey into web development and cybersecurity.</p></div>
    <div class="cert-grid">
      <div class="panel cert-card"><div class="cert-logo">GL</div><div><h3>Front End Developer in HTML</h3><p>Great Learning · HTML and web structure fundamentals</p><div style="margin-top:12px"><span class="pill">Certificate earned</span></div></div></div>
      <div class="panel cert-card"><div class="cert-logo">IS</div><div><h3>Introduction to Cyber Security</h3><p>Infosys Springboard · Introductory cybersecurity learning</p><div style="margin-top:12px"><span class="pill">Certificate earned</span></div></div></div>
    </div>
  </div>
</section>
<section id="projects">
  <div class="wrap">
    <div class="section-top"><div><div class="kicker">05 / Projects</div><h2>Next up: hands-on work.</h2></div><p class="section-desc">These are clearly marked project ideas, ready to replace as I complete and document real work.</p></div>
    <div class="project-grid">
      <article class="panel project-card"><div class="project-meta"><span class="project-number">PROJECT IDEA / 001</span><span class="pill">Planned</span></div><h3>Personal Security Checklist</h3><p class="placeholder">A beginner-friendly checklist for stronger passwords, multi-factor authentication, updates, and safer browsing. To be built and tested.</p><div class="tags"><span class="tag">Security awareness</span><span class="tag">Documentation</span></div></article>
      <article class="panel project-card"><div class="project-meta"><span class="project-number">PROJECT IDEA / 002</span><span class="pill">Planned</span></div><h3>Secure Login UI Demo</h3><p class="placeholder">A small educational web demo exploring form validation and safe authentication concepts—without collecting real credentials.</p><div class="tags"><span class="tag">HTML</span><span class="tag">Web basics</span><span class="tag">Secure design</span></div></article>
      <article class="panel project-card"><div class="project-meta"><span class="project-number">PROJECT IDEA / 003</span><span class="pill">Planned</span></div><h3>Cybersecurity Learning Notes</h3><p class="placeholder">Organized notes explaining core security terms, common risks, and defensive best practices for fellow beginners.</p><div class="tags"><span class="tag">Research</span><span class="tag">Technical writing</span></div></article>
      <article class="panel project-card"><div class="project-meta"><span class="project-number">YOUR NEXT PROJECT</span><span class="pill">Open slot</span></div><h3>Something I'm building next</h3><p class="placeholder">Replace this card with a real project, its goal, the tools used, what you learned, and a link to the source code or demo.</p><div class="tags"><span class="tag">To be updated</span></div></article>
    </div>
  </div>
</section>
<section id="achievements" style="background:#091512">
  <div class="wrap">
    <div class="section-top"><div><div class="kicker">06 / Beyond code</div><h2>Creative achievements.</h2></div><p class="section-desc">Creativity matters in tech too: it helps turn complex ideas into clear, engaging stories.</p></div>
    <div class="achievement-grid">
      <div class="panel achievement"><div class="icon">✦</div><div><strong>1st place · Video shoot &amp; editing</strong><small>Creative production and visual storytelling</small></div></div>
      <div class="panel achievement"><div class="icon">▧</div><div><strong>1st place · Poster design</strong><small>Visual communication and design</small></div></div>
    </div>
  </div>
</section>
<section id="contact">
  <div class="wrap">
    <div class="contact-box">
      <div><div class="kicker">07 / Contact</div><h2>Let's talk security.</h2><p>I'm interested in cybersecurity internship opportunities where I can learn, contribute, and grow. Have an opportunity or advice to share? Send a message draft using the form.</p><p style="font-size:12px;color:#718b81">Location: Bagalkot, Karnataka, India</p></div>
      <form class="contact-form" id="contactForm">
        <input class="field" id="senderName" name="name" placeholder="Your name" required aria-label="Your name">
        <input class="field" id="senderEmail" name="email" type="email" placeholder="Your email" required aria-label="Your email">
        <textarea class="field" id="senderMessage" name="message" placeholder="Your message or internship opportunity..." required aria-label="Your message"></textarea>
        <button class="btn" type="submit">Prepare email draft <span aria-hidden="true">↗</span></button>
        <div class="contact-note">This preview doesn't send messages or store your details. The button opens your email app with a draft; add your real email address below in the source before sharing publicly.</div>
      </form>
    </div>
  </div>
</section>
</main>
<footer><div class="wrap footer-inner"><span>© <span id="year"></span> Narahari Kundaragi · Built with curiosity.</span><span>Learn ethically. Build responsibly. Keep improving.</span></div></footer>
<div class="toast" id="toast" role="status" aria-live="polite"></div>
</div>
<script>
const menuBtn = document.getElementById('menuBtn');
const navlinks = document.getElementById('navlinks');
menuBtn.addEventListener('click', () => {
  const open = navlinks.classList.toggle('open');
  menuBtn.setAttribute('aria-expanded', String(open));
  menuBtn.textContent = open ? '✕ Close' : '☰ Menu';
});
navlinks.querySelectorAll('a').forEach(link => link.addEventListener('click', () => {
  navlinks.classList.remove('open');
  menuBtn.setAttribute('aria-expanded', 'false');
  menuBtn.textContent = '☰ Menu';
}));
document.getElementById('year').textContent = new Date().getFullYear();
document.getElementById('contactForm').addEventListener('submit', (event) => {
  event.preventDefault();
  const name = document.getElementById('senderName').value.trim();
  const email = document.getElementById('senderEmail').value.trim();
  const message = document.getElementById('senderMessage').value.trim();
  const subject = encodeURIComponent('Cybersecurity internship / portfolio enquiry');
  const body = encodeURIComponent(`Hi Narahari,\n\n${message}\n\nRegards,\n${name}\n${email}`);
  const recipient = 'YOUR_EMAIL_HERE';
  if (recipient === 'YOUR_EMAIL_HERE') {
    const toast = document.getElementById('toast');
    toast.textContent = 'Demo form validated. Add your email address in the HTML to enable email drafts.';
    toast.style.display = 'block';
    window.setTimeout(() => { toast.style.display = 'none'; }, 4500);
    return;
  }
  window.location.href = `mailto:${recipient}?subject=${subject}&body=${body}`;
});
</script>
</body>
</html>'''
path = Path("/mnt/data/narahari_cybersecurity_portfolio.html")
path.write_text(html, encoding="utf-8")
print(f"Created {path} ({path.stat().st_size:,} bytes)")
