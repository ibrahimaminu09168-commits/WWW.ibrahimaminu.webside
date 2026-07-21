<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ibrahim Aminu Mentorship — Learn Investing, Wealth Creation & Financial Freedom</title>
<meta name="description" content="Coach Ibrahim Aminu Musa teaches Stock Market Investing, Real Estate, AI Content Creation, Web Development and Financial Coaching. Build real wealth with practical, mentor-led courses.">

<!-- Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@500;700&display=swap" rel="stylesheet">

<style>
/* ============================================================
   IBRAHIM AMINU MENTORSHIP — DESIGN TOKENS
   Color:  --ink #05060F (near-black)  --navy #0A0E27  --blue #2563EB
           --cyan #06B6D4  --paper #F7F9FC  --white #FFFFFF
   Type:   Display  -> 'Space Grotesk'  (headings, big numbers)
           Body     -> 'Inter'          (paragraphs, UI)
           Data     -> 'JetBrains Mono' (prices, tickers, stats)
   Signature: an animated live "market line" that runs through the
   hero and reappears as a thin thread stitching sections together —
   a visual metaphor for tracking growth over time.
   ============================================================ */

:root{
  --ink:#05060F;
  --navy:#0A0E27;
  --navy-2:#0F1538;
  --blue:#2563EB;
  --blue-light:#3B82F6;
  --cyan:#06B6D4;
  --paper:#F7F9FC;
  --white:#FFFFFF;
  --line:rgba(255,255,255,0.10);
  --line-soft:rgba(10,14,39,0.08);
  --muted:#8891B0;
  --muted-dark:#5B6180;
  --success:#10B981;
  --radius:18px;
  --radius-sm:10px;
  --shadow-lg:0 30px 80px -20px rgba(5,6,15,0.45);
  --shadow-md:0 16px 40px -12px rgba(5,6,15,0.28);
  --ease:cubic-bezier(.16,.84,.44,1);
}

*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;overflow-x:hidden;width:100%;max-width:100%;}
body{
  font-family:'Inter',sans-serif;
  background:var(--paper);
  color:var(--ink);
  overflow-x:hidden;
  width:100%;
  max-width:100%;
  position:relative;
  -webkit-font-smoothing:antialiased;
}
img{max-width:100%;display:block;}
/* Global overflow safety net: nothing should ever force horizontal scroll */
section, header, footer, .container, .hero, .hero-content, .about-grid, .course-grid,
.why-grid, .test-grid, .footer-grid, .reg-wrap, .reg-card{
  max-width:100%;
}
a{text-decoration:none;color:inherit;}
button{font-family:inherit;cursor:pointer;border:none;background:none;}
ul{list-style:none;}
input,select{font-family:inherit;}
.mono{font-family:'JetBrains Mono',monospace;}
.container{max-width:1240px;width:100%;margin:0 auto;padding:0 28px;}
h1,h2,h3,h4,p,a,span,li,label,button,input,select{overflow-wrap:break-word;word-break:break-word;}
/* Defensive fix: flex/grid children default to min-width:auto (content-based),
   which is the #1 cause of silent horizontal overflow on small screens.
   Forcing min-width:0 lets every item shrink to fit its track/container. */
.hero-content,.hero-content > *,
.about-grid,.about-grid > *,
.course-grid,.course-grid > *,
.why-grid,.why-grid > *,
.test-grid,.test-grid > *,
.footer-grid,.footer-grid > *,
.stats-grid,.stats-grid > *,
.form-row,.form-row > *,
.nav-inner,.nav-inner > *,
.bank-row,.bank-row > *,
.course-meta,.course-meta > *,
.amount-preview,.amount-preview > *,
.step-track,.step-track > *{min-width:0;}
.eyebrow{
  font-family:'JetBrains Mono',monospace;
  font-size:12px;
  letter-spacing:0.14em;
  text-transform:uppercase;
  color:var(--blue);
  font-weight:700;
  display:flex;align-items:center;gap:10px;
  margin-bottom:16px;
}
.eyebrow::before{content:"";width:22px;height:1px;background:var(--blue);display:inline-block;}
h1,h2,h3,h4{font-family:'Space Grotesk',sans-serif;letter-spacing:-0.02em;}
.section{padding:120px 0;position:relative;}
.section-head{max-width:640px;margin-bottom:64px;}
.section-head h2{font-size:clamp(32px,4.2vw,48px);line-height:1.1;font-weight:600;color:var(--navy);}
.section-head p{font-size:17px;color:var(--muted-dark);margin-top:16px;line-height:1.6;}
.section-head.center{margin-left:auto;margin-right:auto;text-align:center;}

/* reduced motion */
@media (prefers-reduced-motion: reduce){
  *{animation-duration:0.001ms !important;animation-iteration-count:1 !important;transition-duration:0.001ms !important;scroll-behavior:auto !important;}
}

