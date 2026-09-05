<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CASE 003 | سرّ الكلمات المبعثرة</title>

<style>
*{
  box-sizing:border-box;
  -webkit-tap-highlight-color:transparent;
}

body{
  margin:0;
  font-family:Tahoma,Arial,sans-serif;
  background:
    radial-gradient(circle at 10% 10%,#dff7ff 0 12%,transparent 30%),
    radial-gradient(circle at 90% 20%,#f4ddff 0 10%,transparent 28%),
    linear-gradient(135deg,#eef9ff,#fff8ed);
  color:#172554;
  min-height:100vh;
  overflow-x:hidden;
}

button{
  font:inherit;
  cursor:pointer;
  border:none;
}

.app{
  max-width:900px;
  margin:auto;
  padding:14px;
}

/* TOP */
.topbar{
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:13px 16px;
  background:rgba(255,255,255,.9);
  border-radius:22px;
  box-shadow:0 8px 25px rgba(30,41,59,.10);
  position:relative;
  z-index:5;
}

.logo{
  font-weight:900;
}

.case-number{
  background:#172554;
  color:white;
  padding:7px 12px;
  border-radius:14px;
  font-weight:900;
}

/* FLOATING ELEMENTS */
.float{
  position:absolute;
  font-size:30px;
  animation:float 3s ease-in-out infinite;
  pointer-events:none;
}

.f1{top:25px;right:7%;}
.f2{top:75px;left:8%;animation-delay:.7s;}
.f3{bottom:25px;right:14%;animation-delay:1.2s;}
.f4{bottom:40px;left:12%;animation-delay:1.8s;}

@keyframes float{
  50%{transform:translateY(-13px) rotate(8deg);}
}

/* HERO */
.hero{
  position:relative;
  overflow:hidden;
  margin-top:15px;
  padding:30px 18px;
  text-align:center;
  background:rgba(255,255,255,.92);
  border:3px solid #d9ecff;
  border-radius:34px;
  box-shadow:0 20px 50px rgba(30,41,59,.12);
  animation:appear .6s ease;
}

.detective{
  display:block;
  font-size:78px;
  animation:bounce 2s ease-in-out infinite;
}

@keyframes bounce{
  50%{transform:translateY(-9px);}
}

.hero h1{
  font-size:clamp(28px,8vw,48px);
  margin:10px 0;
}

.hero h1 span{
  background:linear-gradient(90deg,#2563eb,#9333ea,#ec4899);
  -webkit-background-clip:text;
  color:transparent;
}

.hero p{
  line-height:1.9;
  max-width:650px;
  margin:auto;
}

.start-btn,
.next-btn,
.finish-btn{
  margin-top:18px;
  padding:14px 25px;
  border-radius:18px;
  color:white;
  font-weight:900;
  background:linear-gradient(135deg,#2563eb,#7c3aed);
  box-shadow:0 10px 25px rgba(37,99,235,.25);
  transition:.2s;
}

.start-btn:hover,
.next-btn:hover,
.finish-btn:hover{
  transform:translateY(-3px) scale(1.03);
}

/* GAME */
.hidden{
  display:none!important;
}

.stats{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:9px;
  margin-top:14px;
}

.stat{
  background:white;
  border-radius:18px;
  padding:11px;
  text-align:center;
  box-shadow:0 7px 20px rgba(30,41,59,.08);
  font-weight:900;
}

.stat small{
  display:block;
  color:#64748b;
  margin-bottom:4px;
}

.progress{
  height:13px;
  margin:13px 0;
  background:#dbeafe;
  border-radius:99px;
  overflow:hidden;
}

.progress-bar{
  width:0;
  height:100%;
  background:linear-gradient(90deg,#06b6d4,#6366f1,#ec4899);
  transition:.5s;
}

/* MISSION MENU */
.mission-menu{
  display:flex;
  gap:8px;
  overflow-x:auto;
  padding:3px 0 8px;
}

.mission-pill{
  flex:0 0 auto;
  padding:9px 13px;
  background:white;
  border-radius:15px;
  color:#475569;
  font-weight:900;
}

.mission-pill.active{
  background:#172554;
  color:white;
}

/* CARD */
.card{
  background:rgba(255,255,255,.96);
  border:3px solid #e3eaff;
  border-radius:31px;
  padding:20px 15px;
  text-align:center;
  box-shadow:0 20px 45px rgba(30,41,59,.11);
  animation:appear .45s ease;
}

@keyframes appear{
  from{
    opacity:0;
    transform:translateY(18px) scale(.98);
  }
  to{
    opacity:1;
    transform:none;
  }
}

.file-tag{
  display:inline-block;
  background:#fff0b8;
  color:#854d0e;
  padding:7px 12px;
  border-radius:13px;
  font-weight:900;
}

.card h2{
  font-size:clamp(23px,6vw,35px);
  margin:12px 0 5px;
}

.description{
  color:#475569;
  line-height:1.8;
}

/* TIMER */
.timer{
  max-width:430px;
  margin:14px auto;
}

.timer-number{
  font-size:28px;
  font-weight:900;
}

.timer-line{
  height:10px;
  background:#e2e8f0;
  border-radius:99px;
  overflow:hidden;
}

.timer-bar{
  width:100%;
  height:100%;
  background:#22c55e;
  transition:width 1s linear;
}

.timer-danger{
  animation:shake .35s infinite;
}

@keyframes shake{
  25%{transform:translateX(7px);}
  50%{transform:translateX(-7px);}
  75%{transform:translateX(5px);}
}

/* VISUAL */
.visual{
  min-height:120px;
  display:flex;
  justify-content:center;
  align-items:center;
  gap:10px;
  margin:12px 0;
}

.big-emoji{
  font-size:82px;
  animation:bounce 1.8s ease-in-out infinite;
}

/* LETTERS */
.letters{
  display:flex;
  justify-content:center;
  flex-wrap:wrap;
  gap:10px;
  margin:15px 0;
}

.letter{
  min-width:58px;
  padding:13px 17px;
  border-radius:18px;
  background:#eff6ff;
  border:3px solid #bfdbfe;
  color:#1d4ed8;
  font-size:25px;
  font-weight:900;
  transition:.2s;
}

.letter:hover{
  transform:translateY(-5px) rotate(-2deg);
}

.letter.selected{
  background:#fef3c7;
  border-color:#f59e0b;
  animation:pop .35s;
}

@keyframes pop{
  50%{transform:scale(1.1);}
}

.word-result{
  min-height:40px;
  font-size:20px;
  font-weight:900;
}

/* CHOICES */
.choices{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:11px;
  max-width:600px;
  margin:15px auto;
}

.choice{
  padding:15px 10px;
  border-radius:20px;
  background:#f8fafc;
  border:3px solid #dbeafe;
  font-size:20px;
  font-weight:900;
  transition:.2s;
}

.choice:hover{
  transform:translateY(-4px) rotate(-1deg);
  box-shadow:0 10px 20px rgba(30,41,59,.10);
}

.choice.correct{
  background:#dcfce7;
  border-color:#22c55e;
  animation:pop .45s;
}

.choice.wrong{
  background:#fee2e2;
  border-color:#ef4444;
  animation:shake .4s;
}

/* FEEDBACK */
.feedback{
  min-height:48px;
  font-size:18px;
  font-weight:900;
  margin:8px;
}

.retry-btn{
  padding:11px 18px;
  border-radius:15px;
  background:#f59e0b;
  color:white;
  font-weight:900;
}

.next-btn{
  background:#16a34a;
  margin-top:5px;
}

/* FINISH */
.finish-screen{
  text-align:center;
}

.confetti{
  font-size:40px;
  letter-spacing:7px;
  animation:bounce 1s infinite;
}

.trophy{
  font-size:90px;
  animation:bounce 1.5s infinite;
}

.footer{
  text-align:center;
  color:#64748b;
  font-weight:700;
  padding:20px 5px;
}

@media(max-width:480px){
  .choices{
    grid-template-columns:1fr 1fr;
  }

  .choice{
    font-size:18px;
  }

  .hero{
    padding:25px 12px;
  }
}
</style>
</head>

<body>

<div class="app">

<header class="topbar">
  <div class="logo">🔎 مُحَرِّك اللغة 001</div>
  <div class="case-number">CASE 003</div>
</header>

<!-- START -->
<section id="hero" class="hero">

  <div class="float f1">⭐</div>
  <div class="float f2">🧩</div>
  <div class="float f3">✨</div>
  <div class="float f4">🔍</div>

  <span class="detective">🕵️‍♀️</span>

  <h1>
    سرّ <span>الكلمات المبعثرة</span>
  </h1>

  <p>
    🚨 حدث خلل غامض في <b>مدينة اللغة</b>!
    الكلمات تفرّقت، والحروف اختلطت،
    وهناك خمس مهمات تنتظرك.
    <br>
    هل تستطيع أن تعيد النظام؟
  </p>

  <button class="start-btn" onclick="startGame()">
    ابدأ التحقيق 🔎
  </button>

</section>

<!-- GAME -->
<section id="game" class="hidden">

  <div class="stats">

    <div class="stat">
      <small>النقاط</small>
      <span id="score">0</span> ⭐
    </div>

    <div class="stat">
      <small>المهمة</small>
      <span id="missionNo">1 / 5</span> 🎯
    </div>

    <div class="stat">
      <small>الأدلة</small>
      <span id="clues">0</span> 🔍
    </div>

  </div>

  <div class="progress">
    <div id="progressBar" class="progress-bar"></div>
  </div>

  <div id="missionMenu" class="mission-menu"></div>

  <div id="missionContainer"></div>

</section>

<div class="footer">
  إعداد: الأستاذة شهد سعد عودة 💙
</div>

</div>

<script>

const missions = [

  {
    title:"المهمة 01 — فكّ الكلمة 🔤",
    type:"letters",
    letters:["ر","م","ق"],
    word:"قمر",
    description:"الحروف تفرّقت! اضغط عليها بالترتيب الصحيح لتكوّن كلمة."
  },

  {
    title:"المهمة 02 — الصورة والكلمة 🖼️",
    type:"picture",
    emoji:"🦋",
    letters:["ة","ش","ر","ا","ف"],
    word:"فراشة",
    description:"انظر إلى الصورة، ثم رتّب الحروف لتكتب اسمها."
  },

  {
    title:"المهمة 03 — الحرف المفقود 🔎",
    type:"missing",
    emoji:"📚",
    shown:"كـتـا _",
    correct:"ب",
    choices:["ت","ب","ج","م"],
    description:"هناك حرف اختفى من الكلمة! اكتشفه."
  },

  {
    title:"المهمة 04 — الكلمة المشبوهة 🚨",
    type:"odd",
    emoji:"🏫",
    correct:"مدرسة",
    choices:["مدرسة","مدرصة","مدرشه"],
    description:"هناك كلمة واحدة مكتوبة بطريقة صحيحة… اكتشفها!"
  },

  {
    title:"المهمة 05 — بوابة الجملة 🚪",
    type:"sentence",
    correct:"الطفل",
    choices:["الطفل","المطر","الكرسي"],
    description:"اختر الكلمة التي تجعل الجملة صحيحة."
  }

];

let currentMission=0;
let score=0;
let clues=0;
let timer=null;
let timeLeft=30;
let locked=false;
let selectedLetters=[];


/* START */

function startGame(){

  document.getElementById("hero").classList.add("hidden");
  document.getElementById("game").classList.remove("hidden");

  loadMission(0);
}


/* MENU */

function renderMenu(){

  const menu=document.getElementById("missionMenu");

  menu.innerHTML=missions.map((m,index)=>`

    <button
      class="mission-pill ${index===currentMission?"active":""}"
      onclick="loadMission(${index})">

      مهمة ${String(index+1).padStart(2,"0")}

    </button>

  `).join("");

}


/* LOAD */

function loadMission(index){

  clearInterval(timer);

  currentMission=index;
  locked=false;
  selectedLetters=[];

  document.getElementById("missionNo").textContent=
    `${index+1} / ${missions.length}`;

  document.getElementById("progressBar").style.width=
    `${(index/missions.length)*100}%`;

  renderMenu();

  const m=missions[index];

  let content="";


  /* LETTERS */

  if(m.type==="letters"){

    const shuffled=[...m.letters].sort(()=>Math.random()-.5);

    content=`

      <div class="letters">

        ${shuffled.map(letter=>`

          <button
            class="letter"
            onclick="chooseLetter(this,'${letter}')">

            ${letter}

          </button>

        `).join("")}

      </div>

      <div id="wordResult" class="word-result">
        الكلمة: —
      </div>

      <button class="start-btn"
        onclick="checkLetters()">

        تحقّق 🔐

      </button>

    `;

  }


  /* PICTURE */

  else if(m.type==="picture"){

    const shuffled=[...m.letters].sort(()=>Math.random()-.5);

    content=`

      <div class="visual">
        <div class="big-emoji">${m.emoji}</div>
      </div>

      <div class="letters">

        ${shuffled.map(letter=>`

          <button
            class="letter"
            onclick="chooseLetter(this,'${letter}')">

            ${letter}

          </button>

        `).join("")}

      </div>

      <div id="wordResult" class="word-result">
        الكلمة: —
      </div>

      <button class="start-btn"
        onclick="checkLetters()">

        تحقّق 🔐

      </button>

    `;

  }


  /* MISSING */

  else if(m.type==="missing"){

    content=`

      <div class="visual">
        <div class="big-emoji">${m.emoji}</div>
      </div>

      <div style="font-size:36px;font-weight:900;margin:15px">
        ${m.shown}
      </div>

      <div class="choices">

        ${m.choices.map(choice=>`

          <button
            class="choice"
            onclick="answerChoice(this,'${choice}','${m.correct}')">

            ${choice}

          </button>

        `).join("")}

      </div>

    `;

  }


  /* ODD */

  else if(m.type==="odd"){

    content=`

      <div class="visual">
        <div class="big-emoji">${m.emoji}</div>
      </div>

      <div class="choices">

        ${m.choices.map(choice=>`

          <button
            class="choice"
            onclick="answerChoice(this,'${choice}','${m.correct}')">

            ${choice}

          </button>

        `).join("")}

      </div>

    `;

  }


  /* SENTENCE */

  else if(m.type==="sentence"){

    content=`

      <div class="visual">
        <div class="big-emoji">🚪</div>
      </div>

      <div style="
        font-size:25px;
        font-weight:900;
        line-height:2;
        margin:15px;
      ">

        شربَ ____ اللبنَ. 🥛

      </div>

      <div class="choices">

        ${m.choices.map((choice,index)=>{

          const icons=["👦🏻","🌧️","🪑"];

          return `

            <button
              class="choice"
              onclick="answerChoice(this,'${choice}','${m.correct}')">

              ${icons[index]} ${choice}

            </button>

          `;

        }).join("")}

      </div>

    `;

  }


  document.getElementById("missionContainer").innerHTML=`

    <article class="card">

      <span class="file-tag">
        📁 الملف نشط
      </span>

      <h2>${m.title}</h2>

      <p class="description">
        ${m.description}
      </p>

      <div class="timer">

        <div id="timerNumber" class="timer-number">
          30
        </div>

        <div class="timer-line">
          <div id="timerBar" class="timer-bar"></div>
        </div>

      </div>

      ${content}

      <div id="feedback" class="feedback"></div>

      <div id="actions"></div>

    </article>

  `;

  startTimer();

}


/* TIMER */

function startTimer(){

  timeLeft=30;

  updateTimer();

  timer=setInterval(()=>{

    timeLeft--;

    updateTimer();

    if(timeLeft<=0){

      clearInterval(timer);

      locked=true;

      document.getElementById("feedback").textContent=
        "⏰ انتهى الوقت! لا مشكلة… حاول مرة أخرى.";

      document.getElementById("actions").innerHTML=`

        <button class="retry-btn"
          onclick="retryMission()">

          🔄 إعادة المحاولة

        </button>

      `;

    }

  },1000);

}


function updateTimer(){

  const number=document.getElementById("timerNumber");
  const bar=document.getElementById("timerBar");

  if(!number || !bar)return;

  number.textContent=timeLeft;

  bar.style.width=(timeLeft/30*100)+"%";

  number.classList.toggle(
    "timer-danger",
    timeLeft<=9
  );

}


/* LETTERS */

function chooseLetter(button,letter){

  if(locked)return;

  button.classList.toggle("selected");

  if(button.classList.contains("selected")){

    selectedLetters.push(letter);

  }else{

    const index=selectedLetters.lastIndexOf(letter);

    if(index>-1){
      selectedLetters.splice(index,1);
    }

  }

  document.getElementById("wordResult").textContent=
    "الكلمة: "+(selectedLetters.join("")||"—");

}


function checkLetters(){

  if(locked)return;

  const answer=selectedLetters.join("");

  if(answer===missions[currentMission].word){

    success();

  }else{

    fail();

  }

}


/* NORMAL ANSWERS */

function answerChoice(button,answer,correct){

  if(locked)return;

  if(answer===correct){

    button.classList.add("correct");

    success();

  }else{

    button.classList.add("wrong");

    fail();

  }

}


/* WRONG */

function fail(){

  const card=document.querySelector(".card");

  card.style.animation="none";

  void card.offsetWidth;

  card.style.animation="shake .4s";

  document.getElementById("feedback").textContent=
    "❌ ليست هذه الإجابة… جرّب مرة أخرى! أنت تستطيع 💪";

  document.getElementById("actions").innerHTML=`

    <button class="retry-btn"
      onclick="retryMission()">

      🔄 حاول مرة أخرى

    </button>

  `;

}


/* RETRY */

function retryMission(){

  locked=false;

  document.getElementById("feedback").textContent=
    "💡 ركّز جيدًا… وابحث عن الدليل!";

  document.getElementById("actions").innerHTML="";

  document.querySelectorAll(".choice").forEach(button=>{
    button.classList.remove("wrong");
  });

  document.querySelectorAll(".letter").forEach(button=>{
    button.classList.remove("selected");
  });

  selectedLetters=[];

  const result=document.getElementById("wordResult");

  if(result){
    result.textContent="الكلمة: —";
  }

}


/* SUCCESS */

function success(){

  if(locked)return;

  locked=true;

  clearInterval(timer);

  score+=10;
  clues++;

  document.getElementById("score").textContent=score;
  document.getElementById("clues").textContent=clues;

  document.getElementById("progressBar").style.width=
    `${((currentMission+1)/missions.length)*100}%`;

  document.getElementById("feedback").innerHTML=
    "🎉 أحسنت يا محقق اللغة! تم حل المهمة 🔓";

  if(currentMission<missions.length-1){

    document.getElementById("actions").innerHTML=`

      <button class="next-btn"
        onclick="loadMission(${currentMission+1})">

        المهمة التالية ➜

      </button>

    `;

  }else{

    document.getElementById("actions").innerHTML=`

      <button class="finish-btn"
        onclick="finishGame()">

        🏆 افتح الملف الأخير

      </button>

    `;

  }

}


/* FINISH */

function finishGame(){

  clearInterval(timer);

  document.getElementById("missionContainer").innerHTML=`

    <article class="card finish-screen">

      <div class="confetti">
        🎉 ⭐ 🎊 ⭐ 🎉
      </div>

      <div class="trophy">
        🏆
      </div>

      <h2>
        تم حل CASE 003 بنجاح!
      </h2>

      <p class="description">

        أحسنت يا محقق اللغة الصغير! 💙
        <br><br>

        لقد أعدت النظام إلى مدينة اللغة
        وجمعت <b>${score}</b> نقطة! ⭐

      </p>

      <div style="
        font-size:23px;
        font-weight:900;
        line-height:1.9;
        margin:18px 0;
      ">

        🎁 مكافأة التحقيق:
        <br>
        ⭐ شارة المحقق الماهر ⭐

      </div>

      <p style="
        font-size:21px;
        font-weight:900;
      ">

        لكن… لحظة! 👀
        <br>
        📁 تم اكتشاف ملف جديد…

      </p>

      <div class="file-tag">
        CASE 004 🔒
      </div>

    </article>

  `;

  document.getElementById("missionMenu").innerHTML="";

}

</script>

</body>
</html>
