<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#2563eb">

<title>CASE 003 | سرّ الكلمات المبعثرة</title>

<style>
*{
  box-sizing:border-box;
  margin:0;
  padding:0;
}

:root{
  --blue:#2563eb;
  --dark:#172554;
  --sky:#dbeafe;
  --pink:#fce7f3;
  --yellow:#fef3c7;
  --green:#16a34a;
  --red:#dc2626;
  --orange:#f59e0b;
  --white:#ffffff;
}

body{
  font-family:Tahoma,Arial,sans-serif;
  min-height:100vh;
  background:
    radial-gradient(circle at 10% 10%,#ffffff 0 5%,transparent 6%),
    radial-gradient(circle at 90% 20%,#ffffff 0 4%,transparent 5%),
    linear-gradient(135deg,#dbeafe 0%,#fce7f3 48%,#fef3c7 100%);
  color:var(--dark);
  overflow-x:hidden;
}

button{
  font-family:inherit;
}

.app{
  width:100%;
  max-width:720px;
  margin:auto;
  padding:12px;
}

/* =========================
   TOP BAR
========================= */

.topbar{
  background:rgba(255,255,255,.94);
  border:2px solid rgba(255,255,255,.9);
  border-radius:24px;
  padding:13px 15px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:10px;
  box-shadow:0 10px 30px rgba(30,64,175,.12);
  margin-bottom:12px;
  position:relative;
  z-index:5;
}

.logo{
  color:var(--blue);
  font-weight:900;
  font-size:14px;
}

.case-number{
  background:#eff6ff;
  color:#1e40af;
  border:1px solid #bfdbfe;
  padding:7px 12px;
  border-radius:18px;
  font-weight:900;
  font-size:13px;
}

/* =========================
   HERO
========================= */

.hero{
  position:relative;
  overflow:hidden;
  min-height:470px;
  border-radius:34px;
  background:
    linear-gradient(145deg,
      rgba(255,255,255,.92),
      rgba(219,234,254,.92) 48%,
      rgba(252,231,243,.92));
  box-shadow:0 18px 45px rgba(30,64,175,.16);
  padding:28px 18px;
  text-align:center;
  border:2px solid rgba(255,255,255,.8);
}

.hero::before,
.hero::after{
  content:"";
  position:absolute;
  border-radius:50%;
  pointer-events:none;
}

.hero::before{
  width:170px;
  height:170px;
  background:#bfdbfe;
  opacity:.35;
  top:-80px;
  right:-60px;
}

.hero::after{
  width:150px;
  height:150px;
  background:#fbcfe8;
  opacity:.35;
  bottom:-80px;
  left:-50px;
}

.float-item{
  position:absolute;
  font-size:28px;
  animation:floatAround 3s ease-in-out infinite;
  z-index:2;
}

.star1{top:18px;right:22px}
.star2{top:75px;left:24px;animation-delay:.5s}
.star3{bottom:45px;right:30px;animation-delay:1s}
.star4{bottom:70px;left:28px;animation-delay:1.5s}

@keyframes floatAround{
  0%,100%{
    transform:translateY(0) rotate(0);
  }
  50%{
    transform:translateY(-12px) rotate(8deg);
  }
}

.detective-wrap{
  position:relative;
  width:120px;
  height:120px;
  margin:8px auto 10px;
  display:flex;
  align-items:center;
  justify-content:center;
}

.detective-circle{
  position:absolute;
  inset:0;
  background:linear-gradient(135deg,#bfdbfe,#fbcfe8);
  border-radius:50%;
  box-shadow:0 12px 25px rgba(37,99,235,.15);
  animation:softPulse 2.5s infinite;
}

.detective{
  position:relative;
  font-size:72px;
  z-index:2;
  animation:detectiveBounce 2s infinite;
}

@keyframes detectiveBounce{
  0%,100%{transform:translateY(0)}
  50%{transform:translateY(-8px)}
}

@keyframes softPulse{
  50%{transform:scale(1.05)}
}

.hero h1{
  position:relative;
  z-index:3;
  font-size:31px;
  line-height:1.3;
  margin:8px 0;
}

.hero .subtitle{
  display:inline-block;
  background:#fff;
  color:#2563eb;
  padding:7px 14px;
  border-radius:20px;
  font-weight:bold;
  font-size:13px;
  margin-bottom:12px;
  box-shadow:0 5px 15px rgba(0,0,0,.07);
}

.hero p{
  position:relative;
  z-index:3;
  color:#475569;
  line-height:1.9;
  font-size:15px;
  max-width:560px;
  margin:auto;
}

.start-button{
  position:relative;
  z-index:3;
  border:0;
  background:linear-gradient(135deg,#2563eb,#4f46e5);
  color:white;
  padding:15px 27px;
  border-radius:20px;
  font-size:17px;
  font-weight:900;
  margin-top:20px;
  box-shadow:0 10px 24px rgba(37,99,235,.28);
  transition:.2s;
}

.start-button:active{
  transform:scale(.95);
}

/* =========================
   DECORATIVE FILE
========================= */

.file-card{
  position:relative;
  z-index:3;
  width:min(100%,390px);
  margin:20px auto 0;
  background:white;
  border-radius:18px;
  padding:10px 14px;
  box-shadow:0 7px 20px rgba(0,0,0,.08);
  display:flex;
  align-items:center;
  justify-content:center;
  gap:8px;
  font-size:12px;
  color:#64748b;
  font-weight:bold;
}

/* =========================
   GAME
========================= */

.game{
  display:none;
}

.stats{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:9px;
  margin:12px 0;
}

.stat{
  background:rgba(255,255,255,.95);
  border-radius:19px;
  padding:11px 4px;
  text-align:center;
  box-shadow:0 7px 20px rgba(30,64,175,.09);
  border:1px solid rgba(255,255,255,.8);
}

.stat strong{
  display:block;
  font-size:21px;
  color:var(--blue);
  margin-bottom:3px;
}

.stat span{
  font-size:11px;
  color:#64748b;
  font-weight:bold;
}

/* =========================
   PROGRESS
========================= */

.progress-card{
  background:rgba(255,255,255,.95);
  border-radius:19px;
  padding:12px;
  margin-bottom:12px;
  box-shadow:0 7px 20px rgba(30,64,175,.08);
}

.progress-info{
  display:flex;
  justify-content:space-between;
  font-size:11px;
  color:#64748b;
  font-weight:bold;
  margin-bottom:8px;
}

.progress{
  width:100%;
  height:11px;
  background:#e2e8f0;
  border-radius:20px;
  overflow:hidden;
}

.progress-bar{
  height:100%;
  width:0%;
  background:linear-gradient(90deg,#2563eb,#7c3aed);
  border-radius:20px;
  transition:.5s;
}

/* =========================
   MISSION TABS
========================= */

.mission-menu{
  display:flex;
  gap:7px;
  overflow-x:auto;
  padding:2px 1px 7px;
  scrollbar-width:none;
}

.mission-menu::-webkit-scrollbar{
  display:none;
}

.mission-btn{
  flex:0 0 auto;
  min-width:74px;
  border:0;
  background:rgba(255,255,255,.95);
  color:#64748b;
  padding:9px 11px;
  border-radius:16px;
  font-weight:900;
  font-size:12px;
  box-shadow:0 5px 15px rgba(0,0,0,.06);
}

.mission-btn.active{
  background:linear-gradient(135deg,#2563eb,#4f46e5);
  color:#fff;
}

/* =========================
   MISSION CARD
========================= */

.mission-card{
  position:relative;
  overflow:hidden;
  background:rgba(255,255,255,.97);
  border-radius:31px;
  padding:21px 15px 24px;
  box-shadow:0 14px 35px rgba(30,64,175,.12);
  border:2px solid rgba(255,255,255,.9);
  text-align:center;
}

.mission-card::before{
  content:"";
  position:absolute;
  width:120px;
  height:120px;
  border-radius:50%;
  background:#dbeafe;
  opacity:.3;
  top:-65px;
  right:-50px;
}

.mission-card::after{
  content:"";
  position:absolute;
  width:100px;
  height:100px;
  border-radius:50%;
  background:#fce7f3;
  opacity:.3;
  bottom:-60px;
  left:-40px;
}

.mission-inner{
  position:relative;
  z-index:2;
}

.mission-label{
  display:inline-block;
  background:#eff6ff;
  color:#2563eb;
  border-radius:18px;
  padding:7px 13px;
  font-size:12px;
  font-weight:900;
  margin-bottom:8px;
}

.mission-title{
  font-size:22px;
  font-weight:900;
  margin-bottom:7px;
}

.description{
  color:#64748b;
  font-size:14px;
  line-height:1.8;
  margin-bottom:15px;
}

/* =========================
   EVIDENCE VISUAL
========================= */

.evidence-strip{
  display:flex;
  justify-content:center;
  gap:8px;
  margin:5px 0 13px;
}

.evidence{
  background:#fff;
  border:1px solid #e2e8f0;
  border-radius:13px;
  padding:6px 9px;
  font-size:12px;
  box-shadow:0 4px 10px rgba(0,0,0,.05);
}

.evidence.locked{
  opacity:.45;
}

/* =========================
   TIMER
========================= */

.timer-wrap{
  position:relative;
  width:82px;
  height:82px;
  margin:0 auto 17px;
}

.timer{
  width:82px;
  height:82px;
  border-radius:50%;
  display:flex;
  align-items:center;
  justify-content:center;
  background:#eff6ff;
  border:7px solid #bfdbfe;
  color:#2563eb;
  font-size:25px;
  font-weight:900;
  box-shadow:0 6px 15px rgba(37,99,235,.1);
}

.timer.warning{
  background:#fff7ed;
  border-color:#fed7aa;
  color:#ea580c;
}

.timer.danger{
  background:#fef2f2;
  border-color:#fecaca;
  color:#dc2626;
  animation:timerPulse .7s infinite;
}

@keyframes timerPulse{
  50%{transform:scale(1.08)}
}

/* =========================
   MISSION VISUAL
========================= */

.visual-box{
  width:125px;
  height:125px;
  margin:5px auto 15px;
  border-radius:32px;
  background:linear-gradient(145deg,#eff6ff,#fdf2f8);
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:72px;
  box-shadow:
    inset 0 0 0 2px rgba(255,255,255,.8),
    0 10px 25px rgba(37,99,235,.09);
  animation:visualFloat 3s ease-in-out infinite;
}

@keyframes visualFloat{
  0%,100%{transform:translateY(0)}
  50%{transform:translateY(-6px)}
}

/* =========================
   ANSWER AREA
========================= */

.answer-box{
  min-height:67px;
  display:flex;
  align-items:center;
  justify-content:center;
  gap:7px;
  border:3px dashed #bfdbfe;
  background:#f8fbff;
  border-radius:21px;
  color:#1e3a8a;
  font-size:29px;
  font-weight:900;
  margin:10px auto 16px;
  max-width:420px;
  transition:.25s;
}

.answer-box.success{
  border-color:#86efac;
  background:#f0fdf4;
  color:#15803d;
  transform:scale(1.02);
}

.answer-box.error{
  border-color:#fca5a5;
  background:#fef2f2;
  animation:shake .4s;
}

/* =========================
   LETTER BUTTONS
========================= */

.letters{
  display:flex;
  justify-content:center;
  align-items:center;
  gap:9px;
  flex-wrap:wrap;
  margin:13px 0;
}

.letter{
  width:61px;
  height:61px;
  border:0;
  border-radius:20px;
  background:linear-gradient(145deg,#dbeafe,#eff6ff);
  color:#1e40af;
  font-size:27px;
  font-weight:900;
  box-shadow:0 7px 15px rgba(37,99,235,.1);
  transition:.2s;
}

.letter:active{
  transform:scale(.91);
}

.letter.selected{
  background:linear-gradient(145deg,#2563eb,#4f46e5);
  color:#fff;
  transform:translateY(-5px) rotate(-2deg);
}

.letter.correct{
  background:#dcfce7;
  color:#166534;
}

/* =========================
   CHOICES
========================= */

.choices{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
  max-width:500px;
  margin:13px auto 0;
}

.choice{
  border:2px solid transparent;
  background:#f8fafc;
  color:#334155;
  border-radius:19px;
  padding:14px 9px;
  min-height:58px;
  font-size:17px;
  font-weight:900;
  box-shadow:0 5px 13px rgba(0,0,0,.05);
  transition:.2s;
}

.choice:active{
  transform:scale(.95);
}

.choice.correct{
  background:#dcfce7;
  color:#166534;
  border-color:#86efac;
  animation:correctPop .5s;
}

.choice.wrong{
  background:#fee2e2;
  color:#991b1b;
  border-color:#fca5a5;
  animation:shake .4s;
}

@keyframes correctPop{
  50%{transform:scale(1.08)}
}

@keyframes shake{
  20%{transform:translateX(7px)}
  40%{transform:translateX(-7px)}
  60%{transform:translateX(5px)}
  80%{transform:translateX(-4px)}
}

/* =========================
   SENTENCE
========================= */

.sentence-box{
  background:#fffbeb;
  border:2px solid #fde68a;
  border-radius:23px;
  padding:18px 10px;
  font-size:23px;
  font-weight:900;
  line-height:2;
  margin:10px auto 15px;
  max-width:520px;
}

/* =========================
   FEEDBACK
========================= */

.feedback{
  min-height:38px;
  margin-top:13px;
  font-size:14px;
  font-weight:900;
  line-height:1.8;
}

.feedback.success{
  color:#15803d;
}

.feedback.error{
  color:#dc2626;
}

.feedback.timeout{
  color:#ea580c;
}

/* =========================
   ACTION BUTTONS
========================= */

.action-button{
  display:none;
  border:0;
  color:#fff;
  padding:12px 22px;
  border-radius:17px;
  font-size:15px;
  font-weight:900;
  margin:9px auto 0;
  box-shadow:0 7px 16px rgba(0,0,0,.1);
}

.retry{
  background:linear-gradient(135deg,#f59e0b,#ea580c);
}

.next{
  background:linear-gradient(135deg,#16a34a,#15803d);
}

/* =========================
   FINAL SCREEN
========================= */

.final{
  display:none;
  position:relative;
  overflow:hidden;
  background:rgba(255,255,255,.97);
  border-radius:34px;
  padding:30px 17px 34px;
  text-align:center;
  box-shadow:0 18px 45px rgba(30,64,175,.15);
  border:2px solid #fff;
}

.final::before,
.final::after{
  content:"✨";
  position:absolute;
  font-size:35px;
  animation:floatAround 2.5s infinite;
}

.final::before{
  top:20px;
  right:25px;
}

.final::after{
  bottom:25px;
  left:25px;
  animation-delay:.7s;
}

.confetti{
  font-size:27px;
  letter-spacing:5px;
  margin-bottom:8px;
}

.trophy{
  font-size:82px;
  animation:trophyBounce 1.4s infinite;
}

@keyframes trophyBounce{
  0%,100%{transform:translateY(0) rotate(0)}
  50%{transform:translateY(-10px) rotate(3deg)}
}

.final h2{
  font-size:27px;
  line-height:1.5;
  margin:8px 0;
}

.final p{
  color:#64748b;
  line-height:1.9;
  font-size:14px;
}

.final-score{
  display:inline-flex;
  flex-direction:column;
  background:#eff6ff;
  color:#1d4ed8;
  border-radius:20px;
  padding:10px 22px;
  margin:15px 0;
}

.final-score strong{
  font-size:26px;
}

.final-score span{
  font-size:11px;
  font-weight:bold;
}

.badge{
  width:min(100%,310px);
  margin:10px auto 18px;
  background:linear-gradient(145deg,#fef3c7,#fffbeb);
  border:2px solid #fde68a;
  border-radius:24px;
  padding:16px;
}

.badge-icon{
  font-size:42px;
}

.badge-title{
  font-weight:900;
  margin-top:5px;
}

.next-case{
  margin-top:20px;
  background:#172554;
  color:white;
  border-radius:23px;
  padding:18px 12px;
}

.next-case .lock{
  font-size:35px;
}

.next-case strong{
  display:block;
  margin:6px 0;
  font-size:20px;
}

/* =========================
   FOOTER
========================= */

.footer{
  text-align:center;
  color:#64748b;
  font-size:12px;
  margin:18px 0 4px;
  font-weight:bold;
}

/* =========================
   RESPONSIVE
========================= */

@media(max-width:420px){

  .hero{
    min-height:450px;
    padding:24px 13px;
  }

  .hero h1{
    font-size:27px;
  }

  .detective{
    font-size:64px;
  }

  .mission-title{
    font-size:20px;
  }

  .choices{
    grid-template-columns:1fr 1fr;
  }

  .choice{
    font-size:16px;
  }

  .letter{
    width:58px;
    height:58px;
  }

}
</style>
</head>

<body>

<div class="app">

<!-- TOP -->
<div class="topbar">
  <div class="logo">🔎 مُحَرِّك اللغة 001</div>
  <div class="case-number">CASE 003</div>
</div>

<!-- HERO -->
<section class="hero" id="hero">

  <div class="float-item star1">⭐</div>
  <div class="float-item star2">🧩</div>
  <div class="float-item star3">✨</div>
  <div class="float-item star4">🔍</div>

  <div class="detective-wrap">
    <div class="detective-circle"></div>
    <div class="detective">🕵️‍♀️</div>
  </div>

  <div class="subtitle">📁 ملف القضية الجديد</div>

  <h1>سرّ الكلمات المبعثرة</h1>

  <p>
    هناك خلل غامض في مدينة اللغة...
    الحروف تفرّقت، والكلمات اختبأت،
    وبعض الأدلة اختفت! 🧩
    هل تستطيع حلّ القضية؟
  </p>

  <button class="start-button" onclick="startGame()">
    🚀 ابدأ التحقيق
  </button>

  <div class="file-card">
    📂 CASE 003 &nbsp; | &nbsp; الحالة: مفتوحة 🔓
  </div>

</section>

<!-- GAME -->
<section class="game" id="game">

  <!-- STATS -->
  <div class="stats">

    <div class="stat">
      <strong id="score">0</strong>
      <span>النقاط ⭐</span>
    </div>

    <div class="stat">
      <strong id="missionNumber">1</strong>
      <span>المهمة 🎯</span>
    </div>

    <div class="stat">
      <strong id="clues">0</strong>
      <span>الأدلة 🔎</span>
    </div>

  </div>

  <!-- PROGRESS -->
  <div class="progress-card">

    <div class="progress-info">
      <span>تقدّم التحقيق</span>
      <span id="progressText">0 / 5</span>
    </div>

    <div class="progress">
      <div class="progress-bar" id="progressBar"></div>
    </div>

  </div>

  <!-- MISSIONS -->
  <div class="mission-menu" id="missionMenu"></div>

  <!-- MISSION CARD -->
  <div class="mission-card">

    <div class="mission-inner">

      <div class="mission-label">
        🔎 دليل القضية
      </div>

      <div class="mission-title" id="missionTitle"></div>

      <div class="description" id="description"></div>

      <div class="evidence-strip">
        <div class="evidence">📁 ملف</div>
        <div class="evidence">🧩 لغز</div>
        <div class="evidence locked" id="evidenceStatus">🔒 لم يُحل</div>
      </div>

      <div class="timer-wrap">
        <div class="timer" id="timer">30</div>
      </div>

      <div id="missionContent"></div>

      <div class="feedback" id="feedback"></div>

      <button
        class="action-button retry"
        id="retry"
        onclick="retryMission()">
        🔄 حاول مرة أخرى
      </button>

      <button
        class="action-button next"
        id="next"
        onclick="nextMission()">
        المهمة التالية ➡️
      </button>

    </div>

  </div>

</section>

<!-- FINAL -->
<section class="final" id="final">

  <div class="confetti">
    🎉 ✨ ⭐ ✨ 🎉
  </div>

  <div class="trophy">🏆</div>

  <h2>تم حل CASE 003 بنجاح!</h2>

  <p>
    أحسنت يا محقق اللغة! 🕵️‍♀️<br>
    استطعت فكّ الكلمات، واكتشاف الحروف،
    وحلّ الأدلة والوصول إلى نهاية القضية.
  </p>

  <div class="final-score">
    <strong id="finalScore">50</strong>
    <span>نقطة تحقيق ⭐</span>
  </div>

  <div class="badge">
    <div class="badge-icon">🏅</div>
    <div class="badge-title">
      محقق الكلمات المبعثرة
    </div>
  </div>

  <p>
    لكن... لحظة واحدة! 👀<br>
    يبدو أن النظام اكتشف ملفًا جديدًا...
  </p>

  <div class="next-case">
    <div class="lock">🔐</div>
    <strong>CASE 004</strong>
    <span>الملف التالي مغلق حاليًا...</span>
  </div>

  <div class="confetti" style="margin-top:20px;">
    🧩 🔍 ⭐ 📁 ✨
  </div>

</section>

<div class="footer">
  إعداد: الأستاذة شهد سعد عودة 💙
</div>

</div>

<script>

/* =====================================================
   CASE 003 DATA
===================================================== */

const missions = [

  /* -----------------------------------------------
     MISSION 01
     التعديل الوحيد: نجم بدل قمر
  ------------------------------------------------ */

  {
    title:"المهمة 01 — فكّ الكلمة 🔤",
    type:"letters",
    letters:["م","ن","ج"],
    word:"نجم",
    description:"الحروف تفرّقت! اضغط عليها بالترتيب الصحيح لتكوّن كلمة."
  },

  /* -----------------------------------------------
     MISSION 02
  ------------------------------------------------ */

  {
    title:"المهمة 02 — الصورة والكلمة 🖼️",
    type:"lettersImage",
    emoji:"🦋",
    letters:["ة","ش","ر","ا","ف"],
    word:"فراشة",
    description:"انظر إلى الصورة، ثم رتّب الحروف لتكتب اسمها."
  },

  /* -----------------------------------------------
     MISSION 03
  ------------------------------------------------ */

  {
    title:"المهمة 03 — الحرف المفقود 🔎",
    type:"missing",
    emoji:"📚",
    shown:"كـتـا _",
    correct:"ب",
    choices:["ت","ب","ج","م"],
    description:"هناك حرف اختفى من الكلمة! اكتشفه."
  },

  /* -----------------------------------------------
     MISSION 04
  ------------------------------------------------ */

  {
    title:"المهمة 04 — الكلمة المشبوهة 🚨",
    type:"choice",
    emoji:"🏫",
    correct:"مدرسة",
    choices:["مدرسة","مدرصة","مدرشه"],
    description:"هناك كلمة واحدة مكتوبة بطريقة صحيحة… اكتشفها!"
  },

  /* -----------------------------------------------
     MISSION 05
  ------------------------------------------------ */

  {
    title:"المهمة 05 — بوابة الجملة 🚪",
    type:"choice",
    correct:"الطفل",
    choices:["الطفل","المطر","الكرسي"],
    description:"اختر الكلمة التي تجعل الجملة صحيحة."
  }

];

/* =====================================================
   GAME VARIABLES
===================================================== */

let currentMission = 0;
let score = 0;
let clues = 0;
let selectedLetters = [];
let timerInterval = null;
let timeLeft = 30;
let gameStarted = false;

/* =====================================================
   START GAME
===================================================== */

function startGame(){

  gameStarted = true;

  document.getElementById("hero").style.display = "none";
  document.getElementById("game").style.display = "block";
  document.getElementById("final").style.display = "none";

  score = 0;
  clues = 0;
  currentMission = 0;

  document.getElementById("score").textContent = "0";
  document.getElementById("clues").textContent = "0";

  buildMissionMenu();
  loadMission(0);

  window.scrollTo({
    top:0,
    behavior:"smooth"
  });
}

/* =====================================================
   BUILD MISSION MENU
===================================================== */

function buildMissionMenu(){

  const menu = document.getElementById("missionMenu");

  menu.innerHTML = "";

  missions.forEach((mission,index)=>{

    const button = document.createElement("button");

    button.className = "mission-btn";

    button.textContent = "مهمة " + (index + 1);

    button.onclick = function(){

      /*
        يسمح فقط بالعودة للمهمة الحالية
        أو المهام التي تم فتحها.
      */

      if(index <= currentMission){
        loadMission(index);
      }

    };

    menu.appendChild(button);

  });

}

/* =====================================================
   UPDATE MISSION MENU
===================================================== */

function updateMissionMenu(){

  document
    .querySelectorAll(".mission-btn")
    .forEach((button,index)=>{

      button.classList.toggle(
        "active",
        index === currentMission
      );

    });

}

/* =====================================================
   LOAD MISSION
===================================================== */

function loadMission(index){

  clearInterval(timerInterval);

  currentMission = index;
  selectedLetters = [];

  document.getElementById("missionNumber").textContent =
    index + 1;

  document.getElementById("progressText").textContent =
    index + " / " + missions.length;

  document.getElementById("progressBar").style.width =
    ((index) / missions.length * 100) + "%";

  document.getElementById("missionTitle").textContent =
    missions[index].title;

  document.getElementById("description").textContent =
    missions[index].description;

  document.getElementById("feedback").textContent = "";
  document.getElementById("feedback").className = "feedback";

  document.getElementById("retry").style.display = "none";
  document.getElementById("next").style.display = "none";

  document.getElementById("evidenceStatus").textContent =
    "🔒 لم يُحل";

  updateMissionMenu();

  renderMission(missions[index]);

  startTimer();

  window.scrollTo({
    top:0,
    behavior:"smooth"
  });
}

/* =====================================================
   RENDER MISSION
===================================================== */

function renderMission(mission){

  const content =
    document.getElementById("missionContent");

  content.innerHTML = "";

  /* -----------------------------------------------
     LETTER MISSION
  ------------------------------------------------ */

  if(mission.type === "letters"){

    const visual = document.createElement("div");

    visual.className = "visual-box";
    visual.textContent = "🧩";

    content.appendChild(visual);

    const answer = document.createElement("div");

    answer.className = "answer-box";
    answer.id = "answer";
    answer.textContent = "؟";

    content.appendChild(answer);

    createLetterButtons(
      content,
      mission
    );

  }

  /* -----------------------------------------------
     IMAGE + LETTERS
  ------------------------------------------------ */

  else if(mission.type === "lettersImage"){

    const visual = document.createElement("div");

    visual.className = "visual-box";
    visual.textContent = mission.emoji;

    content.appendChild(visual);

    const answer = document.createElement("div");

    answer.className = "answer-box";
    answer.id = "answer";
    answer.textContent = "؟";

    content.appendChild(answer);

    createLetterButtons(
      content,
      mission
    );

  }

  /* -----------------------------------------------
     MISSING LETTER
  ------------------------------------------------ */

  else if(mission.type === "missing"){

    const visual = document.createElement("div");

    visual.className = "visual-box";
    visual.textContent = mission.emoji;

    content.appendChild(visual);

    const word = document.createElement("div");

    word.className = "answer-box";
    word.textContent = mission.shown;

    content.appendChild(word);

    createChoiceButtons(
      content,
      mission
    );

  }

  /* -----------------------------------------------
     CHOICE
  ------------------------------------------------ */

  else if(mission.type === "choice"){

    if(currentMission === 4){

      const sentence = document.createElement("div");

      sentence.className = "sentence-box";

      sentence.textContent =
        "شربَ ____ اللبنَ. 🥛";

      content.appendChild(sentence);

    }else{

      const visual = document.createElement("div");

      visual.className = "visual-box";
      visual.textContent = mission.emoji;

      content.appendChild(visual);

    }

    createChoiceButtons(
      content,
      mission
    );

  }

}

/* =====================================================
   CREATE LETTER BUTTONS
===================================================== */

function createLetterButtons(content,mission){

  const lettersBox =
    document.createElement("div");

  lettersBox.className = "letters";

  mission.letters.forEach(letter=>{

    const button =
      document.createElement("button");

    button.className = "letter";

    button.textContent = letter;

    button.onclick = function(){

      selectLetter(
        button,
        letter,
        mission.word
      );

    };

    lettersBox.appendChild(button);

  });

  content.appendChild(lettersBox);

}

/* =====================================================
   CREATE CHOICE BUTTONS
===================================================== */

function createChoiceButtons(content,mission){

  const choicesBox =
    document.createElement("div");

  choicesBox.className = "choices";

  mission.choices.forEach(choice=>{

    const button =
      document.createElement("button");

    button.className = "choice";

    button.textContent = choice;

    button.onclick = function(){

      checkChoice(
        button,
        choice,
        mission.correct
      );

    };

    choicesBox.appendChild(button);

  });

  content.appendChild(choicesBox);

}

/* =====================================================
   SELECT LETTER
===================================================== */

function selectLetter(
  button,
  letter,
  correctWord
){

  if(
    button.classList.contains("selected") ||
    button.disabled
  ){
    return;
  }

  button.classList.add("selected");

  selectedLetters.push(letter);

  const answer =
    document.getElementById("answer");

  answer.textContent =
    selectedLetters.join("");

  if(
    selectedLetters.length ===
    correctWord.length
  ){

    const result =
      selectedLetters.join("");

    if(result === correctWord){

      answer.classList.add("success");

      correctAnswer();

    }else{

      answer.classList.add("error");

      wrongAnswer();

    }

  }

}

/* =====================================================
   CHECK CHOICE
===================================================== */

function checkChoice(
  button,
  choice,
  correct
){

  if(button.disabled){
    return;
  }

  if(choice === correct){

    button.classList.add("correct");

    correctAnswer();

  }else{

    button.classList.add("wrong");

    wrongAnswer();

  }

}

/* =====================================================
   CORRECT ANSWER
===================================================== */

function correctAnswer(){

  clearInterval(timerInterval);

  score += 10;
  clues += 1;

  document.getElementById("score").textContent =
    score;

  document.getElementById("clues").textContent =
    clues;

  const feedback =
    document.getElementById("feedback");

  feedback.textContent =
    "🎉 إجابة صحيحة! أحسنت يا محقق اللغة!";

  feedback.className =
    "feedback success";

  document.getElementById("evidenceStatus").textContent =
    "🔓 تم اكتشاف الدليل!";

  /*
    تعطيل الاختيارات بعد الإجابة الصحيحة
  */

  document
    .querySelectorAll(".letter,.choice")
    .forEach(button=>{
      button.disabled = true;
    });

  /*
    احتفال بصري بسيط
  */

  createMiniConfetti();

  if(currentMission === missions.length - 1){

    setTimeout(
      showFinal,
      900
    );

  }else{

    document.getElementById("next").style.display =
      "block";

  }

}

/* =====================================================
   WRONG ANSWER
===================================================== */

function wrongAnswer(){

  const feedback =
    document.getElementById("feedback");

  feedback.textContent =
    "❌ ليست الإجابة الصحيحة... ركّز وحاول مرة أخرى!";

  feedback.className =
    "feedback error";

  document.getElementById("retry").style.display =
    "block";

}

/* =====================================================
   RETRY
===================================================== */

function retryMission(){

  clearInterval(timerInterval);

  selectedLetters = [];

  document.getElementById("feedback").textContent = "";
  document.getElementById("feedback").className =
    "feedback";

  document.getElementById("retry").style.display =
    "none";

  document.getElementById("next").style.display =
    "none";

  document.getElementById("evidenceStatus").textContent =
    "🔒 لم يُحل";

  renderMission(
    missions[currentMission]
  );

  startTimer();

}

/* =====================================================
   NEXT MISSION
===================================================== */

function nextMission(){

  if(
    currentMission <
    missions.length - 1
  ){

    loadMission(
      currentMission + 1
    );

  }

}

/* =====================================================
   TIMER
===================================================== */

function startTimer(){

  clearInterval(timerInterval);

  timeLeft = 30;

  const timer =
    document.getElementById("timer");

  timer.textContent = timeLeft;

  timer.className = "timer";

  timerInterval =
    setInterval(()=>{

      timeLeft--;

      timer.textContent =
        timeLeft;

      if(timeLeft <= 15){

        timer.classList.add(
          "warning"
        );

      }

      if(timeLeft <= 9){

        timer.classList.remove(
          "warning"
        );

        timer.classList.add(
          "danger"
        );

      }

      if(timeLeft <= 0){

        clearInterval(
          timerInterval
        );

        timeExpired();

      }

    },1000);

}

/* =====================================================
   TIME EXPIRED
===================================================== */

function timeExpired(){

  const feedback =
    document.getElementById("feedback");

  feedback.textContent =
    "⏰ انتهى الوقت! خُد نفسًا وحاول مرة أخرى.";

  feedback.className =
    "feedback timeout";

  document.getElementById("retry").style.display =
    "block";

  /*
    منع الضغط بعد انتهاء الوقت
  */

  document
    .querySelectorAll(".letter,.choice")
    .forEach(button=>{
      button.disabled = true;
    });

}

/* =====================================================
   FINAL SCREEN
===================================================== */

function showFinal(){

  clearInterval(timerInterval);

  document.getElementById("game").style.display =
    "none";

  document.getElementById("final").style.display =
    "block";

  document.getElementById("finalScore").textContent =
    score;

  document.getElementById("progressBar").style.width =
    "100%";

  createFinalConfetti();

  window.scrollTo({
    top:0,
    behavior:"smooth"
  });

}

/* =====================================================
   MINI CONFETTI
===================================================== */

function createMiniConfetti(){

  const symbols =
    ["✨","⭐","💙","🧩"];

  for(let i=0;i<8;i++){

    const item =
      document.createElement("div");

    item.textContent =
      symbols[
        Math.floor(
          Math.random()*symbols.length
        )
      ];

    item.style.position =
      "fixed";

    item.style.left =
      (30 + Math.random()*40) + "%";

    item.style.top =
      "45%";

    item.style.fontSize =
      "22px";

    item.style.zIndex =
      "9999";

    item.style.pointerEvents =
      "none";

    document.body.appendChild(item);

    const x =
      (Math.random()-.5)*180;

    const y =
      -80 - Math.random()*160;

    item.animate(
      [
        {
          transform:"translate(0,0) scale(1)",
          opacity:1
        },
        {
          transform:
            `translate(${x}px,${y}px) scale(.4)`,
          opacity:0
        }
      ],
      {
        duration:800,
        easing:"ease-out"
      }
    );

    setTimeout(()=>{
      item.remove();
    },850);

  }

}

/* =====================================================
   FINAL CONFETTI
===================================================== */

function createFinalConfetti(){

  const symbols =
    ["🎉","⭐","✨","💙","🧩","🔎"];

  for(let i=0;i<28;i++){

    const item =
      document.createElement("div");

    item.textContent =
      symbols[
        Math.floor(
          Math.random()*symbols.length
        )
      ];

    item.style.position =
      "fixed";

    item.style.left =
      Math.random()*100 + "%";

    item.style.top =
      "-30px";

    item.style.fontSize =
      (18 + Math.random()*18) + "px";

    item.style.zIndex =
      "9999";

    item.style.pointerEvents =
      "none";

    document.body.appendChild(item);

    const x =
      (Math.random()-.5)*160;

    const y =
      500 + Math.random()*350;

    const rotate =
      Math.random()*720 - 360;

    item.animate(
      [
        {
          transform:"translate(0,0) rotate(0)",
          opacity:1
        },
        {
          transform:
            `translate(${x}px,${y}px) rotate(${rotate}deg)`,
          opacity:0
        }
      ],
      {
        duration:
          1800 + Math.random()*1000,
        easing:"ease-out"
      }
    );

    setTimeout(()=>{
      item.remove();
    },3000);

  }

}

</script>

</body>
</html>
