<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1"/>
<meta name="description" content="Vivek Jariwala — BCA student, Android developer and UI/UX designer."/>
<title>Vivek Jariwala — Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
  :root {
    --lavender-deep:   #3b2d5e;
    --lavender-mid:    #6e5a9e;
    --lavender-soft:   #b8a9d9;
    --lavender-pale:   #ede8f7;
    --beige-warm:      #f5f0e8;
    --beige-mid:       #e0d4be;
    --beige-dark:      #c4a97d;
    --text-dark:       #2a2040;
    --text-mid:        #6b5f82;
    --white:           #fffdf9;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--beige-warm);
    color: var(--text-dark);
    overflow-x: hidden;
  }

  /* ── Noise texture overlay ── */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.035'/%3E%3C/svg%3E");
    pointer-events: none; z-index: 0;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.2rem 5%;
    background: rgba(245,240,232,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--beige-mid);
  }
  .nav-logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.5rem; font-weight: 700;
    color: var(--lavender-deep);
    letter-spacing: 0.03em;
  }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a {
    font-size: 0.85rem; font-weight: 500; letter-spacing: 0.08em;
    text-transform: uppercase; text-decoration: none;
    color: var(--text-mid);
    transition: color 0.3s;
  }
  .nav-links a:hover { color: var(--lavender-deep); }

  /* ── HERO ── */
  #hero {
    min-height: 100vh;
    display: grid; grid-template-columns: 1fr 1fr;
    align-items: center;
    padding: 8rem 5% 4rem;
    position: relative; overflow: hidden;
  }

  .hero-bg-circle {
    position: absolute;
    border-radius: 50%;
    background: radial-gradient(circle, var(--lavender-pale) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero-bg-circle.c1 { width: 600px; height: 600px; top: -100px; right: -100px; opacity: 0.7; }
  .hero-bg-circle.c2 { width: 400px; height: 400px; bottom: 0; left: -100px; opacity: 0.5; }

  .hero-text { position: relative; z-index: 1; }
  .hero-tag {
    display: inline-block;
    font-size: 0.78rem; font-weight: 600; letter-spacing: 0.15em;
    text-transform: uppercase; color: var(--beige-dark);
    background: var(--lavender-deep);
    padding: 0.35rem 0.9rem; border-radius: 2rem;
    margin-bottom: 1.5rem;
    animation: fadeUp 0.8s ease both;
  }
  .hero-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(3rem, 6vw, 5.5rem);
    font-weight: 700; line-height: 1.05;
    color: var(--lavender-deep);
    animation: fadeUp 0.8s 0.15s ease both;
  }
  .hero-name span {
    font-style: italic; font-weight: 300;
    color: var(--lavender-mid);
  }
  .hero-sub {
    font-size: 1.05rem; font-weight: 300; line-height: 1.7;
    color: var(--text-mid); margin: 1.5rem 0 2.5rem;
    max-width: 480px;
    animation: fadeUp 0.8s 0.3s ease both;
  }
  .hero-btns {
    display: flex; gap: 1rem;
    animation: fadeUp 0.8s 0.45s ease both;
  }
  .btn-primary {
    padding: 0.85rem 2rem; border-radius: 3rem;
    background: var(--lavender-deep); color: var(--white);
    font-size: 0.9rem; font-weight: 500; letter-spacing: 0.05em;
    text-decoration: none; border: none; cursor: pointer;
    transition: transform 0.25s, box-shadow 0.25s;
    box-shadow: 0 4px 20px rgba(59,45,94,0.25);
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 28px rgba(59,45,94,0.35); }
  .btn-secondary {
    padding: 0.85rem 2rem; border-radius: 3rem;
    background: transparent; color: var(--lavender-deep);
    font-size: 0.9rem; font-weight: 500; letter-spacing: 0.05em;
    text-decoration: none; border: 2px solid var(--lavender-soft);
    cursor: pointer; transition: background 0.25s, border-color 0.25s;
  }
  .btn-secondary:hover { background: var(--lavender-pale); border-color: var(--lavender-mid); }

  .hero-visual {
    display: flex; justify-content: center; align-items: center;
    position: relative; z-index: 1;
    animation: fadeIn 1s 0.4s ease both;
  }
  .avatar-ring {
    width: 340px; height: 340px; border-radius: 50%;
    background: linear-gradient(135deg, var(--lavender-soft) 0%, var(--beige-mid) 100%);
    display: flex; align-items: center; justify-content: center;
    position: relative;
    box-shadow: 0 20px 60px rgba(59,45,94,0.18);
  }
  .avatar-ring::before {
    content: '';
    position: absolute; inset: -12px; border-radius: 50%;
    border: 2px dashed var(--lavender-soft);
    animation: spin 18s linear infinite;
  }
  .avatar-initials {
    font-family: 'Cormorant Garamond', serif;
    font-size: 5rem; font-weight: 700;
    color: var(--lavender-deep); line-height: 1;
    letter-spacing: -0.02em;
  }
  .floating-chip {
    position: absolute;
    background: var(--white);
    border: 1px solid var(--beige-mid);
    border-radius: 2rem;
    padding: 0.5rem 1rem;
    font-size: 0.78rem; font-weight: 600;
    color: var(--lavender-deep);
    box-shadow: 0 4px 16px rgba(0,0,0,0.08);
    white-space: nowrap;
  }
  .chip1 { top: 30px; right: -20px; animation: float 4s ease-in-out infinite; }
  .chip2 { bottom: 60px; left: -30px; animation: float 4s 1.5s ease-in-out infinite; }
  .chip3 { top: 130px; left: -40px; animation: float 4s 0.8s ease-in-out infinite; }

  /* ── SECTIONS ── */
  section { padding: 6rem 5%; position: relative; }

  .section-label {
    font-size: 0.75rem; font-weight: 600; letter-spacing: 0.18em;
    text-transform: uppercase; color: var(--beige-dark);
    margin-bottom: 0.5rem;
  }
  .section-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(2rem, 4vw, 3.2rem);
    font-weight: 700; color: var(--lavender-deep);
    line-height: 1.15; margin-bottom: 3rem;
  }
  .section-title em { font-style: italic; font-weight: 300; color: var(--lavender-mid); }

  /* ── ABOUT ── */
  #about { background: var(--white); }
  .about-grid {
    display: grid; grid-template-columns: 1fr 1.6fr;
    gap: 5rem; align-items: start;
  }
  .about-stats { display: flex; flex-direction: column; gap: 1.5rem; }
  .stat-card {
    background: var(--beige-warm);
    border: 1px solid var(--beige-mid);
    border-radius: 1rem; padding: 1.5rem;
    transition: transform 0.3s, box-shadow 0.3s;
  }
  .stat-card:hover { transform: translateY(-4px); box-shadow: 0 12px 30px rgba(59,45,94,0.1); }
  .stat-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 2.8rem; font-weight: 700; color: var(--lavender-deep);
    line-height: 1;
  }
  .stat-label { font-size: 0.85rem; color: var(--text-mid); margin-top: 0.3rem; }
  .about-text p {
    font-size: 1.05rem; line-height: 1.85;
    color: var(--text-mid); margin-bottom: 1.2rem;
  }
  .about-text strong { color: var(--lavender-deep); }

  /* ── SKILLS ── */
  #skills { background: var(--lavender-pale); }
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(160px,1fr)); gap: 1.2rem; }
  .skill-pill {
    background: var(--white);
    border: 1px solid var(--lavender-soft);
    border-radius: 1rem; padding: 1.2rem 1rem;
    text-align: center;
    transition: all 0.3s;
    cursor: default;
  }
  .skill-pill:hover {
    background: var(--lavender-deep);
    border-color: var(--lavender-deep);
    transform: translateY(-4px);
    box-shadow: 0 10px 25px rgba(59,45,94,0.2);
  }
  .skill-pill:hover .skill-name, .skill-pill:hover .skill-cat { color: var(--white); }
  .skill-icon { font-size: 1.8rem; margin-bottom: 0.5rem; }
  .skill-name { font-size: 0.9rem; font-weight: 600; color: var(--lavender-deep); }
  .skill-cat { font-size: 0.72rem; color: var(--text-mid); margin-top: 0.2rem; }

  /* ── PROJECTS ── */
  #projects { background: var(--beige-warm); }
  .projects-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; }
  .project-card {
    background: var(--white);
    border-radius: 1.5rem; overflow: hidden;
    border: 1px solid var(--beige-mid);
    transition: transform 0.35s, box-shadow 0.35s;
  }
  .project-card:hover { transform: translateY(-6px); box-shadow: 0 20px 50px rgba(59,45,94,0.13); }
  .project-top {
    height: 180px;
    display: flex; align-items: center; justify-content: center;
    font-size: 4rem; position: relative; overflow: hidden;
  }
  .project-top.emi { background: linear-gradient(135deg, var(--lavender-pale), var(--lavender-soft)); }
  .project-top.figma { background: linear-gradient(135deg, var(--beige-mid), var(--beige-dark)); }
  .project-body { padding: 1.8rem; }
  .project-tags { display: flex; gap: 0.5rem; flex-wrap: wrap; margin-bottom: 1rem; }
  .project-tag {
    font-size: 0.72rem; font-weight: 600; letter-spacing: 0.08em;
    text-transform: uppercase; color: var(--lavender-mid);
    background: var(--lavender-pale);
    padding: 0.25rem 0.65rem; border-radius: 2rem;
  }
  .project-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.6rem; font-weight: 700; color: var(--lavender-deep);
    margin-bottom: 0.75rem;
  }
  .project-desc { font-size: 0.9rem; line-height: 1.7; color: var(--text-mid); }
  .project-bullets { margin-top: 1rem; display: flex; flex-direction: column; gap: 0.4rem; }
  .project-bullets li {
    font-size: 0.88rem; color: var(--text-mid); line-height: 1.5;
    list-style: none; padding-left: 1.2rem; position: relative;
  }
  .project-bullets li::before {
    content: '◆'; font-size: 0.4rem;
    color: var(--lavender-mid); position: absolute; left: 0; top: 6px;
  }

  /* ── EDUCATION ── */
  #education { background: var(--white); }
  .edu-timeline { display: flex; flex-direction: column; gap: 0; position: relative; }
  .edu-timeline::before {
    content: '';
    position: absolute; left: 22px; top: 0; bottom: 0;
    width: 2px; background: linear-gradient(to bottom, var(--lavender-mid), var(--beige-mid));
  }
  .edu-item {
    display: flex; gap: 2rem;
    padding: 0 0 2.5rem 0;
    position: relative;
  }
  .edu-dot {
    width: 46px; height: 46px; border-radius: 50%; flex-shrink: 0;
    background: var(--lavender-deep);
    border: 3px solid var(--beige-warm);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.2rem; z-index: 1;
    box-shadow: 0 4px 12px rgba(59,45,94,0.25);
  }
  .edu-content {
    background: var(--beige-warm);
    border: 1px solid var(--beige-mid);
    border-radius: 1rem; padding: 1.4rem 1.6rem;
    flex: 1;
    transition: transform 0.3s, box-shadow 0.3s;
  }
  .edu-content:hover { transform: translateX(4px); box-shadow: 0 8px 24px rgba(59,45,94,0.08); }
  .edu-degree {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.3rem; font-weight: 700; color: var(--lavender-deep);
  }
  .edu-school { font-size: 0.88rem; color: var(--text-mid); margin-top: 0.3rem; }
  .edu-badge {
    display: inline-block; margin-top: 0.7rem;
    font-size: 0.72rem; font-weight: 600; letter-spacing: 0.08em;
    text-transform: uppercase; color: var(--beige-dark);
    background: var(--lavender-deep);
    padding: 0.25rem 0.75rem; border-radius: 2rem;
  }

  /* ── EXPERIENCE ── */
  #experience { background: var(--lavender-pale); }
  .exp-card {
    background: var(--white);
    border-radius: 1.5rem; padding: 2.5rem;
    border: 1px solid var(--lavender-soft);
    max-width: 720px;
    box-shadow: 0 8px 30px rgba(59,45,94,0.07);
  }
  .exp-header { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 1.5rem; flex-wrap: wrap; gap: 1rem; }
  .exp-role {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.8rem; font-weight: 700; color: var(--lavender-deep);
  }
  .exp-company { font-size: 0.95rem; color: var(--text-mid); margin-top: 0.3rem; }
  .exp-duration {
    background: var(--lavender-deep); color: var(--white);
    padding: 0.4rem 1rem; border-radius: 2rem;
    font-size: 0.8rem; font-weight: 600; white-space: nowrap;
  }
  .exp-list { display: flex; flex-direction: column; gap: 0.7rem; }
  .exp-list li {
    font-size: 0.95rem; line-height: 1.65;
    color: var(--text-mid); list-style: none;
    padding-left: 1.5rem; position: relative;
  }
  .exp-list li::before {
    content: '→';
    position: absolute; left: 0; color: var(--lavender-mid); font-weight: 600;
  }

  /* ── CERTIFICATIONS ── */
  #certifications { background: var(--beige-warm); }
  .cert-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 1.5rem; }
  .cert-card {
    background: var(--white);
    border: 1px solid var(--beige-mid);
    border-radius: 1.2rem; padding: 1.8rem;
    display: flex; align-items: center; gap: 1.2rem;
    transition: all 0.3s;
  }
  .cert-card:hover { border-color: var(--lavender-mid); transform: translateY(-3px); box-shadow: 0 10px 25px rgba(59,45,94,0.1); }
  .cert-icon {
    width: 48px; height: 48px; border-radius: 0.8rem;
    background: var(--lavender-pale);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.5rem; flex-shrink: 0;
  }
  .cert-name { font-size: 0.95rem; font-weight: 600; color: var(--lavender-deep); }
  .cert-issuer { font-size: 0.78rem; color: var(--text-mid); margin-top: 0.2rem; }

  /* ── CONTACT ── */
  #contact {
    background: var(--lavender-deep);
    text-align: center; padding: 6rem 5%;
  }
  #contact .section-label { color: var(--lavender-soft); }
  #contact .section-title { color: var(--white); margin-bottom: 1rem; }
  #contact .section-title em { color: var(--lavender-soft); }
  .contact-sub { font-size: 1rem; color: var(--lavender-soft); margin-bottom: 3rem; max-width: 480px; margin-left: auto; margin-right: auto; }
  .contact-chips { display: flex; justify-content: center; flex-wrap: wrap; gap: 1rem; }
  .contact-chip {
    display: flex; align-items: center; gap: 0.6rem;
    background: rgba(255,255,255,0.1);
    border: 1px solid rgba(255,255,255,0.2);
    border-radius: 3rem; padding: 0.85rem 1.6rem;
    color: var(--white); font-size: 0.9rem;
    text-decoration: none;
    transition: all 0.3s;
    backdrop-filter: blur(8px);
  }
  .contact-chip:hover { background: rgba(255,255,255,0.2); transform: translateY(-2px); }

  /* ── FOOTER ── */
  footer {
    background: var(--lavender-deep); border-top: 1px solid rgba(255,255,255,0.1);
    text-align: center; padding: 1.5rem;
    font-size: 0.8rem; color: var(--lavender-soft);
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(28px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeIn {
    from { opacity: 0; } to { opacity: 1; }
  }
  @keyframes float {
    0%, 100% { transform: translateY(0); }
    50%       { transform: translateY(-10px); }
  }
  @keyframes spin {
    from { transform: rotate(0deg); }
    to   { transform: rotate(360deg); }
  }

  .reveal {
    opacity: 0; transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    #hero { grid-template-columns: 1fr; padding-top: 7rem; }
    .hero-visual { display: none; }
    .about-grid { grid-template-columns: 1fr; gap: 2rem; }
    .projects-grid { grid-template-columns: 1fr; }
  }

  /* ── NEW: links, motion ── */
  a.skill-pill,a.cert-card,a.floating-chip{text-decoration:none;color:inherit;display:block}
  a.cert-card{display:flex}
  .edu-school a,.exp-company a{color:var(--lavender-mid);text-decoration:none;background:linear-gradient(currentColor,currentColor) 0 100%/0 1px no-repeat;transition:background-size .3s,color .3s}
  .edu-school a:hover,.exp-company a:hover{background-size:100% 1px;color:var(--lavender-deep)}
  .nav-cta{border:1.5px solid var(--lavender-soft);padding:.4rem .9rem;border-radius:2rem}
  .nav-cta:hover{background:var(--lavender-deep);color:var(--white)!important}
  .project-links{display:flex;gap:.6rem;flex-wrap:wrap;margin-top:1.3rem}
  .plink{font-size:.8rem;font-weight:600;color:var(--lavender-deep);text-decoration:none;border:1.5px solid var(--lavender-soft);padding:.45rem .95rem;border-radius:2rem;transition:all .25s}
  .plink:hover{background:var(--lavender-deep);color:var(--white);transform:translateY(-2px)}
  [hidden]{display:none!important}
  #progress{position:fixed;top:0;left:0;height:3px;width:0;z-index:200;background:linear-gradient(90deg,var(--lavender-mid),var(--beige-dark))}
  #glow{position:fixed;width:340px;height:340px;border-radius:50%;pointer-events:none;z-index:0;left:0;top:0;opacity:0;transition:opacity .4s;background:radial-gradient(circle,rgba(184,169,217,.35),transparent 65%)}
  .hero-typed{font-size:1.25rem;font-weight:500;color:var(--lavender-mid);margin:1rem 0 -.5rem;min-height:1.8rem;animation:fadeUp .8s .22s ease both}
  #typed{color:var(--lavender-deep);font-weight:600}
  .caret{display:inline-block;width:2px;height:1.2em;background:var(--beige-dark);margin-left:3px;vertical-align:-3px;animation:blink 1s steps(1) infinite}
  .hero-name span{background:linear-gradient(90deg,var(--lavender-mid),var(--beige-dark),var(--lavender-mid));background-size:200% auto;-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;animation:shimmer 5s linear infinite}
  .orb{position:absolute;border-radius:50%;pointer-events:none;background:var(--lavender-soft);opacity:.25;animation:drift 9s ease-in-out infinite}
  .o1{width:18px;height:18px;top:22%;left:46%}.o2{width:12px;height:12px;top:68%;left:40%;background:var(--beige-dark);animation-delay:2s}.o3{width:24px;height:24px;top:15%;right:12%;animation-delay:4s}
  .btn-primary,.btn-secondary{position:relative;overflow:hidden}
  .btn-primary::after{content:'';position:absolute;top:0;left:-80%;width:50%;height:100%;background:linear-gradient(100deg,transparent,rgba(255,255,255,.35),transparent);transform:skewX(-20deg);transition:left .6s}
  .btn-primary:hover::after{left:130%}
  .section-title::after{content:'';display:block;height:3px;width:0;margin-top:.7rem;border-radius:2px;background:linear-gradient(90deg,var(--lavender-mid),var(--beige-dark));transition:width .9s .3s ease}
  .reveal.visible .section-title::after,.reveal.visible.section-title::after{width:70px}
  .skills-grid.visible .skill-pill,.projects-grid.visible .project-card,.cert-grid.visible .cert-card,.edu-timeline.visible .edu-item{animation:pop .6s both;animation-delay:calc(var(--i,0)*90ms)}
  .edu-timeline::before{transform-origin:top;transform:scaleY(0);transition:transform 1.4s ease}
  .edu-timeline.visible::before{transform:scaleY(1)}
  .stat-card,.project-card{transform-style:preserve-3d;will-change:transform}
  .exp-card{transition:transform .35s,box-shadow .35s}.exp-card:hover{transform:translateY(-5px);box-shadow:0 18px 45px rgba(59,45,94,.15)}
  #totop{position:fixed;right:1.4rem;bottom:1.4rem;width:44px;height:44px;border-radius:50%;background:var(--lavender-deep);color:var(--white);display:flex;align-items:center;justify-content:center;text-decoration:none;z-index:90;opacity:0;transform:translateY(20px);pointer-events:none;transition:all .35s;box-shadow:0 6px 20px rgba(59,45,94,.3)}
  #totop.show{opacity:1;transform:none;pointer-events:auto}
  footer a{color:var(--beige-mid)}
  @keyframes blink{50%{opacity:0}}
  @keyframes shimmer{to{background-position:200% center}}
  @keyframes drift{0%,100%{transform:translate(0,0)}50%{transform:translate(14px,-22px)}}
  @keyframes pop{from{opacity:0;transform:translateY(24px) scale(.96)}to{opacity:1;transform:none}}
  @media (max-width:700px){.nav-links{gap:.9rem;overflow-x:auto;max-width:75vw}.nav-links a{font-size:.68rem;white-space:nowrap}.hero-btns{flex-wrap:wrap}.chip1,.chip2,.chip3{display:none}}
  @media (prefers-reduced-motion:reduce){*,*::before,*::after{animation-duration:.01ms!important;animation-iteration-count:1!important;transition-duration:.01ms!important}.reveal{opacity:1;transform:none}}
</style>
</head>
<body>

<!-- NAV -->
<div id="progress"></div><div id="glow"></div>
<nav>
  <a href="#hero" class="nav-logo" style="text-decoration:none">VJ</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#certifications">Certifications</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#" data-resume class="nav-cta">Resume ↓</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg-circle c1"></div>
  <div class="hero-bg-circle c2"></div>
  <span class="orb o1"></span><span class="orb o2"></span><span class="orb o3"></span>

  <div class="hero-text">
    <div class="hero-tag">Available for Opportunities</div>
    <h1 class="hero-name">Vivek<br/><span>Jariwala</span></h1>
    <p class="hero-typed">I'm an <span id="typed"></span><span class="caret"></span></p>
    <p class="hero-sub">BCA Student · Android Developer · UI/UX Designer.
    Building functional apps and beautiful interfaces with a passion for clean code and thoughtful design.</p>
    <div class="hero-btns">
      <a href="#projects" class="btn-primary">View My Work</a>
      <a href="#contact" class="btn-secondary">Get in Touch</a>
      <a href="#" data-resume class="btn-secondary">⬇ Resume</a>
    </div>
  </div>

  <div class="hero-visual">
    <div class="avatar-ring">
      <span class="avatar-initials">VJ</span>
      <a href="#projects" class="floating-chip chip1">📱 Android Dev</a>
      <a href="#skills" class="floating-chip chip2">🎨 Figma Design</a>
      <a href="#skills" class="floating-chip chip3">☕ Java / Kotlin</a>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-grid reveal">
    <div class="about-stats">
      <p class="section-label">Who I Am</p>
      <h2 class="section-title">Crafting <em>digital experiences</em></h2>
      <div class="stat-card">
        <div class="stat-num" data-count="2" data-suffix="+">2+</div>
        <div class="stat-label">Projects Completed</div>
      </div>
      <div class="stat-card">
        <div class="stat-num" data-count="4" data-suffix="mo">4mo</div>
        <div class="stat-label">Work Experience</div>
      </div>
      <div class="stat-card">
        <div class="stat-num" data-count="5" data-suffix="+">5+</div>
        <div class="stat-label">Technologies Known</div>
      </div>
    </div>
    <div class="about-text">
      <p>I'm a <strong>2nd Year BCA student at St. Joseph's University, Bangalore</strong>, with a genuine passion for Android development and UI/UX design. I love turning ideas into real, working applications.</p>
      <p>I started my coding journey with <strong>C and C++</strong>, then moved into <strong>Java and Kotlin</strong> for Android development, and picked up <strong>Figma</strong> to bring my UI concepts to life. I believe great software is both functional and beautiful.</p>
      <p>Beyond tech, I have hands-on experience in <strong>accounting and the GST department</strong> from <strong>4 months at CA N.C. Rupawala</strong>, where I worked independently on assigned work — giving me a unique blend of technical and business awareness.</p>
      <p>I'm a fresher in Android development, hungry to learn, collaborate, and build things that matter.</p>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="reveal">
    <p class="section-label">What I Know</p>
    <h2 class="section-title">Skills &amp; <em>Technologies</em></h2>
  </div>
  <div class="skills-grid reveal">
    <a class="skill-pill" href="https://en.cppreference.com/w/c" target="_blank" rel="noopener">
      <div class="skill-icon">🅲</div>
      <div class="skill-name">C Language</div>
      <div class="skill-cat">Programming</div>
    </a>
    <a class="skill-pill" href="https://isocpp.org/" target="_blank" rel="noopener">
      <div class="skill-icon">⊕</div>
      <div class="skill-name">C++</div>
      <div class="skill-cat">Programming</div>
    </a>
    <a class="skill-pill" href="https://dev.java/" target="_blank" rel="noopener">
      <div class="skill-icon">☕</div>
      <div class="skill-name">Java</div>
      <div class="skill-cat">Android Dev</div>
    </a>
    <a class="skill-pill" href="https://kotlinlang.org/" target="_blank" rel="noopener">
      <div class="skill-icon">🤖</div>
      <div class="skill-name">Kotlin</div>
      <div class="skill-cat">Android Dev</div>
    </a>
    <a class="skill-pill" href="https://developer.android.com/studio" target="_blank" rel="noopener">
      <div class="skill-icon">📱</div>
      <div class="skill-name">Android Studio</div>
      <div class="skill-cat">IDE</div>
    </a>
    <a class="skill-pill" href="https://www.figma.com/" target="_blank" rel="noopener">
      <div class="skill-icon">🎨</div>
      <div class="skill-name">Figma</div>
      <div class="skill-cat">UI/UX Design</div>
    </a>
    <a class="skill-pill" href="https://www.gst.gov.in/" target="_blank" rel="noopener">
      <div class="skill-icon">🧾</div>
      <div class="skill-name">GST &amp; Accounts</div>
      <div class="skill-cat">Professional</div>
    </a>
    <div class="skill-pill">
      <div class="skill-icon">🤝</div>
      <div class="skill-name">Teamwork</div>
      <div class="skill-cat">Soft Skill</div>
    </div>
    <div class="skill-pill">
      <div class="skill-icon">💬</div>
      <div class="skill-name">Communication</div>
      <div class="skill-cat">Soft Skill</div>
    </div>
    <div class="skill-pill">
      <div class="skill-icon">❤️</div>
      <div class="skill-name">Emotional IQ</div>
      <div class="skill-cat">Soft Skill</div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="reveal">
    <p class="section-label">What I've Built</p>
    <h2 class="section-title">Featured <em>Projects</em></h2>
  </div>
  <div class="projects-grid reveal">
    <div class="project-card">
      <div class="project-top emi">🧮</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag">Java</span>
          <span class="project-tag">Android Studio</span>
          <span class="project-tag">Android</span>
        </div>
        <div class="project-title">EMI Calculator App</div>
        <p class="project-desc">A fully functional Android application for computing EMI and other financial calculations, built natively in Android Studio.</p>
        <ul class="project-bullets">
          <li>Accurate EMI computation with multiple calculation modes</li>
          <li>Clean and intuitive native Android UI</li>
          <li>Built entirely in Java with Android Studio</li>
        </ul>
        <div class="project-links"><a class="plink" href="mailto:vivekjariwala1319@gmail.com?subject=EMI%20Calculator%20App">💬 Discuss this project</a><a class="plink" data-link="emi_src" hidden target="_blank" rel="noopener">⌨ Source code</a></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-top figma">🏫</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag">Figma</span>
          <span class="project-tag">UI/UX Design</span>
          <span class="project-tag">Prototype</span>
        </div>
        <div class="project-title">Multimedia Institute App</div>
        <p class="project-desc">A comprehensive mobile app prototype for Red and White Multimedia Institute, designed with a signature red and white brand theme.</p>
        <ul class="project-bullets">
          <li>Course details, fee structure &amp; institute info</li>
          <li>Student profiles, attendance &amp; certificate tracking</li>
          <li>Consistent red &amp; white branding throughout</li>
        </ul>
        <div class="project-links"><a class="plink" href="mailto:vivekjariwala1319@gmail.com?subject=Multimedia%20Institute%20App">💬 Discuss this project</a><a class="plink" data-link="figma_proto" hidden target="_blank" rel="noopener">🎨 View prototype</a></div>
      </div>
    </div>
  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="reveal">
    <p class="section-label">My Academic Journey</p>
    <h2 class="section-title">Education &amp; <em>Training</em></h2>
  </div>
  <div class="edu-timeline reveal">
    <div class="edu-item">
      <div class="edu-dot">🎓</div>
      <div class="edu-content">
        <div class="edu-degree">Bachelor of Computer Applications (BCA)</div>
        <div class="edu-school"><a href="https://sju.edu.in/" target="_blank" rel="noopener">St. Joseph's University, Bangalore ↗</a></div>
        <span class="edu-badge">Currently Pursuing — 2nd Year</span>
      </div>
    </div>
    <div class="edu-item">
      <div class="edu-dot">📱</div>
      <div class="edu-content">
        <div class="edu-degree">Android Development</div>
        <div class="edu-school"><a href="https://www.google.com/search?q=Red+and+White+Multimedia+Education+Surat" target="_blank" rel="noopener">Red and White Multimedia Institute, Surat ↗</a></div>
        <span class="edu-badge">Completed</span>
      </div>
    </div>
    <div class="edu-item">
      <div class="edu-dot">📚</div>
      <div class="edu-content">
        <div class="edu-degree">Higher Secondary — 12th</div>
        <div class="edu-school"><a href="https://www.google.com/maps/search/?api=1&query=Experimental+School+Surat+Gujarat" target="_blank" rel="noopener">Experimental School, Surat, Gujarat ↗</a></div>
        <span class="edu-badge">Completed</span>
      </div>
    </div>
    <div class="edu-item">
      <div class="edu-dot">🏫</div>
      <div class="edu-content">
        <div class="edu-degree">Secondary — 10th</div>
        <div class="edu-school"><a href="https://www.google.com/maps/search/?api=1&query=Experimental+School+Surat+Gujarat" target="_blank" rel="noopener">Experimental School, Surat, Gujarat ↗</a></div>
        <span class="edu-badge">Completed</span>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="reveal">
    <p class="section-label">Professional Background</p>
    <h2 class="section-title">Work <em>Experience</em></h2>
  </div>
  <div class="exp-card reveal">
    <div class="exp-header">
      <div>
        <div class="exp-role">GST Department</div>
        <div class="exp-company">CA N.C. Rupawala · <a href="https://www.gst.gov.in/" target="_blank" rel="noopener">GST Portal ↗</a></div>
      </div>
      <div class="exp-duration">4 Months</div>
    </div>
    <ul class="exp-list">
      <li>Handled professionally assigned work in the GST department with accuracy and attention to detail.</li>
      <li>Demonstrated the ability to work independently and manage assigned tasks responsibly.</li>
      <li>Maintained honesty, enthusiasm, and strong moral character in a professional environment.</li>
    </ul>
  </div>
</section>

<!-- CERTIFICATIONS -->
<section id="certifications">
  <div class="reveal">
    <p class="section-label">Credentials</p>
    <h2 class="section-title">Certifi<em>cations</em></h2>
  </div>
  <div class="cert-grid reveal">
    <a class="cert-card" href="https://en.cppreference.com/w/c" target="_blank" rel="noopener">
      <div class="cert-icon">🅲</div>
      <div>
        <div class="cert-name">C Programming</div>
        <div class="cert-issuer">Certificate Course</div>
      </div>
    </a>
    <a class="cert-card" href="https://isocpp.org/" target="_blank" rel="noopener">
      <div class="cert-icon">⊕</div>
      <div>
        <div class="cert-name">C++ Programming</div>
        <div class="cert-issuer">Certificate Course</div>
      </div>
    </a>
    <a class="cert-card" href="https://dev.java/" target="_blank" rel="noopener">
      <div class="cert-icon">☕</div>
      <div>
        <div class="cert-name">Java Programming</div>
        <div class="cert-issuer">Certificate Course</div>
      </div>
    </a>
  <a class="cert-card" href="https://www.google.com/search?q=Red+and+White+Multimedia+Education+Surat" target="_blank" rel="noopener">
      <div class="cert-icon">📱</div>
      <div>
        <div class="cert-name">Android Development</div>
        <div class="cert-issuer">Red and White Multimedia Institute</div>
      </div>
    </a>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <p class="section-label">Let's Connect</p>
  <h2 class="section-title">Get in <em>Touch</em></h2>
  <p class="contact-sub">I'm open to internships, collaborations, and exciting opportunities. Feel free to reach out!</p>
  <div class="contact-chips">
    <a href="mailto:vivekjariwala1319@gmail.com" class="contact-chip">✉️ vivekjariwala1319@gmail.com</a>
    <a href="tel:+918799400865" class="contact-chip">📞 +91 87994 00865</a>
    <a href="https://wa.me/918799400865" target="_blank" rel="noopener" class="contact-chip">💬 WhatsApp</a>
    <a href="https://www.google.com/maps/search/?api=1&query=Bangalore+India" target="_blank" rel="noopener" class="contact-chip">📍 Bangalore, India</a>
    <a href="#" data-resume class="contact-chip">📄 Download Resume</a>
    <a data-link="linkedin" hidden target="_blank" rel="noopener" class="contact-chip">💼 LinkedIn</a>
    <a data-link="github" hidden target="_blank" rel="noopener" class="contact-chip">🐙 GitHub</a>
    <a data-link="instagram" hidden target="_blank" rel="noopener" class="contact-chip">📸 Instagram</a>
  </div>
</section>

<a id="totop" href="#hero" aria-label="Back to top">↑</a>
<footer>
  © 2026 Vivek Jariwala · Designed with ♥ in Lavender &amp; Beige · <a href="#hero">Back to top ↑</a>
</footer>

<script>
  // Scroll reveal
  const revealEls = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 100);
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });
  revealEls.forEach(el => observer.observe(el));

  // Nav active highlight
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.nav-links a');
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(sec => {
      if (window.scrollY >= sec.offsetTop - 120) current = sec.getAttribute('id');
    });
    navLinks.forEach(a => {
      a.style.color = a.getAttribute('href') === '#' + current ? 'var(--lavender-deep)' : '';
    });
  });
  // ── Edit your links here (leave '' to keep a button hidden) ──
  const LINKS = { linkedin:'', github:'', instagram:'', emi_src:'', figma_proto:'' };
  document.querySelectorAll('[data-link]').forEach(a => { const u = LINKS[a.dataset.link]; if (u) { a.href = u; a.hidden = false; } });

  // Typed roles
  const roles = ['Android Developer','UI/UX Designer','BCA Student','GST & Accounts Associate'];
  const typed = document.getElementById('typed'); let ri = 0, ci = 0, del = false;
  (function type(){
    const w = roles[ri]; typed.textContent = w.slice(0, ci);
    if (!del && ci < w.length) ci++;
    else if (!del) { del = true; return setTimeout(type, 1400); }
    else if (ci > 0) ci--;
    else { del = false; ri = (ri + 1) % roles.length; }
    setTimeout(type, del ? 40 : 85);
  })();

  // Stagger children when a grid reveals
  document.querySelectorAll('.skills-grid,.projects-grid,.cert-grid,.edu-timeline').forEach(g => [...g.children].forEach((c,i) => c.style.setProperty('--i', i)));

  // Count-up stats
  const cObs = new IntersectionObserver(es => es.forEach(e => { if (!e.isIntersecting) return; cObs.unobserve(e.target);
    const n = +e.target.dataset.count, s = e.target.dataset.suffix || '', t0 = performance.now();
    (function tick(t){ const p = Math.min((t - t0) / 1200, 1); e.target.textContent = Math.round(n * (1 - Math.pow(1 - p, 3))) + s; if (p < 1) requestAnimationFrame(tick); })(t0);
  }), { threshold: .6 });
  document.querySelectorAll('[data-count]').forEach(el => cObs.observe(el));

  // Scroll progress + back-to-top
  const bar = document.getElementById('progress'), toTopBtn = document.getElementById('totop');
  addEventListener('scroll', () => { const h = document.documentElement; bar.style.width = (scrollY / (h.scrollHeight - innerHeight) * 100) + '%'; toTopBtn.classList.toggle('show', scrollY > 600); }, { passive: true });

  // Cursor glow + 3D tilt (desktop only)
  if (matchMedia('(hover:hover)').matches && !matchMedia('(prefers-reduced-motion:reduce)').matches) {
    const g = document.getElementById('glow');
    addEventListener('mousemove', e => { g.style.opacity = 1; g.style.transform = `translate(${e.clientX-170}px,${e.clientY-170}px)`; });
    document.querySelectorAll('.project-card,.stat-card').forEach(c => {
      c.addEventListener('mousemove', e => { const r = c.getBoundingClientRect(), x = (e.clientX - r.left) / r.width - .5, y = (e.clientY - r.top) / r.height - .5; c.style.transform = `perspective(800px) rotateY(${x*7}deg) rotateX(${-y*7}deg) translateY(-6px)`; });
      c.addEventListener('mouseleave', () => c.style.transform = '');
    });
  }
  // Resume download (PDF is embedded, so it works from anywhere)
  const RESUME_B64 = "JVBERi0xLjQKJZOMi54gUmVwb3J0TGFiIEdlbmVyYXRlZCBQREYgZG9jdW1lbnQgKG9wZW5zb3VyY2UpCjEgMCBvYmoKPDwKL0YxIDIgMCBSIC9GMiAzIDAgUiAvRjMgNCAwIFIKPj4KZW5kb2JqCjIgMCBvYmoKPDwKL0Jhc2VGb250IC9IZWx2ZXRpY2EgL0VuY29kaW5nIC9XaW5BbnNpRW5jb2RpbmcgL05hbWUgL0YxIC9TdWJ0eXBlIC9UeXBlMSAvVHlwZSAvRm9udAo+PgplbmRvYmoKMyAwIG9iago8PAovQmFzZUZvbnQgL0hlbHZldGljYS1Cb2xkIC9FbmNvZGluZyAvV2luQW5zaUVuY29kaW5nIC9OYW1lIC9GMiAvU3VidHlwZSAvVHlwZTEgL1R5cGUgL0ZvbnQKPj4KZW5kb2JqCjQgMCBvYmoKPDwKL0Jhc2VGb250IC9IZWx2ZXRpY2EtT2JsaXF1ZSAvRW5jb2RpbmcgL1dpbkFuc2lFbmNvZGluZyAvTmFtZSAvRjMgL1N1YnR5cGUgL1R5cGUxIC9UeXBlIC9Gb250Cj4+CmVuZG9iago1IDAgb2JqCjw8Ci9Db250ZW50cyA5IDAgUiAvTWVkaWFCb3ggWyAwIDAgNTk1LjI3NTYgODQxLjg4OTggXSAvUGFyZW50IDggMCBSIC9SZXNvdXJjZXMgPDwKL0ZvbnQgMSAwIFIgL1Byb2NTZXQgWyAvUERGIC9UZXh0IC9JbWFnZUIgL0ltYWdlQyAvSW1hZ2VJIF0KPj4gL1JvdGF0ZSAwIC9UcmFucyA8PAoKPj4gCiAgL1R5cGUgL1BhZ2UKPj4KZW5kb2JqCjYgMCBvYmoKPDwKL1BhZ2VNb2RlIC9Vc2VOb25lIC9QYWdlcyA4IDAgUiAvVHlwZSAvQ2F0YWxvZwo+PgplbmRvYmoKNyAwIG9iago8PAovQXV0aG9yIChWaXZlayBKYXJpd2FsYSkgL0NyZWF0aW9uRGF0ZSAoRDoyMDI2MTAyODE1MjM1OSswMCcwMCcpIC9DcmVhdG9yIChcKHVuc3BlY2lmaWVkXCkpIC9LZXl3b3JkcyAoKSAvTW9kRGF0ZSAoRDoyMDI2MTAyODE1MjM1OSswMCcwMCcpIC9Qcm9kdWNlciAoUmVwb3J0TGFiIFBERiBMaWJyYXJ5IC0gXChvcGVuc291cmNlXCkpIAogIC9TdWJqZWN0IChcKHVuc3BlY2lmaWVkXCkpIC9UaXRsZSAoVml2ZWsgSmFyaXdhbGEgLSBSZXN1bWUpIC9UcmFwcGVkIC9GYWxzZQo+PgplbmRvYmoKOCAwIG9iago8PAovQ291bnQgMSAvS2lkcyBbIDUgMCBSIF0gL1R5cGUgL1BhZ2VzCj4+CmVuZG9iago5IDAgb2JqCjw8Ci9GaWx0ZXIgWyAvQVNDSUk4NURlY29kZSAvRmxhdGVEZWNvZGUgXSAvTGVuZ3RoIDI4NjYKPj4Kc3RyZWFtCkdiITtlZ04pJS4mcS9BNW9bQnNVWD1zZCVJcDVFRDEzMkEiQScncWYuX2QpPyxVKSw4Nlw+JENDLVIuZGkha2lkYFk3KixnLE1oNSZFcTsnai5PZEZALGhkRnMySE0nUmckSFI5N1RpQFhGUmdIJF0+Tkw/JlxiJD1ZdC4qJCxOP0IoZkQvJGYrKC4hSlJVZGI3TlI4NiMkKVIxK2YkQC9GWSJHVUljJEsiP1lHLyVBK1klUTQzRjdfai0tJSpBa1k+UHFFZ1puWk1NO05FXzFkOz5ObTtGN1dnVjI0Z0Q7dUNGKDRXXChuZF9FRzcoJTVCbF8nZVFKLWRYaUI/aTdkbFEyKjAzIlFlWlUySjVlJWRFWEZQVjciSTlqJGlXVjJVREo2biFbYTdUVDNRKmtmNDtbXEVRNTtPUlVYUWQ4VTlTIzgxcSJUZGc6ZSoiTjhEViVgNT9EYj9gckxHYzk8QTEsbFIpcyE5Mz5GO0IrMzBrX3FFSkMmbEEhM2NUXlUtb2csbSRwNEFRP3V1clhUUmRHOktYcVVabG1HTj8jKUdPaz1Laz9Ua2A9Qz1lK1tnKUVcW0gzbyY4WEc9Rj5iP1lBMCg0N1EtKk5ZWDBIMyJDUzJXJWZCKF0iMnJjcTpARDlES3RXWC5QN3M+LEM8ODc8bjZeXjBDZyNoLiQpZF1pLWknJkVdKF43PXFYUkZMQW9eaDhKc0ZiQGBjRjleS2lvSTowSEBuIUZuPVZLYVJcOW9PalAnZHBmJFolWUxzRyc/TlRnclpVSTcpZHJzSkhDXF5mJiJUYmMnQks6NDJXS3E9KFtkLEhzQlNAT1NmTCtydWIpI2FPKlgqREdZIV5HLWAwYThGXE4hV3RIamREUiJUOklUVTZGPXFqNEkrRnBIQzlDI0gkOmlpK1VeaUZTYSsqSTk8cGk4UkNtQGJkKydRLUxxOGs6dElWQWRFVTYsTVolNCNlOWF1Xl5rQEltIjQwaGJKODxHUzloNEpcaid0PF1GW0Y6PittUD46IjE1JnBJKy5LZzYpKE5zTXBjVHVhOT5IJUpvLTpXcElMQzleYlw6KWMuNUdrR04oNUdOWnVGYCxVXWhqNV1aTVxHLnIuKUYvM1wzOkEuVWorMTFBVVVnQT0yXmJiLyNOcls5LmFZJC05aWdQQXNgWDZfJyZrM2lSckcuclpPXVpVcClNJWRIa0Asci5aKE9mMVZGdVtUOUxILHE8JTFkbzd1NiRLTm5WY0tUQUgpNC1PWEltKkhjUT8sKGRNRiYzNUVaZm41YFVCLzJVZlc8R2siO2lAYjxqYzNrPmU8RVleYUpSPmA3cXBuLXFbZkpIT1ZRQlsmO1ZtWEU5OTlMaWdOSFEiSTpXSmFYJzpMLlBDbzsuSj4yby9LN20sJlRSc20qKidfcTFaODohO1QyS2YjRWEuTl08KDZUPFRCPywoWGE7VltZMCMzZ0VMInBaNHFUKE9xdFNRJ1UranUqXG9MK0dPcE5bYDhXYlsxK0JMZGd1UUZ1JFUzVEUmTScnMFh0dDdHYHBjMFlNOSpcX19XOkNOcGlwJF9hTyZjZmEvTFNSWiIrS3RXQ1x1PTA2byJ0KSdKYGZsY3QwbSFvcT1RLjlrZ11KUykuUjJScyI1aiVVazBROWI3TyxZPXNNYFRUdT1eL2UuZC8kXl1ya1YrIU1iWkZAaVRjNTxZa2pVTVBiTC47ZCdBbWZTZVUxOCY6QjE1U11wTU1ZOidNcmxHOy1hOy04STsrbTNVTmA3PTFEY3JQUTo/PVhVXy9hKlgocGVHX3NfM2Q0Sl8wTnBcRScrNkZtL1E7JCowRllXQls6VHM2J1QndFEoIUFYX3FWU0wwQmYudHNhO15ScjlXaSYiRVB1O203cj9iYmw8aXFrbVlwdT8qWCQ/Iz5hbjVlN0lPREsxYGdDJVNhbj9fVV5rSHJNSFNNQEsyI1wxayEjZD0pOV8jREdVblluLXRwN0kwRlRjJSkpOkJTYEVfRFhMXkIqRTguXUg/bDxKWj1JMWIpXFl0Skg9aU8yRywoUiYqQ3BUZFw2RlIzJzNVQHVAV0U2VSZaKmZaVUBpal5IVCFoYkI/OHBtPEwiKlxyYEtuRmEoX2FHdDY1WXQzOWBaTlglVktMdVxxXk40JURqPU45K0deLUcnV2lhamxSQyM9cypFSEcvJi5GPHIwTFdQLGViVjdfYSVUWklZY0JrYzMyLnI6XyVANU4waipZJShzamFlLCZRSU5mLF9JT1IkRTMqJV0rc1RqaWNENnJmM2RjYFJHMzxyay46I1VWUyhcUzFzNkVjU0lRSUpQcSkmQHEkbz1QWTQ5LkpdcV9ySiY5MTQ8Yi91Jmtxazw+OkhwVG5CQWtoPHBkUjVZMS49VmxCYWVUblxYVFUrJkMxWSJfVywmXCFxbDVFMSxbQT9CZGJbOTZZNWVcP2RaQkhJJHVBTVIkK3RhcVkrLDpsTTAhRiZpXjtOJDgraDBgRUVNKVsoJygwZGcsMGlZR0I5PCxSRyFGK2BbOkBAUU8lOyFlR0EqcU9XP2tLK1MnYUpYJWVtal8jWVIyaVI8TzJZYSJBLVdKPUxKVzZAK1tMWj5maFhrUTAzdWZaY1RaYEQlci5rUXIvNU5KVUlrYlVQNXVrU0glNSFEZG5yPGJVXG1RSVwnSzNSclpEXSg0QC88NDYqa25jUkdfRnArX2JqYFdcPmFpMSRHK0goc1lRVGpRYV9iVDJwMz9pPURCNV5WTV9CRWdsIy8zPyYqcmY2Kl8sPilxUztfXkR0OlppOD9hUV5ULltbZCRpQlgzdD5MIydNQm41Kk9UPiJuRW50aStNYE1MVlxTSzwyQm4yUiY3RXFkdFNgSFVtIjNKZVEjYGdeWTZtPl4+TVA4Qjw2bGkkW3ByVFtFNiY2cGNbNDRVYWdGMTVEXzleP1tQYV9OQnVRQzRQUXMzND0+LGoyPWtIQCRgPClDUic3aj0mZ2hbaj80PUQ2R0RcYWA0VV5zdWNpKUNwQXIwZW8ocHFLWyVEKil0WF9zJ15HW2w+KlY9JVFnLlo5ZEBoaFNyOVFMdSwlPyU6NzglLUdublUub0xvWWhZalBnTUw5PDtTKms1J1htXUMxSVk8TWRlQ29HO0RgcCo3IyJjWlRsKFlVLzhGTy8xUG1xSj5UQkooRTAoK2lWQG5hODJiVzddX0JqdVwpLl47b0w9J0JDIlJAMWMnaC83VzE8am1ZVkNGPD9tSF1ObDViTzBockUkXk1LWkI5KmoxSXUwLT8pVm9PSDMkYFVvTyJhSjJqSkhSM2slXTM5aF5MQmpJT2FOMWklXjVtcmM1JXJtWls6MiNBWStdQGU9Y1VxMWQ6JVBQNGlKSixwbTk4WkNHMD9CRThHYSw1aCRWWTo7OmZJZEpgbzpLaD5tXUhZOmtyaVdGUWcmXCc3WjxWckZMVUVsMG8iWFk7P0Y0SzBgUztmRjUsOC5BZygtKXQnQSlnQ3QhPEsnMyxFLkcpaS9YYFdQOTIpR1AsWFUrXEdwMS4hZDs1Lksqbj9PSCp1NkN1NmsxdTZGQ2gsJSxFLzluPFRwKWg1JC1OVSJKWVwhOnNbM1AuSDdUXW5uUGtbWC4jWEZLKWAoOEllNUVRRWMyRkZSOWhGVkRlRjQjQWhdRG1eMko5TVAiPzZFMWFGMGc2O0lDMDwhVT8wSUZWSTovNTsrQjEldW0ibzc+dEFyQWQmalpwdUQ8SW9ta1pUMDptU0FEXWFaViMrJ1s4UFFcKkUtS1xAYVZSWXNwU0BqYSdrYmo8KSNYdERuKSlMfj5lbmRzdHJlYW0KZW5kb2JqCnhyZWYKMCAxMAowMDAwMDAwMDAwIDY1NTM1IGYgCjAwMDAwMDAwNjEgMDAwMDAgbiAKMDAwMDAwMDExMiAwMDAwMCBuIAowMDAwMDAwMjE5IDAwMDAwIG4gCjAwMDAwMDAzMzEgMDAwMDAgbiAKMDAwMDAwMDQ0NiAwMDAwMCBuIAowMDAwMDAwNjQ5IDAwMDAwIG4gCjAwMDAwMDA3MTcgMDAwMDAgbiAKMDAwMDAwMTAwOCAwMDAwMCBuIAowMDAwMDAxMDY3IDAwMDAwIG4gCnRyYWlsZXIKPDwKL0lEIApbPDY0MmVhMmE1YTM2ZDUyMTZjMzI2MWQ2MDNkNThlYjMyPjw2NDJlYTJhNWEzNmQ1MjE2YzMyNjFkNjAzZDU4ZWIzMj5dCiUgUmVwb3J0TGFiIGdlbmVyYXRlZCBQREYgZG9jdW1lbnQgLS0gZGlnZXN0IChvcGVuc291cmNlKQoKL0luZm8gNyAwIFIKL1Jvb3QgNiAwIFIKL1NpemUgMTAKPj4Kc3RhcnR4cmVmCjQwMjQKJSVFT0YK";
  document.querySelectorAll('[data-resume]').forEach(a => a.addEventListener('click', e => {
    e.preventDefault();
    const bin = atob(RESUME_B64), arr = new Uint8Array(bin.length);
    for (let i = 0; i < bin.length; i++) arr[i] = bin.charCodeAt(i);
    const url = URL.createObjectURL(new Blob([arr], { type: 'application/pdf' }));
    const l = document.createElement('a'); l.href = url; l.download = 'Vivek_Jariwala_Resume.pdf';
    document.body.appendChild(l); l.click(); l.remove(); setTimeout(() => URL.revokeObjectURL(url), 2000);
  }));
</script>
</body>
</html>