/* ============ LOADING SCREEN ============ */
#loader{
  position:fixed;inset:0;z-index:9999;
  background:var(--ink);
  display:flex;align-items:center;justify-content:center;
  flex-direction:column;gap:22px;
  transition:opacity .7s var(--ease), visibility .7s var(--ease);
}
#loader.hide{opacity:0;visibility:hidden;pointer-events:none;}
.loader-mark{font-family:'Space Grotesk';font-weight:700;font-size:22px;color:#fff;letter-spacing:-0.01em;display:flex;align-items:center;gap:10px;}
.loader-mark .dot{width:8px;height:8px;border-radius:50%;background:var(--cyan);box-shadow:0 0 14px var(--cyan);}
.loader-bar{width:220px;height:2px;background:rgba(255,255,255,0.12);border-radius:2px;overflow:hidden;}
.loader-bar::after{content:"";display:block;height:100%;width:40%;background:linear-gradient(90deg,var(--blue),var(--cyan));animation:loadmove 1.1s ease-in-out infinite;}
@keyframes loadmove{0%{transform:translateX(-100%);}100%{transform:translateX(340%);}}
.loader-sub{font-family:'JetBrains Mono';font-size:11px;letter-spacing:0.12em;color:var(--muted);text-transform:uppercase;}

/* ============ NAV ============ */
header{
  position:fixed;top:0;left:0;right:0;z-index:1000;
  padding:22px 0;
  transition:all .4s var(--ease);
}
header.scrolled{
  padding:14px 0;
  background:rgba(5,6,15,0.72);
  backdrop-filter:blur(18px) saturate(160%);
  -webkit-backdrop-filter:blur(18px) saturate(160%);
  border-bottom:1px solid var(--line);
}
.nav-inner{display:flex;align-items:center;justify-content:space-between;}
.logo{display:flex;align-items:center;gap:10px;font-family:'Space Grotesk';font-weight:700;font-size:18px;color:#fff;}
.logo-mark{width:34px;height:34px;border-radius:9px;background:linear-gradient(135deg,var(--blue),var(--cyan));display:flex;align-items:center;justify-content:center;font-size:14px;font-weight:700;color:#fff;flex-shrink:0;}
.nav-inner{gap:14px;}
.nav-links{display:flex;gap:38px;align-items:center;}
.nav-links a{font-size:14px;font-weight:500;color:rgba(255,255,255,0.78);transition:color .25s;position:relative;}
.nav-links a:hover{color:#fff;}
.nav-cta{
  padding:11px 22px;border-radius:100px;
  background:linear-gradient(135deg,var(--blue),var(--cyan));
  color:#fff;font-weight:600;font-size:14px;
  transition:transform .3s var(--ease), box-shadow .3s var(--ease);
  box-shadow:0 8px 24px -8px rgba(37,99,235,0.6);
}
.nav-cta:hover{transform:translateY(-2px);box-shadow:0 14px 30px -8px rgba(37,99,235,0.75);}
.burger{display:none;flex-direction:column;gap:5px;width:26px;cursor:pointer;}
.burger span{height:2px;background:#fff;border-radius:2px;transition:.3s;}

/* ============ HERO ============ */
.hero{
  position:relative;
  min-height:100vh;
  display:flex;align-items:center;
  background:radial-gradient(120% 90% at 15% 10%, #101833 0%, var(--navy) 45%, var(--ink) 100%);
  overflow:hidden;
  max-width:100vw;
  padding-top:120px;padding-bottom:80px;
}
.hero-grid{
  position:absolute;inset:0;
  background-image:linear-gradient(rgba(255,255,255,0.035) 1px,transparent 1px),linear-gradient(90deg,rgba(255,255,255,0.035) 1px,transparent 1px);
  background-size:64px 64px;
  mask-image:radial-gradient(80% 60% at 50% 30%, black, transparent);
}
.hero-glow{position:absolute;width:640px;height:640px;border-radius:50%;background:radial-gradient(circle,rgba(37,99,235,0.35),transparent 70%);top:-200px;right:-160px;filter:blur(10px);pointer-events:none;}
.hero-glow.two{background:radial-gradient(circle,rgba(6,182,212,0.22),transparent 70%);top:40%;left:-220px;width:520px;height:520px;}

/* signature: animated market line svg */
.market-line-wrap{position:absolute;left:0;right:0;bottom:0;height:220px;opacity:0.9;pointer-events:none;}
.market-line-wrap svg{width:100%;height:100%;}
.market-path{fill:none;stroke:url(#lineGrad);stroke-width:2;stroke-linecap:round;stroke-dasharray:2000;stroke-dashoffset:2000;animation:drawline 3.2s var(--ease) forwards .5s;}
.market-fill{opacity:0;animation:fadein 1.5s ease forwards 2s;}
@keyframes drawline{to{stroke-dashoffset:0;}}
@keyframes fadein{to{opacity:1;}}
.market-dot{animation:pulse 2s ease-in-out infinite;}
@keyframes pulse{0%,100%{r:4;opacity:1;}50%{r:7;opacity:0.5;}}

.hero-content{position:relative;z-index:2;display:grid;grid-template-columns:1.05fr 0.95fr;gap:64px;align-items:center;}
.hero-badge{
  display:inline-flex;align-items:center;gap:8px;
  padding:8px 16px;border-radius:100px;
  background:rgba(255,255,255,0.06);
  border:1px solid rgba(255,255,255,0.12);
  font-family:'JetBrains Mono';font-size:12px;color:var(--cyan);
  margin-bottom:26px;letter-spacing:0.04em;
}
.hero-badge .live-dot{width:6px;height:6px;border-radius:50%;background:var(--success);box-shadow:0 0 10px var(--success);animation:pulse 1.8s infinite;}
.hero h1{
  font-size:clamp(40px,5.6vw,68px);
  line-height:1.04;font-weight:600;color:#fff;
  margin-bottom:24px;
}
.hero h1 .accent{background:linear-gradient(135deg,var(--blue-light),var(--cyan));-webkit-background-clip:text;background-clip:text;color:transparent;}
.hero p.lead{font-size:18px;line-height:1.65;color:rgba(255,255,255,0.68);max-width:520px;margin-bottom:38px;}
.hero-actions{display:flex;gap:16px;flex-wrap:wrap;margin-bottom:56px;}
.btn{
  display:inline-flex;align-items:center;justify-content:center;gap:8px;
  padding:16px 30px;border-radius:100px;font-weight:600;font-size:15px;
  transition:all .35s var(--ease);
}
.btn-primary{
  background:linear-gradient(135deg,var(--blue),var(--cyan));
  color:#fff;box-shadow:0 12px 30px -10px rgba(37,99,235,0.65);
}
.btn-primary:hover{transform:translateY(-3px);box-shadow:0 18px 40px -10px rgba(37,99,235,0.8);}
.btn-ghost{
  background:rgba(255,255,255,0.06);
  border:1px solid rgba(255,255,255,0.16);
  color:#fff;
}
.btn-ghost:hover{background:rgba(255,255,255,0.12);transform:translateY(-3px);}
.btn-block{width:100%;}

.hero-visual{position:relative;}
.hero-card{
  position:relative;border-radius:22px;overflow:hidden;
  border:1px solid rgba(255,255,255,0.14);
  box-shadow:var(--shadow-lg);
  aspect-ratio:4/5;
}
.hero-card img{width:100%;height:100%;object-fit:cover;}
.hero-card::after{content:"";position:absolute;inset:0;background:linear-gradient(180deg,rgba(5,6,15,0) 40%,rgba(5,6,15,0.75) 100%);}
.float-chip{
  position:absolute;z-index:3;
  background:rgba(10,14,39,0.72);
  backdrop-filter:blur(16px);
  border:1px solid rgba(255,255,255,0.14);
  border-radius:16px;padding:16px 18px;
  box-shadow:var(--shadow-md);
  animation:floaty 5s ease-in-out infinite;
}
.float-chip.a{top:8%;left:-4%;animation-delay:0s;max-width:160px;}
.float-chip.b{bottom:10%;right:-2%;animation-delay:1.2s;max-width:160px;}
@keyframes floaty{0%,100%{transform:translateY(0);}50%{transform:translateY(-12px);}}
.chip-label{font-size:11px;color:var(--muted);font-family:'JetBrains Mono';text-transform:uppercase;letter-spacing:.08em;margin-bottom:4px;}
.chip-value{font-family:'Space Grotesk';font-weight:700;font-size:20px;color:#fff;}
.chip-sub{font-size:11px;color:var(--success);font-family:'JetBrains Mono';margin-top:2px;}

/* ============ STATS ============ */
.stats-bar{background:var(--ink);position:relative;z-index:2;padding:56px 0;}
.stats-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:20px;}
.stat{text-align:center;padding:0 12px;border-left:1px solid var(--line);}
.stat:first-child{border-left:none;}
.stat-num{font-family:'Space Grotesk';font-weight:700;font-size:clamp(30px,3.4vw,44px);color:#fff;display:flex;align-items:baseline;justify-content:center;gap:2px;}
.stat-num .plus{color:var(--cyan);font-size:0.6em;}
.stat-label{font-size:13px;color:var(--muted);margin-top:8px;font-family:'JetBrains Mono';letter-spacing:.02em;}

/* ============ ABOUT ============ */
.about{background:var(--white);}
.about-grid{display:grid;grid-template-columns:0.85fr 1.15fr;gap:72px;align-items:center;}
.about-visual{position:relative;}
.about-img{border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow-md);aspect-ratio:1/1.05;}
.about-img img{width:100%;height:100%;object-fit:cover;}
.about-badge-card{
  position:absolute;bottom:-28px;left:-28px;
  background:var(--white);border-radius:16px;padding:20px 22px;
  box-shadow:var(--shadow-lg);border:1px solid var(--line-soft);
  display:flex;align-items:center;gap:14px;
}
.about-badge-card .icon{width:46px;height:46px;border-radius:12px;background:linear-gradient(135deg,var(--blue),var(--cyan));display:flex;align-items:center;justify-content:center;color:#fff;flex-shrink:0;}
.about-badge-card strong{font-family:'Space Grotesk';font-size:16px;display:block;color:var(--navy);}
.about-badge-card span{font-size:12px;color:var(--muted-dark);}
.about-copy p{font-size:16.5px;line-height:1.75;color:var(--muted-dark);margin-bottom:18px;}
.about-copy strong{color:var(--navy);}
.about-signature{display:flex;align-items:center;gap:16px;margin-top:34px;padding-top:28px;border-top:1px solid var(--line-soft);}
.sig-name{font-family:'Space Grotesk';font-weight:700;font-size:17px;color:var(--navy);}
.sig-role{font-size:13px;color:var(--blue);font-family:'JetBrains Mono';}
.about-pills{display:flex;gap:12px;flex-wrap:wrap;margin-top:26px;}
.pill{padding:9px 16px;border-radius:100px;background:var(--paper);border:1px solid var(--line-soft);font-size:13px;font-weight:600;color:var(--navy);}

/* ============ COURSES ============ */
.courses{background:var(--paper);}
.course-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:28px;}
.course-card{
  background:var(--white);border-radius:var(--radius);overflow:hidden;
  border:1px solid var(--line-soft);
  box-shadow:var(--shadow-md);
  transition:transform .4s var(--ease), box-shadow .4s var(--ease);
  display:flex;flex-direction:column;
}
.course-card:hover{transform:translateY(-8px);box-shadow:var(--shadow-lg);}
.course-media{position:relative;aspect-ratio:16/10;overflow:hidden;}
.course-media img{width:100%;height:100%;object-fit:cover;transition:transform .6s var(--ease);}
.course-card:hover .course-media img{transform:scale(1.06);}
.course-tag{position:absolute;top:16px;left:16px;background:rgba(5,6,15,0.7);backdrop-filter:blur(8px);color:#fff;font-size:11px;font-family:'JetBrains Mono';padding:6px 12px;border-radius:100px;letter-spacing:.04em;}
.course-body{padding:26px 26px 28px;display:flex;flex-direction:column;flex:1;}
.course-body h3{font-size:19px;font-weight:600;color:var(--navy);margin-bottom:10px;line-height:1.35;}
.course-meta{display:flex;justify-content:space-between;align-items:center;margin-bottom:16px;}
.course-price{font-family:'JetBrains Mono';font-weight:700;font-size:22px;color:var(--blue);}
.course-duration{font-size:12px;color:var(--muted-dark);background:var(--paper);padding:5px 10px;border-radius:8px;}
.course-list{margin:6px 0 22px;flex:1;}
.course-list li{font-size:13.5px;color:var(--muted-dark);padding:6px 0;display:flex;align-items:flex-start;gap:8px;line-height:1.4;}
.course-list li::before{content:"";width:14px;height:14px;border-radius:4px;background:linear-gradient(135deg,var(--blue),var(--cyan));flex-shrink:0;margin-top:2px;-webkit-mask:url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="black" d="M9 16.2 4.8 12l-1.4 1.4L9 19 21 7l-1.4-1.4z"/></svg>') no-repeat center / contain;mask:url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="black" d="M9 16.2 4.8 12l-1.4 1.4L9 19 21 7l-1.4-1.4z"/></svg>') no-repeat center / contain;}
.course-cta{
  width:100%;padding:14px;border-radius:12px;text-align:center;
  background:var(--navy);color:#fff;font-weight:600;font-size:14px;
  transition:background .3s;
}
.course-cta:hover{background:var(--blue);}

/* ============ WHY CHOOSE US ============ */
.why{background:var(--ink);color:#fff;position:relative;overflow:hidden;max-width:100vw;}
.why::before{content:"";position:absolute;top:-100px;right:-100px;width:500px;height:500px;border-radius:50%;background:radial-gradient(circle,rgba(37,99,235,0.25),transparent 70%);}
.why .section-head h2, .why .section-head p{color:#fff;}
.why .section-head p{color:rgba(255,255,255,0.6);}
.why-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;position:relative;z-index:2;}
.why-card{
  background:rgba(255,255,255,0.04);
  border:1px solid rgba(255,255,255,0.1);
  border-radius:var(--radius);padding:32px 28px;
  transition:all .4s var(--ease);
}
.why-card:hover{background:rgba(255,255,255,0.08);transform:translateY(-6px);border-color:rgba(255,255,255,0.22);}
.why-icon{width:48px;height:48px;border-radius:13px;background:linear-gradient(135deg,var(--blue),var(--cyan));display:flex;align-items:center;justify-content:center;margin-bottom:20px;color:#fff;}
.why-card h3{font-size:18px;font-weight:600;margin-bottom:10px;}
.why-card p{font-size:14px;color:rgba(255,255,255,0.58);line-height:1.6;}

/* ============ TESTIMONIALS ============ */
.testimonials{background:var(--white);}
.test-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:26px;}
.test-card{
  background:var(--paper);border-radius:var(--radius);padding:30px 28px;
  border:1px solid var(--line-soft);
}
.stars{color:#F5A623;font-size:14px;margin-bottom:16px;letter-spacing:2px;}
.test-card p{font-size:15px;line-height:1.7;color:var(--navy);margin-bottom:22px;}
.test-person{display:flex;align-items:center;gap:12px;}
.test-avatar{width:42px;height:42px;border-radius:50%;background:linear-gradient(135deg,var(--blue),var(--cyan));display:flex;align-items:center;justify-content:center;color:#fff;font-weight:700;font-family:'Space Grotesk';flex-shrink:0;}
.test-name{font-weight:700;font-size:14px;color:var(--navy);}
.test-role{font-size:12px;color:var(--muted-dark);}

/* ============ FAQ ============ */
.faq{background:var(--paper);}
.faq-list{max-width:820px;margin:0 auto;}
.faq-item{background:var(--white);border:1px solid var(--line-soft);border-radius:14px;margin-bottom:14px;overflow:hidden;}
.faq-q{width:100%;padding:22px 26px;display:flex;justify-content:space-between;align-items:center;gap:20px;text-align:left;font-family:'Space Grotesk';font-weight:600;font-size:15.5px;color:var(--navy);}
.faq-q .icon{width:26px;height:26px;border-radius:50%;background:var(--paper);display:flex;align-items:center;justify-content:center;flex-shrink:0;transition:transform .35s var(--ease);font-size:14px;color:var(--blue);}
.faq-item.open .faq-q .icon{transform:rotate(45deg);}
.faq-a{max-height:0;overflow:hidden;transition:max-height .4s var(--ease);}
.faq-a-inner{padding:0 26px 22px;font-size:14.5px;color:var(--muted-dark);line-height:1.7;}

/* ============ REGISTRATION / PAYMENT ============ */
.register{background:var(--navy);position:relative;overflow:hidden;color:#fff;max-width:100vw;}
.register::before{content:"";position:absolute;bottom:-140px;left:-140px;width:480px;height:480px;border-radius:50%;background:radial-gradient(circle,rgba(6,182,212,0.2),transparent 70%);}
.register .section-head h2, .register .section-head p{color:#fff;}
.register .section-head p{color:rgba(255,255,255,0.62);}
.reg-wrap{max-width:640px;margin:0 auto;position:relative;z-index:2;}
.reg-card{
  background:rgba(255,255,255,0.05);
  border:1px solid rgba(255,255,255,0.12);
  backdrop-filter:blur(10px);
  border-radius:22px;padding:44px;
  box-shadow:var(--shadow-lg);
}
.step-track{display:flex;align-items:center;gap:10px;margin-bottom:34px;}
.step-dot{width:30px;height:30px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:12px;font-weight:700;font-family:'JetBrains Mono';background:rgba(255,255,255,0.08);color:rgba(255,255,255,0.5);border:1px solid rgba(255,255,255,0.16);flex-shrink:0;transition:all .3s;}
.step-dot.active{background:linear-gradient(135deg,var(--blue),var(--cyan));color:#fff;border-color:transparent;}
.step-line{flex:1;height:1px;background:rgba(255,255,255,0.14);}
.form-group{margin-bottom:20px;}
.form-group label{display:block;font-size:13px;font-weight:600;color:rgba(255,255,255,0.75);margin-bottom:9px;font-family:'JetBrains Mono';letter-spacing:.02em;}
.form-group input, .form-group select{
  width:100%;padding:15px 16px;border-radius:12px;
  background:rgba(255,255,255,0.06);
  border:1px solid rgba(255,255,255,0.14);
  color:#fff;font-size:14.5px;
  transition:border-color .3s, background .3s;
}
.form-group select option{background:var(--navy);color:#fff;}
.form-group input::placeholder{color:rgba(255,255,255,0.32);}
.form-group input:focus, .form-group select:focus{outline:none;border-color:var(--cyan);background:rgba(255,255,255,0.1);}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:16px;}
.amount-preview{
  display:flex;justify-content:space-between;align-items:center;
  padding:18px 20px;border-radius:14px;
  background:linear-gradient(135deg,rgba(37,99,235,0.18),rgba(6,182,212,0.14));
  border:1px solid rgba(255,255,255,0.14);
  margin-bottom:26px;
}
.amount-preview .lbl{font-size:12px;color:rgba(255,255,255,0.6);font-family:'JetBrains Mono';text-transform:uppercase;letter-spacing:.06em;}
.amount-preview .val{font-family:'Space Grotesk';font-weight:700;font-size:24px;color:#fff;}

/* payment section */
.pay-panel{display:none;}
.pay-panel.show{display:block;animation:fadeup .5s var(--ease);}
@keyframes fadeup{from{opacity:0;transform:translateY(14px);}to{opacity:1;transform:translateY(0);}}
.bank-card{
  background:linear-gradient(135deg,#0F1538,#141B47);
  border:1px solid rgba(255,255,255,0.14);
  border-radius:16px;padding:26px;margin-bottom:24px;
  position:relative;overflow:hidden;
}
.bank-card::after{content:"";position:absolute;top:-40px;right:-40px;width:140px;height:140px;border-radius:50%;background:radial-gradient(circle,rgba(6,182,212,0.25),transparent 70%);}
.bank-row{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:6px 10px;padding:12px 0;border-bottom:1px solid rgba(255,255,255,0.08);position:relative;z-index:2;}
.bank-row:last-child{border-bottom:none;}
.bank-row .k{font-size:12px;color:rgba(255,255,255,0.55);font-family:'JetBrains Mono';text-transform:uppercase;letter-spacing:.05em;flex-shrink:0;}
.bank-row .v{font-family:'Space Grotesk';font-weight:700;font-size:16px;color:#fff;min-width:0;word-break:break-word;text-align:right;}
.bank-row .v.copyable{cursor:pointer;display:flex;align-items:center;flex-wrap:wrap;justify-content:flex-end;gap:8px;}
.copy-tag{font-size:10px;background:rgba(6,182,212,0.2);color:var(--cyan);padding:3px 8px;border-radius:6px;font-family:'JetBrains Mono';}
.upload-box{
  border:1.5px dashed rgba(255,255,255,0.24);
  border-radius:14px;padding:30px 20px;text-align:center;
  cursor:pointer;transition:all .3s;margin-bottom:24px;
}
.upload-box:hover, .upload-box.drag{border-color:var(--cyan);background:rgba(6,182,212,0.06);}
.upload-box .u-icon{width:44px;height:44px;margin:0 auto 14px;border-radius:12px;background:rgba(255,255,255,0.08);display:flex;align-items:center;justify-content:center;color:var(--cyan);}
.upload-box p{font-size:13.5px;color:rgba(255,255,255,0.55);}
.upload-box strong{color:#fff;}
.file-chosen{margin-top:12px;font-size:13px;color:var(--success);font-family:'JetBrains Mono';display:none;}
.back-link{font-size:13px;color:rgba(255,255,255,0.5);display:inline-flex;align-items:center;gap:6px;margin-bottom:20px;}
.back-link:hover{color:#fff;}

.success-panel{display:none;text-align:center;padding:20px 0;}
.success-panel.show{display:block;animation:fadeup .5s var(--ease);}
.success-icon{width:70px;height:70px;border-radius:50%;background:linear-gradient(135deg,var(--success),#06B6D4);display:flex;align-items:center;justify-content:center;margin:0 auto 24px;font-size:30px;color:#fff;box-shadow:0 0 0 8px rgba(16,185,129,0.14);}
.success-panel h3{font-size:24px;color:#fff;margin-bottom:12px;}
.success-panel p{font-size:14.5px;color:rgba(255,255,255,0.62);line-height:1.7;margin-bottom:28px;max-width:440px;margin-left:auto;margin-right:auto;}

/* ============ FOOTER ============ */
footer{background:var(--ink);color:#fff;padding:80px 0 30px;}
.footer-grid{display:grid;grid-template-columns:1.4fr 1fr 1fr;gap:60px;margin-bottom:60px;}
.footer-logo{display:flex;align-items:center;gap:10px;font-family:'Space Grotesk';font-weight:700;font-size:19px;margin-bottom:18px;}
.footer-brand p{font-size:14px;color:rgba(255,255,255,0.5);line-height:1.7;max-width:320px;}
.footer-col h4{font-family:'JetBrains Mono';font-size:12px;text-transform:uppercase;letter-spacing:.08em;color:rgba(255,255,255,0.4);margin-bottom:20px;}
.footer-col li{margin-bottom:13px;font-size:14px;color:rgba(255,255,255,0.68);}
.footer-col li:hover{color:#fff;}
.footer-bottom{border-top:1px solid var(--line);padding-top:26px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:14px;}
.footer-bottom p{font-size:13px;color:rgba(255,255,255,0.42);}
.footer-socials{display:flex;gap:12px;}
.footer-socials a{width:36px;height:36px;border-radius:10px;background:rgba(255,255,255,0.06);display:flex;align-items:center;justify-content:center;font-size:14px;transition:.3s;}
.footer-socials a:hover{background:var(--blue);}

/* ============ FLOATING BUTTONS ============ */
.whatsapp-float{
  position:fixed;bottom:26px;right:26px;z-index:900;
  width:60px;height:60px;border-radius:50%;
  background:#25D366;display:flex;align-items:center;justify-content:center;
  box-shadow:0 12px 30px -8px rgba(37,211,102,0.65);
  transition:transform .3s var(--ease);
}
.whatsapp-float:hover{transform:scale(1.08);}
.whatsapp-float svg{width:30px;height:30px;}
.pulse-ring{position:absolute;inset:0;border-radius:50%;border:2px solid #25D366;animation:pulsering 2s ease-out infinite;}
@keyframes pulsering{0%{transform:scale(1);opacity:0.7;}100%{transform:scale(1.7);opacity:0;}}

.scrolltop{
  position:fixed;bottom:26px;right:98px;z-index:900;
  width:48px;height:48px;border-radius:50%;
  background:var(--navy);color:#fff;display:flex;align-items:center;justify-content:center;
  box-shadow:var(--shadow-md);
  opacity:0;visibility:hidden;transform:translateY(10px);
  transition:all .35s var(--ease);
}
.scrolltop.show{opacity:1;visibility:visible;transform:translateY(0);}
.scrolltop:hover{background:var(--blue);}

/* ============ SCROLL REVEAL ============ */
.reveal{opacity:0;transform:translateY(30px);transition:opacity .8s var(--ease), transform .8s var(--ease);}
.reveal.in{opacity:1;transform:translateY(0);}
.reveal-stagger.in > *{animation:none;}

/* ============ RESPONSIVE ============ */
@media (max-width:980px){
  .hero-content{grid-template-columns:1fr;}
  .hero-visual{max-width:420px;margin:0 auto;}
  .about-grid{grid-template-columns:1fr;}
  .course-grid{grid-template-columns:1fr 1fr;}
  .why-grid{grid-template-columns:1fr 1fr;}
  .test-grid{grid-template-columns:1fr 1fr;}
  .footer-grid{grid-template-columns:1fr 1fr;}
  .stats-grid{grid-template-columns:1fr 1fr;gap:32px;}
  .stat{border-left:none;}
  .about-badge-card{position:static;margin-top:-40px;margin-left:20px;margin-right:20px;}
}
@media (max-width:760px){
  .nav-links{display:none;}
  .nav-cta{display:none;}
  .burger{display:flex;}
  .logo{font-size:15px;gap:8px;}
  .logo-mark{width:30px;height:30px;font-size:12px;}
  .section{padding:80px 0;}
  .course-grid{grid-template-columns:1fr;}
  .why-grid{grid-template-columns:1fr;}
  .test-grid{grid-template-columns:1fr;}
  .footer-grid{grid-template-columns:1fr;gap:36px;}
  .form-row{grid-template-columns:1fr;}
  .reg-card{padding:28px 22px;}
  .stats-grid{grid-template-columns:1fr 1fr;}
  .scrolltop{right:20px;bottom:96px;}
  .whatsapp-float{right:20px;bottom:26px;}
  .about-badge-card{position:static;margin-top:-40px;margin-left:20px;margin-right:20px;}
}
@media (max-width:400px){
  .container{padding:0 18px;}
  .hero{padding-top:110px;}
  .hero h1{font-size:clamp(30px,9vw,40px);}
  .section-head h2{font-size:clamp(26px,7.5vw,32px);}
  .hero p.lead{font-size:16px;}
  .hero-actions{gap:12px;}
  .btn{padding:14px 22px;font-size:14px;}
  .reg-card{padding:22px 16px;}
  .float-chip{padding:12px 14px;}
  .chip-value{font-size:17px;}
}

/* mobile nav drawer */
.mobile-drawer{
  position:fixed;top:0;right:0;width:78%;max-width:320px;height:100vh;z-index:1100;
  background:var(--ink);border-left:1px solid var(--line);
  padding:100px 30px 30px;
  transform:translateX(100%);
  transition:transform .45s var(--ease);
}
.mobile-drawer.open{transform:translateX(0);}
.mobile-drawer a{display:block;color:#fff;font-size:17px;font-weight:500;padding:16px 0;border-bottom:1px solid var(--line);}
.drawer-close{position:absolute;top:28px;right:28px;color:#fff;font-size:26px;}
.drawer-backdrop{position:fixed;inset:0;background:rgba(0,0,0,0.5);z-index:1050;opacity:0;visibility:hidden;transition:.4s;}
.drawer-backdrop.show{opacity:1;visibility:visible;}
</style>
</head>
<body>

<!-- ============ LOADING SCREEN ============ -->
<div id="loader">
  <div class="loader-mark"><span class="dot"></span>IBRAHIM AMINU MENTORSHIP</div>
  <div class="loader-bar"></div>
  <div class="loader-sub">Preparing your journey to financial freedom</div>
</div>

<!-- ============ NAV ============ -->
<header id="siteHeader">
  <div class="container nav-inner">
    <a href="#home" class="logo"><span class="logo-mark">IA</span>Ibrahim Aminu Mentorship</a>
    <nav class="nav-links">
      <a href="#about">About</a>
      <a href="#courses">Courses</a>
      <a href="#why">Why Us</a>
      <a href="#testimonials">Testimonials</a>
      <a href="#faq">FAQ</a>
    </nav>
    <a href="#register" class="nav-cta">Register Now</a>
    <div class="burger" id="burger"><span></span><span></span><span></span></div>
  </div>
</header>

<div class="drawer-backdrop" id="drawerBackdrop"></div>
<div class="mobile-drawer" id="mobileDrawer">
  <div class="drawer-close" id="drawerClose">&times;</div>
  <a href="#about">About</a>
  <a href="#courses">Courses</a>
  <a href="#why">Why Us</a>
  <a href="#testimonials">Testimonials</a>
  <a href="#faq">FAQ</a>
  <a href="#register">Register Now</a>
</div>

<!-- ============ HERO ============ -->
<section class="hero" id="home">
  <div class="hero-grid"></div>
  <div class="hero-glow"></div>
  <div class="hero-glow two"></div>

  <div class="container hero-content">
    <div>
      <div class="hero-badge"><span class="live-dot"></span> LIVE MENTORSHIP · ENROLLMENT OPEN</div>
      <h1>Learn High‑Income Skills, Investing &amp; <span class="accent">Financial Freedom.</span></h1>
      <p class="lead">Practical, mentor‑led courses in stock market investing, real estate, AI content creation and web development — taught by Coach Ibrahim Aminu Musa to help you build real, lasting wealth.</p>
      <div class="hero-actions">
        <a href="#register" class="btn btn-primary">Register Now →</a>
        <a href="#courses" class="btn btn-ghost">Learn More</a>
      </div>
    </div>

    <div class="hero-visual">
      <div class="hero-card">
        <img src="https://images.unsplash.com/photo-1611974789855-9c2a0a7236a3?auto=format&fit=crop&w=900&q=80" alt="Stock market trading dashboard">
      </div>
      <div class="float-chip a">
        <div class="chip-label">Portfolio Growth</div>
        <div class="chip-value">+184%</div>
        <div class="chip-sub">▲ 12 months</div>
      </div>
      <div class="float-chip b">
        <div class="chip-label">Students Trained</div>
        <div class="chip-value">500+</div>
        <div class="chip-sub">Certified Graduates</div>
      </div>
    </div>
  </div>

  <div class="market-line-wrap">
    <svg viewBox="0 0 1200 220" preserveAspectRatio="none">
      <defs>
        <linearGradient id="lineGrad" x1="0" y1="0" x2="1" y2="0">
          <stop offset="0%" stop-color="#2563EB"/>
          <stop offset="100%" stop-color="#06B6D4"/>
        </linearGradient>
        <linearGradient id="fillGrad" x1="0" y1="0" x2="0" y2="1">
          <stop offset="0%" stop-color="#2563EB" stop-opacity="0.22"/>
          <stop offset="100%" stop-color="#2563EB" stop-opacity="0"/>
        </linearGradient>
      </defs>
      <path class="market-fill" fill="url(#fillGrad)" d="M0,160 L60,150 L120,165 L180,120 L240,140 L300,95 L360,110 L420,70 L480,90 L540,55 L600,75 L660,40 L720,60 L780,30 L840,50 L900,20 L960,45 L1020,15 L1080,35 L1140,10 L1200,25 L1200,220 L0,220 Z"/>
      <path class="market-path" d="M0,160 L60,150 L120,165 L180,120 L240,140 L300,95 L360,110 L420,70 L480,90 L540,55 L600,75 L660,40 L720,60 L780,30 L840,50 L900,20 L960,45 L1020,15 L1080,35 L1140,10 L1200,25"/>
      <circle class="market-dot" cx="1200" cy="25" r="5" fill="#06B6D4"/>
    </svg>
  </div>
</section>

<!-- ============ STATS ============ -->
<div class="stats-bar">
  <div class="container stats-grid">
    <div class="stat"><div class="stat-num"><span class="counter" data-target="500">0</span><span class="plus">+</span></div><div class="stat-label">STUDENTS TRAINED</div></div>
    <div class="stat"><div class="stat-num"><span class="counter" data-target="5">0</span><span class="plus">+</span></div><div class="stat-label">PREMIUM COURSES</div></div>
    <div class="stat"><div class="stat-num"><span class="counter" data-target="50">0</span><span class="plus">+</span></div><div class="stat-label">LESSONS</div></div>
    <div class="stat"><div class="stat-num" style="font-size:clamp(20px,2vw,26px);">Certified</div><div class="stat-label">PROFESSIONAL CERTIFICATE</div></div>
  </div>
</div>

<!-- ============ ABOUT ============ -->
<section class="section about" id="about">
  <div class="container about-grid">
    <div class="about-visual reveal">
      <div class="about-img">
        <img src="https://images.unsplash.com/photo-1521737604893-d14cc237f11d?auto=format&fit=crop&w=800&q=80" alt="Professional business mentor">
      </div>
      <div class="about-badge-card">
        <div class="icon">★</div>
        <div><strong>4.9 / 5.0</strong><span>Student Satisfaction</span></div>
      </div>
    </div>
    <div class="about-copy reveal">
      <div class="eyebrow">About the Mentor</div>
      <h2 style="font-size:clamp(28px,3.6vw,40px);color:var(--navy);font-weight:600;margin-bottom:22px;">Building wealth is a skill. We teach it properly.</h2>
      <p><strong>Coach Ibrahim Aminu Musa</strong> teaches practical, real‑world skills that help students build wealth, invest wisely, create multiple income streams, and achieve true financial independence.</p>
      <p>Every course is designed around one goal: turning knowledge into income. From the Nigerian stock market to real estate, AI‑powered content creation and modern web development, students leave with skills they can apply immediately — backed by direct, one‑on‑one mentorship.</p>
      <div class="about-pills">
        <div class="pill">Stock Market Mentor</div>
        <div class="pill">Financial Coach</div>
        <div class="pill">Real Estate Mentor</div>
        <div class="pill">AI &amp; Web Trainer</div>
      </div>
      <div class="about-signature">
        <div>
          <div class="sig-name">Coach Ibrahim Aminu Musa</div>
          <div class="sig-role">Founder, Ibrahim Aminu Mentorship</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============ COURSES ============ -->
<section class="section courses" id="courses">
  <div class="container">
    <div class="section-head center reveal" style="margin-left:auto;margin-right:auto;">
      <div class="eyebrow" style="justify-content:center;">Our Courses</div>
      <h2>Five paths to financial independence</h2>
      <p>Pick the skill that fits your goals — every course includes lifetime knowledge, mentorship and a certificate on completion.</p>
    </div>

    <div class="course-grid">

      <div class="course-card reveal">
        <div class="course-media">
          <img src="https://images.unsplash.com/photo-1590283603385-17ffb3a7f29f?auto=format&fit=crop&w=700&q=80" alt="Stock market investing">
          <div class="course-tag">STOCK MARKET</div>
        </div>
        <div class="course-body">
          <h3>Learn Stock Market From Scratch to Expert</h3>
          <div class="course-meta"><span class="course-price mono">₦25,000</span><span class="course-duration">1 Month</span></div>
          <ul class="course-list">
            <li>Beginner to Advanced</li>
            <li>Nigerian Stock Market</li>
            <li>Dividend Investing</li>
            <li>Technical &amp; Fundamental Analysis</li>
            <li>Portfolio Building &amp; Risk Management</li>
            <li>Certificate + Private Mentorship</li>
          </ul>
          <a href="#register" class="course-cta" data-course="Learn Stock Market From Scratch to Expert" data-price="25000">Register for this Course</a>
        </div>
      </div>

      <div class="course-card reveal">
        <div class="course-media">
          <img src="https://images.unsplash.com/photo-1560518883-ce09059eeffa?auto=format&fit=crop&w=700&q=80" alt="Real estate investment">
          <div class="course-tag">REAL ESTATE</div>
        </div>
        <div class="course-body">
          <h3>Learn Real Estate Investment</h3>
          <div class="course-meta"><span class="course-price mono">₦30,000</span><span class="course-duration">Self‑paced</span></div>
          <ul class="course-list">
            <li>Land Investment</li>
            <li>Property Investment</li>
            <li>Rental Income</li>
            <li>Real Estate Analysis</li>
            <li>Investment Strategies</li>
          </ul>
          <a href="#register" class="course-cta" data-course="Learn Real Estate Investment" data-price="30000">Register for this Course</a>
        </div>
      </div>

      <div class="course-card reveal">
        <div class="course-media">
          <img src="https://images.unsplash.com/photo-1574717024653-61fd2cf4d44d?auto=format&fit=crop&w=700&q=80" alt="Video editing and AI content creation">
          <div class="course-tag">AI &amp; VIDEO</div>
        </div>
        <div class="course-body">
          <h3>Professional Video Editing &amp; AI Content Creation</h3>
          <div class="course-meta"><span class="course-price mono">₦30,000</span><span class="course-duration">Self‑paced</span></div>
          <ul class="course-list">
            <li>CapCut &amp; Canva Mastery</li>
            <li>Free AI Tools</li>
            <li>AI Video Creation</li>
            <li>Content Creation</li>
            <li>Social Media Growth</li>
          </ul>
          <a href="#register" class="course-cta" data-course="Professional Video Editing & AI Content Creation" data-price="30000">Register for this Course</a>
        </div>
      </div>

      <div class="course-card reveal">
        <div class="course-media">
          <img src="https://images.unsplash.com/photo-1547658719-da2b51169166?auto=format&fit=crop&w=700&q=80" alt="Website development">
          <div class="course-tag">WEB DEV</div>
        </div>
        <div class="course-body">
          <h3>Website Development &amp; Google Business Profile</h3>
          <div class="course-meta"><span class="course-price mono">₦30,000</span><span class="course-duration">Self‑paced</span></div>
          <ul class="course-list">
            <li>HTML Website Development</li>
            <li>Responsive Design</li>
            <li>Google Business Profile Setup</li>
            <li>SEO Basics</li>
            <li>Business Branding</li>
          </ul>
          <a href="#register" class="course-cta" data-course="Website Development & Google Business Profile" data-price="30000">Register for this Course</a>
        </div>
      </div>

      <div class="course-card reveal">
        <div class="course-media">
          <img src="https://images.unsplash.com/photo-1642543348745-775a8ee49af7?auto=format&fit=crop&w=700&q=80" alt="Financial coaching">
          <div class="course-tag">FINANCIAL COACHING</div>
        </div>
        <div class="course-body">
          <h3>Financial Coach Mentorship</h3>
          <div class="course-meta"><span class="course-price mono">₦50,000</span><span class="course-duration">Premium</span></div>
          <ul class="course-list">
            <li>Financial Planning</li>
            <li>Investment Strategy</li>
            <li>Budgeting</li>
            <li>Business Growth</li>
            <li>Long‑term Wealth Building</li>
            <li>One‑on‑One Coaching</li>
          </ul>
          <a href="#register" class="course-cta" data-course="Financial Coach Mentorship" data-price="50000">Register for this Course</a>
        </div>
      </div>

      <div class="course-card reveal" style="background:linear-gradient(135deg,var(--navy),var(--ink));color:#fff;justify-content:center;">
        <div class="course-body" style="justify-content:center;text-align:center;">
          <h3 style="color:#fff;">Not sure which course fits you?</h3>
          <p style="font-size:14px;color:rgba(255,255,255,0.6);margin-bottom:22px;line-height:1.6;">Chat with Coach Ibrahim directly on WhatsApp and get guided to the right path.</p>
          <a href="https://wa.me/2348087485703?text=Hello%20Coach%20Ibrahim%2C%20I%27d%20like%20guidance%20on%20choosing%20a%20course." target="_blank" class="course-cta" style="background:linear-gradient(135deg,var(--blue),var(--cyan));">Chat on WhatsApp</a>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ============ WHY CHOOSE US ============ -->
<section class="section why" id="why">
  <div class="container">
    <div class="section-head center reveal" style="margin-left:auto;margin-right:auto;">
      <div class="eyebrow" style="justify-content:center;">Why Choose Us</div>
      <h2>Mentorship built for real results</h2>
      <p>Not just theory — a complete system to help you learn, apply, and earn.</p>
    </div>
    <div class="why-grid">
      <div class="why-card reveal">
        <div class="why-icon">✓</div>
        <h3>Practical Learning</h3>
        <p>Hands‑on lessons built around real market scenarios, not just textbook theory.</p>
      </div>
      <div class="why-card reveal">
        <div class="why-icon">◆</div>
        <h3>Professional Mentorship</h3>
        <p>Direct guidance from Coach Ibrahim Aminu Musa throughout your learning journey.</p>
      </div>
      <div class="why-card reveal">
        <div class="why-icon">∞</div>
        <h3>Lifetime Knowledge</h3>
        <p>Skills and frameworks you'll apply for the rest of your financial life.</p>
      </div>
      <div class="why-card reveal">
        <div class="why-icon">🎓</div>
        <h3>Certificate</h3>
        <p>Earn a professional certificate of completion recognized by our community.</p>
      </div>
      <div class="why-card reveal">
        <div class="why-icon">💬</div>
        <h3>WhatsApp Support</h3>
        <p>Direct access to support and mentorship, right from your phone.</p>
      </div>
      <div class="why-card reveal">
        <div class="why-icon">₦</div>
        <h3>Affordable Pricing</h3>
        <p>Premium quality mentorship priced to be accessible to serious learners.</p>
      </div>
    </div>
  </div>
</section>

<!-- ============ TESTIMONIALS ============ -->
<section class="section testimonials" id="testimonials">
  <div class="container">
    <div class="section-head center reveal" style="margin-left:auto;margin-right:auto;">
      <div class="eyebrow" style="justify-content:center;">Testimonials</div>
      <h2>Trusted by our students</h2>
      <p>Real feedback from people building real wealth.</p>
    </div>
    <div class="test-grid">
      <div class="test-card reveal">
        <div class="stars">★★★★★</div>
        <p>"The stock market course completely changed how I think about investing. I built my first portfolio within weeks of finishing."</p>
        <div class="test-person"><div class="test-avatar">A</div><div><div class="test-name">Amina Yusuf</div><div class="test-role">Stock Market Student</div></div></div>
      </div>
      <div class="test-card reveal">
        <div class="stars">★★★★★</div>
        <p>"Coach Ibrahim breaks everything down so simply. The real estate course gave me the confidence to make my first land investment."</p>
        <div class="test-person"><div class="test-avatar">M</div><div><div class="test-name">Musa Bello</div><div class="test-role">Real Estate Student</div></div></div>
      </div>
      <div class="test-card reveal">
        <div class="stars">★★★★★</div>
        <p>"I learned video editing and AI content tools in weeks. Now I create content for clients and earn consistently."</p>
        <div class="test-person"><div class="test-avatar">C</div><div><div class="test-name">Chiamaka Obi</div><div class="test-role">AI &amp; Video Student</div></div></div>
      </div>
    </div>
  </div>
</section>

<!-- ============ FAQ ============ -->
<section class="section faq" id="faq">
  <div class="container">
    <div class="section-head center reveal" style="margin-left:auto;margin-right:auto;">
      <div class="eyebrow" style="justify-content:center;">FAQ</div>
      <h2>Frequently asked questions</h2>
    </div>
    <div class="faq-list">
      <div class="faq-item">
        <button class="faq-q">Do I need prior experience to enroll? <span class="icon">+</span></button>
        <div class="faq-a"><div class="faq-a-inner">No. Every course starts from the basics and builds up to advanced, practical skills — no prior experience required.</div></div>
      </div>
      <div class="faq-item">
        <button class="faq-q">How long do I have access to the course? <span class="icon">+</span></button>
        <div class="faq-a"><div class="faq-a-inner">You get lifetime access to course materials, plus ongoing WhatsApp support from Coach Ibrahim and the mentorship community.</div></div>
      </div>
      <div class="faq-item">
        <button class="faq-q">How do I make payment? <span class="icon">+</span></button>
        <div class="faq-a"><div class="faq-a-inner">After registering, you'll see our OPay bank details. Make payment, upload your receipt, and confirm your registration on WhatsApp.</div></div>
      </div>
      <div class="faq-item">
        <button class="faq-q">Will I get a certificate? <span class="icon">+</span></button>
        <div class="faq-a"><div class="faq-a-inner">Yes. Every student who completes a course receives a professional certificate of completion.</div></div>
      </div>
      <div class="faq-item">
        <button class="faq-q">Can I enroll in more than one course? <span class="icon">+</span></button>
        <div class="faq-a"><div class="faq-a-inner">Absolutely. Many students take multiple courses to build a well‑rounded set of income‑generating skills.</div></div>
      </div>
    </div>
  </div>
</section>

<!-- ============ REGISTRATION / PAYMENT / SUCCESS ============ -->
<section class="section register" id="register">
  <div class="container">
    <div class="section-head center reveal" style="margin-left:auto;margin-right:auto;">
      <div class="eyebrow" style="justify-content:center;">Get Started</div>
      <h2>Register for your course</h2>
      <p>Fill in your details below — takes less than 2 minutes.</p>
    </div>

    <div class="reg-wrap">
      <div class="reg-card">

        <div class="step-track">
          <div class="step-dot active" id="dot1">1</div>
          <div class="step-line"></div>
          <div class="step-dot" id="dot2">2</div>
          <div class="step-line"></div>
          <div class="step-dot" id="dot3">3</div>
        </div>

        <!-- STEP 1: REGISTRATION FORM -->
        <div class="pay-panel show" id="panelForm">
          <form id="regForm">
            <div class="form-group">
              <label>Full Name</label>
              <input type="text" id="fullName" placeholder="e.g. Ahmed Musa" required>
            </div>
            <div class="form-row">
              <div class="form-group">
                <label>Email Address</label>
                <input type="email" id="email" placeholder="you@email.com" required>
              </div>
              <div class="form-group">
                <label>Phone Number</label>
                <input type="tel" id="phone" placeholder="080..." required>
              </div>
            </div>
            <div class="form-row">
              <div class="form-group">
                <label>State</label>
                <input type="text" id="state" placeholder="e.g. Lagos" required>
              </div>
              <div class="form-group">
                <label>Occupation</label>
                <select id="occupation" required>
                  <option value="" disabled selected>Select occupation</option>
                  <option>Student</option>
                  <option>Business Owner</option>
                  <option>Employee</option>
                  <option>Entrepreneur</option>
                  <option>Other</option>
                </select>
              </div>
            </div>
            <div class="form-group">
              <label>Select Course</label>
              <select id="courseSelect" required>
                <option value="" disabled selected>Choose a course</option>
                <option data-price="25000">Learn Stock Market From Scratch to Expert — ₦25,000</option>
                <option data-price="30000">Learn Real Estate Investment — ₦30,000</option>
                <option data-price="30000">Professional Video Editing &amp; AI Content Creation — ₦30,000</option>
                <option data-price="30000">Website Development &amp; Google Business Profile — ₦30,000</option>
                <option data-price="50000">Financial Coach Mentorship — ₦50,000</option>
              </select>
            </div>
            <div class="amount-preview">
              <span class="lbl">Amount to Pay</span>
              <span class="val mono" id="amountPreview">₦0</span>
            </div>
            <button type="submit" class="btn btn-primary btn-block">Continue to Payment →</button>
          </form>
        </div>

        <!-- STEP 2: PAYMENT -->
        <div class="pay-panel" id="panelPay">
          <div class="back-link" id="backToForm">← Back</div>
          <h3 style="color:#fff;font-size:20px;margin-bottom:6px;">Make Your Payment Now</h3>
          <p style="font-size:13.5px;color:rgba(255,255,255,0.55);margin-bottom:24px;">Transfer the exact amount below, then upload your receipt.</p>

          <div class="bank-card">
            <div class="bank-row"><span class="k">Bank</span><span class="v">OPay</span></div>
            <div class="bank-row"><span class="k">Account Name</span><span class="v">Ibrahim Aminu Musa</span></div>
            <div class="bank-row"><span class="k">Account Number</span><span class="v copyable mono" id="acctNum">9168059744 <span class="copy-tag" id="copyTag">Tap to copy</span></span></div>
            <div class="bank-row"><span class="k">Selected Course</span><span class="v" id="payCourse" style="font-size:13px;text-align:right;max-width:60%;">—</span></div>
            <div class="bank-row"><span class="k">Amount to Pay</span><span class="v mono" id="payAmount" style="color:var(--cyan);">₦0</span></div>
          </div>

          <label style="display:block;font-size:13px;font-weight:600;color:rgba(255,255,255,0.75);margin-bottom:10px;font-family:'JetBrains Mono';">Upload Payment Receipt</label>
          <div class="upload-box" id="uploadBox">
            <div class="u-icon">⬆</div>
            <p><strong>Click to upload</strong> or drag and drop<br>Image or PDF file</p>
            <input type="file" id="receiptFile" accept="image/*,.pdf" style="display:none;">
            <div class="file-chosen" id="fileChosen"></div>
          </div>

          <button class="btn btn-primary btn-block" id="continueWhatsapp">Continue to WhatsApp →</button>
        </div>

        <!-- STEP 3: SUCCESS -->
        <div class="success-panel" id="panelSuccess">
          <div class="success-icon">✓</div>
          <h3>Thank you for registering.</h3>
          <p>Your registration details have been prepared successfully. Please attach your payment receipt in WhatsApp and press Send. We will verify your payment and contact you shortly.</p>
          <a href="#home" class="btn btn-ghost" style="color:#fff;">Back to Home</a>
        </div>

      </div>
    </div>
  </div>
</section>

<!-- ============ FOOTER ============ -->
<footer>
  <div class="container">
    <div class="footer-grid">
      <div class="footer-brand">
        <div class="footer-logo"><span class="logo-mark">IA</span>Ibrahim Aminu Mentorship</div>
        <p>Coach Ibrahim Aminu Musa — helping students build wealth through practical, high‑income skills and disciplined investing.</p>
      </div>
      <div class="footer-col">
        <h4>Coach Ibrahim Aminu Musa</h4>
        <ul>
          <li>Stock Market Mentor</li>
          <li>Financial Coach</li>
          <li>Real Estate Mentor</li>
          <li>Website Development Trainer</li>
          <li>Video Editing &amp; AI Trainer</li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Quick Links</h4>
        <ul>
          <li><a href="#about">About</a></li>
          <li><a href="#courses">Courses</a></li>
          <li><a href="#faq">FAQ</a></li>
          <li><a href="#register">Register Now</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>Copyright © 2026 Ibrahim Aminu Mentorship. All rights reserved.</p>
      <div class="footer-socials">
        <a href="https://wa.me/2348087485703" target="_blank">WA</a>
        <a href="#">IG</a>
        <a href="#">FB</a>
      </div>
    </div>
  </div>
</footer>

<!-- ============ FLOATING BUTTONS ============ -->
<a class="whatsapp-float" href="https://wa.me/2348087485703?text=Hello%20Coach%20Ibrahim%20Aminu%20Musa%2C%20I%27d%20like%20to%20know%20more%20about%20your%20courses." target="_blank" aria-label="Chat on WhatsApp">
  <span class="pulse-ring"></span>
  <svg viewBox="0 0 32 32" fill="#fff"><path d="M16.001 3C9.373 3 4 8.373 4 15c0 2.386.7 4.61 1.902 6.472L4 29l7.71-1.874A11.94 11.94 0 0 0 16.001 27C22.628 27 28 21.627 28 15S22.628 3 16.001 3zm0 21.6c-1.98 0-3.822-.55-5.4-1.505l-.386-.23-4.577 1.113 1.14-4.462-.252-.4A9.55 9.55 0 0 1 5.4 15c0-5.85 4.75-10.6 10.6-10.6S26.6 9.15 26.6 15 21.851 24.6 16.001 24.6zm5.79-7.94c-.317-.159-1.878-.927-2.169-1.033-.29-.106-.502-.159-.714.159-.211.317-.82 1.033-1.005 1.245-.185.211-.37.238-.687.079-.317-.159-1.338-.493-2.548-1.571-.942-.84-1.578-1.878-1.763-2.195-.185-.317-.02-.489.139-.647.143-.142.317-.37.476-.556.159-.185.211-.317.317-.529.106-.211.053-.397-.026-.556-.079-.159-.714-1.72-.978-2.355-.258-.62-.52-.536-.714-.546l-.608-.011c-.211 0-.556.079-.847.397-.29.317-1.11 1.084-1.11 2.645s1.137 3.068 1.295 3.28c.159.211 2.238 3.417 5.42 4.792.757.327 1.348.522 1.809.668.76.242 1.452.208 1.999.126.61-.091 1.878-.767 2.143-1.508.265-.741.265-1.376.185-1.508-.079-.132-.29-.211-.608-.37z"/></svg>
</a>
<button class="scrolltop" id="scrollTop" aria-label="Scroll to top">↑</button>

<script>
(function(){
  'use strict';

  /* ---------- LOADING SCREEN ---------- */
  window.addEventListener('load', function(){
    setTimeout(function(){
      document.getElementById('loader').classList.add('hide');
    }, 500);
  });

  /* ---------- STICKY NAV ---------- */
  const header = document.getElementById('siteHeader');
  window.addEventListener('scroll', function(){
    if(window.scrollY > 40){ header.classList.add('scrolled'); } else { header.classList.remove('scrolled'); }
    const st = document.getElementById('scrollTop');
    if(window.scrollY > 600){ st.classList.add('show'); } else { st.classList.remove('show'); }
  });

  /* ---------- MOBILE DRAWER ---------- */
  const burger = document.getElementById('burger');
  const drawer = document.getElementById('mobileDrawer');
  const backdrop = document.getElementById('drawerBackdrop');
  const drawerClose = document.getElementById('drawerClose');
  function openDrawer(){ drawer.classList.add('open'); backdrop.classList.add('show'); }
  function closeDrawer(){ drawer.classList.remove('open'); backdrop.classList.remove('show'); }
  burger.addEventListener('click', openDrawer);
  drawerClose.addEventListener('click', closeDrawer);
  backdrop.addEventListener('click', closeDrawer);
  drawer.querySelectorAll('a').forEach(a => a.addEventListener('click', closeDrawer));

  /* ---------- SCROLL TO TOP ---------- */
  document.getElementById('scrollTop').addEventListener('click', function(){
    window.scrollTo({top:0, behavior:'smooth'});
  });

  /* ---------- SCROLL REVEAL ---------- */
  const revealEls = document.querySelectorAll('.reveal');
  const revealObserver = new IntersectionObserver((entries)=>{
    entries.forEach(entry=>{
      if(entry.isIntersecting){
        entry.target.classList.add('in');
        revealObserver.unobserve(entry.target);
      }
    });
  }, {threshold:0.15});
  revealEls.forEach(el => revealObserver.observe(el));

  /* ---------- ANIMATED COUNTERS ---------- */
  const counters = document.querySelectorAll('.counter');
  const counterObserver = new IntersectionObserver((entries)=>{
    entries.forEach(entry=>{
      if(entry.isIntersecting){
        const el = entry.target;
        const target = parseInt(el.dataset.target, 10);
        let current = 0;
        const duration = 1600;
        const startTime = performance.now();
        function tick(now){
          const progress = Math.min((now - startTime) / duration, 1);
          const eased = 1 - Math.pow(1 - progress, 3);
          current = Math.floor(eased * target);
          el.textContent = current;
          if(progress < 1){ requestAnimationFrame(tick); } else { el.textContent = target; }
        }
        requestAnimationFrame(tick);
        counterObserver.unobserve(el);
      }
    });
  }, {threshold:0.5});
  counters.forEach(el => counterObserver.observe(el));

  /* ---------- FAQ ACCORDION ---------- */
  document.querySelectorAll('.faq-item').forEach(item=>{
    const q = item.querySelector('.faq-q');
    const a = item.querySelector('.faq-a');
    q.addEventListener('click', function(){
      const isOpen = item.classList.contains('open');
      document.querySelectorAll('.faq-item').forEach(other=>{
        other.classList.remove('open');
        other.querySelector('.faq-a').style.maxHeight = null;
      });
      if(!isOpen){
        item.classList.add('open');
        a.style.maxHeight = a.scrollHeight + 'px';
      }
    });
  });

  /* ---------- COURSE CARD "Register" BUTTONS PRE-FILL SELECT ---------- */
  document.querySelectorAll('.course-cta[data-course]').forEach(btn=>{
    btn.addEventListener('click', function(){
      const courseName = this.dataset.course;
      const select = document.getElementById('courseSelect');
      for(let opt of select.options){
        if(opt.text.indexOf(courseName.split(' ').slice(0,3).join(' ')) !== -1 || opt.text.indexOf(courseName) !== -1){
          select.value = opt.value || opt.text;
          select.selectedIndex = opt.index;
          break;
        }
      }
      updateAmount();
    });
  });

  /* ---------- REGISTRATION FLOW ---------- */
  const courseSelect = document.getElementById('courseSelect');
  const amountPreview = document.getElementById('amountPreview');
  const regForm = document.getElementById('regForm');
  const panelForm = document.getElementById('panelForm');
  const panelPay = document.getElementById('panelPay');
  const panelSuccess = document.getElementById('panelSuccess');
  const dot1 = document.getElementById('dot1');
  const dot2 = document.getElementById('dot2');
  const dot3 = document.getElementById('dot3');

  function formatNaira(n){
    return '₦' + Number(n).toLocaleString('en-NG');
  }

  function updateAmount(){
    const opt = courseSelect.options[courseSelect.selectedIndex];
    const price = opt && opt.dataset.price ? opt.dataset.price : 0;
    amountPreview.textContent = formatNaira(price);
  }
  courseSelect.addEventListener('change', updateAmount);

  let regData = {};

  regForm.addEventListener('submit', function(e){
    e.preventDefault();
    const opt = courseSelect.options[courseSelect.selectedIndex];
    regData = {
      fullName: document.getElementById('fullName').value.trim(),
      email: document.getElementById('email').value.trim(),
      phone: document.getElementById('phone').value.trim(),
      state: document.getElementById('state').value.trim(),
      occupation: document.getElementById('occupation').value,
      course: opt.text.split(' — ')[0],
      amount: opt.dataset.price
    };

    // populate payment panel
    document.getElementById('payCourse').textContent = regData.course;
    document.getElementById('payAmount').textContent = formatNaira(regData.amount);

    panelForm.classList.remove('show');
    panelPay.classList.add('show');
    dot1.classList.remove('active');
    dot2.classList.add('active');
    window.scrollTo({top: document.getElementById('register').offsetTop - 100, behavior:'smooth'});
  });

  document.getElementById('backToForm').addEventListener('click', function(){
    panelPay.classList.remove('show');
    panelForm.classList.add('show');
    dot2.classList.remove('active');
    dot1.classList.add('active');
  });

  /* ---------- COPY ACCOUNT NUMBER ---------- */
  document.getElementById('acctNum').addEventListener('click', function(){
    const tag = document.getElementById('copyTag');
    navigator.clipboard.writeText('9168059744').then(function(){
      tag.textContent = 'Copied!';
      setTimeout(()=>{ tag.textContent = 'Tap to copy'; }, 1800);
    }).catch(function(){
      tag.textContent = 'Copy manually';
    });
  });

  /* ---------- FILE UPLOAD ---------- */
  const uploadBox = document.getElementById('uploadBox');
  const receiptFile = document.getElementById('receiptFile');
  const fileChosen = document.getElementById('fileChosen');
  uploadBox.addEventListener('click', ()=> receiptFile.click());
  uploadBox.addEventListener('dragover', function(e){ e.preventDefault(); uploadBox.classList.add('drag'); });
  uploadBox.addEventListener('dragleave', function(){ uploadBox.classList.remove('drag'); });
  uploadBox.addEventListener('drop', function(e){
    e.preventDefault();
    uploadBox.classList.remove('drag');
    if(e.dataTransfer.files.length){
      receiptFile.files = e.dataTransfer.files;
      showFile();
    }
  });
  receiptFile.addEventListener('change', showFile);
  function showFile(){
    if(receiptFile.files.length){
      fileChosen.style.display = 'block';
      fileChosen.textContent = '✓ ' + receiptFile.files[0].name + ' selected';
    }
  }

  /* ---------- CONTINUE TO WHATSAPP ---------- */
  document.getElementById('continueWhatsapp').addEventListener('click', function(){
    const message =
`Hello Coach Ibrahim Aminu Musa,

I have completed my registration.

My details are:

Full Name: ${regData.fullName}
Email: ${regData.email}
Phone Number: ${regData.phone}
State: ${regData.state}
Occupation: ${regData.occupation}
Selected Course: ${regData.course}
Amount: ${formatNaira(regData.amount)}

I have completed my payment. I will attach my payment receipt before sending this message.`;

    const encoded = encodeURIComponent(message);
    const waUrl = `https://wa.me/2348087485703?text=${encoded}`;
    window.open(waUrl, '_blank');

    // show success panel
    panelPay.classList.remove('show');
    panelSuccess.classList.add('show');
    dot2.classList.remove('active');
    dot3.classList.add('active');
  });

})();
</script>
</body>
</html>

