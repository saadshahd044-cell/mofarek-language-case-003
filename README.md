<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CASE 003 | سرّ الكلمات المبعثرة</title>

<style>
*{
  box-sizing:border-box;
  margin:0;
  padding:0;
}

body{
  font-family:Tahoma,Arial,sans-serif;
  background:linear-gradient(135deg,#eef7ff,#fff7fc);
  color:#172554;
  min-height:100vh;
}

button{
  font-family:inherit;
  cursor:pointer;
}

.app{
  width:min(100%,650px);
  margin:auto;
  padding:15px;
}

.topbar{
  background:white;
  border-radius:22px;
  padding:14px 16px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  box-shadow:0 8px 25px #00000012;
  margin-bottom:15px;
}

.logo{
  font-weight:bold;
  color:#1d4ed8;
}

.case{
  background:#eef2ff;
  padding:7px 12px;
  border-radius:20px;
  font-weight:bold;
}

.hero{
  background:linear-gradient(135deg,#dbeafe,#fce7f3);
  border-radius:30px;
  padding:25px 18px;
  text-align:center;
  position:relative;
  overflow:hidden;
  box-shadow:0 12px 30px #00000015;
}

.floating{
  position:absolute;
  font-size:25px;
  animation:float 3s infinite ease-in-out;
}

.f1{top:15px;right:20px}
.f2{top:65px;left:25px;animation-delay:.5s}
.f3{bottom:20px;right:35px;animation-delay:1s}
.f4{bottom:45px;left:35px;animation-delay:1.5s}

@keyframes float{
  50%{transform:translateY(-10px) rotate(8deg)}
}

.detective{
  font-size:65px;
  animation:bounce 2s infinite;
}

@keyframes bounce{
  50%{transform:translateY(-6px)}
}

h1{
  font-size:30px;
  margin:8px 0;
}

.hero p{
  line-height:1.8;
  font-size:15px;
  color:#334155;
}

.start{
  border:0;
  background:#2563eb;
  color:white;
  padding:14px 25px;
  border-radius:18px;
  font-size:17px;
  font-weight:bold;
  margin-top:18px;
  box-shadow:0 8px 18px #2563eb44;
  transition:.2s;
}

.start:active{
  transform:scale(.95);
}

.stats{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:10px;
  margin:15px 0;
}

.stat{
  background:white;
  border-radius:18px;
  padding:13px 5px;
  text-align:center;
  box-shadow:0 6px 18px #0000000d;
}

.stat strong{
  display:block;
  font-size:21px;
  color:#2563eb;
}

.stat span{
  font-size:12px;
  color:#64748b;
}

.progress-box{
  background:white;
  padding:12px;
  border-radius:18px;
  margin-bottom:15px;
}

.progress{
  height:10px;
  background:#e2e8f0;
  border-radius:20px;
  overflow:hidden;
}

.progress-bar{
  height:100%;
  width:0%;
  background:#2563eb;
  transition:.4s;
}

.game{
  display:none;
}

.mission-menu{
  display:flex;
  gap:7px;
  overflow-x:auto;
  margin-bottom:15px;
}

.mission-btn{
  min-width:65px;
  border:0;
  background:white;
  padding:10px;
  border-radius:15px;
  font-weight:bold;
  color:#64748b;
}

.mission-btn.active{
  background:#2563eb;
  color:white;
}

.card{
  background:white;
  border-radius:28px;
  padding:22px 16px;
  box-shadow:0 10px 30px #00000012;
  text-align:center;
}

.mission-title{
  font-size:21px;
  margin-bottom:10px;
}

.description{
  color:#64748b;
  line-height:1.8;
  margin-bottom:18px;
}

.timer{
  width:80px;
  height:80px;
  border-radius:50%;
  background:#eff6ff;
  border:7px solid #bfdbfe;
  display:flex;
  align-items:center;
  justify-content:center;
  margin:0 auto 18px;
  font-size:25px;
  font-weight:bold;
  color:#2563eb;
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
  animation:pulse .7s infinite;
}

@keyframes pulse{
  50%{transform:scale(1.08)}
}

.letters{
  display:flex;
  justify-content:center;
  gap:10px;
  flex-wrap:wrap;
  margin:20px 0;
}

.letter{
  width:62px;
  height:62px;
  border:0;
  border-radius:20px;
  background:#dbeafe;
  color:#1e40af;
  font-size:27px;
  font-weight:bold;
  box-shadow:0 5px 12px #00000012;
  transition:.2s;
}

.letter:active{
  transform:scale(.9);
}

.letter.selected{
  background:#2563eb;
  color:white;
  transform:translateY(-5px);
}

.answer{
  min-height:65px;
  border:3px dashed #bfdbfe;
  border-radius:20px;
  display:flex;
  align-items:center;
  justify-content:center;
  gap:8px;
  font-size:30px;
  font-weight:bold;
  color:#1e3a8a;
  margin:15px 0;
}

.image-box{
  font-size:75px;
  margin:10px 0 18px;
  animation:float 3s infinite ease-in-out;
}

.choices{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
  margin-top:15px;
}

.choice{
  border:0;
  background:#f1f5f9;
  border-radius:18px;
  padding:15px 10px;
  font-size:18px;
  font-weight:bold;
  color:#334155;
  transition:.2s;
}

.choice:active{
  transform:scale(.95);
}

.choice.correct{
  background:#dcfce7;
  color:#166534;
  animation:correct .5s;
}

.choice.wrong{
  background:#fee2e2;
  color:#991b1b;
  animation:shake .4s;
}

@keyframes correct{
  50%{transform:scale(1.08)}
}

@keyframes shake{
  25%{transform:translateX(7px)}
  50%{transform:translateX(-7px)}
  75%{transform:translateX(5px)}
}

.feedback{
  margin-top:15px;
  font-weight:bold;
  line-height:1.7;
  min-height:30px;
}

.retry{
  display:none;
  border:0;
  background:#f59e0b;
  color:white;
  padding:12px 20px;
  border-radius:16px;
  font-weight:bold;
  margin:12px auto 0;
}

.next{
  display:none;
  border:0;
  background:#16a34a;
  color:white;
  padding:12px 20px;
  border-radius:16px;
  font-weight:bold;
  margin:12px auto 0;
}

.final{
  display:none;
  background:white;
  border-radius:28px;
  padding:30px 18px;
  text-align:center;
  box-shadow:0 10px 30px #00000012;
}

.trophy{
  font-size:75px;
  animation:bounce 1.5s infinite;
}

.final h2{
  margin:10px 0;
  font-size:27px;
}

.badge{
  display:inline-block;
  background:#fef3c7;
  padding:12px 18px;
  border-radius:18px;
  margin:15px 0;
  font-weight:bold;
}

.footer{
  text-align:center;
  margin:20px 0 5px;
  color:#64748b;
  font-size:13px;
}
</style>
</head>

<body>

<div class="app">

  <div class="topbar">
    <div class="logo">🔎 مُحَرِّك اللغة 001</div>
    <div class="case">CASE 003</div>
  </div>

  <section class="hero" id="hero">

    <div class="floating f1">⭐</div>
    <div class="floating f2">🧩</div>
    <div class="floating f3">✨</div>
    <div class="floating f4">🔍</div>

    <div class="detective">🕵️‍♀️</div>

    <h1>سرّ الكلمات المبعثرة</h1>

    <p>
      هناك خلل غامض في مدينة اللغة...
      الكلمات تفرّقت، والحروف اختفت،
      والجمل تحتاج إلى محقق ذكي! 🔎
    </p>

    <button class="start" onclick="startGame()">
      🚀 ابدأ التحقيق
    </button>

  </section>

  <div class="game" id="game">

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

    <div class="progress-box">
      <div class="progress">
        <div class="progress-bar" id="progressBar"></div>
      </div>
    </div>

    <div class="mission-menu" id="missionMenu"></div>

    <div class="card" id="missionCard">

      <div class="mission-title" id="missionTitle"></div>

      <div class="description" id="description"></div>

      <div class="timer" id="timer">30</div>

      <div id="missionContent"></div>

      <div class="feedback" id="feedback"></div>

      <button class="retry" id="retry" onclick="retryMission()">
        🔄 حاول مرة أخرى
      </button>

      <button class="next" id="next" onclick="nextMission()">
        المهمة التالية ➡️
      </button>

    </div>

  </div>

  <div class="final" id="final">

    <div class="trophy">🏆</div>

    <h2>تم حل CASE 003 بنجاح! 🎉</h2>

    <p>
      أحسنت أيها المحقق!
      لقد نجحت في فكّ الكلمات واكتشاف الحروف
      وحلّ الألغاز. 🔎
    </p>

    <div class="badge">
      🏅 محقق الكلمات المبعثرة
    </div>

    <p>
      لكن لحظة... 👀<br>
      النظام اكتشف ملفًا جديدًا...
    </p>

    <h2>CASE 004 // ??? 🔐</h2>

  </div>

  <div class="footer">
    إعداد: الأستاذة شهد سعد عودة 💙
  </div>

</div>

<script>

const missions = [

  {
    title:"المهمة 01 — فكّ الكلمة 🔤",
    type:"letters",
    letters:["م","ج","ن"],
    word:"نجم",
    description:"الحروف تفرّقت! اضغط عليها بالترتيب الصحيح لتكوّن كلمة."
  },

  {
    title:"المهمة 02 — الصورة والكلمة 🖼️",
    type:"lettersImage",
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
    type:"choice",
    emoji:"🏫",
    correct:"مدرسة",
    choices:["مدرسة","مدرصة","مدرشه"],
    description:"هناك كلمة واحدة مكتوبة بطريقة صحيحة… اكتشفها!"
  },

  {
    title:"المهمة 05 — بوابة الجملة 🚪",
    type:"choice",
    correct:"الطفل",
    choices:["الطفل","المطر","الكرسي"],
    description:"اختر الكلمة التي تجعل الجملة صحيحة."
  }

];

let currentMission = 0;
let score = 0;
let clues = 0;
let timerInterval;
let timeLeft = 30;
let selectedLetters = [];

function startGame(){

  document.getElementById("hero").style.display="none";
  document.getElementById("game").style.display="block";

  buildMissionMenu();
  loadMission(0);
}

function buildMissionMenu(){

  const menu=document.getElementById("missionMenu");

  menu.innerHTML="";

  missions.forEach((m,index)=>{

    const btn=document.createElement("button");

    btn.className="mission-btn";

    btn.textContent="م"+(index+1);

    btn.onclick=()=>{

      if(index<=currentMission){
        loadMission(index);
      }

    };

    menu.appendChild(btn);

  });

}

function updateMenu(){

  document.querySelectorAll(".mission-btn")
  .forEach((btn,index)=>{

    btn.classList.toggle(
      "active",
      index===currentMission
    );

  });

}

function loadMission(index){

  clearInterval(timerInterval);

  currentMission=index;
  selectedLetters=[];

  document.getElementById("missionNumber").textContent=index+1;

  document.getElementById("missionTitle").textContent=
    missions[index].title;

  document.getElementById("description").textContent=
    missions[index].description;

  document.getElementById("feedback").textContent="";
  document.getElementById("retry").style.display="none";
  document.getElementById("next").style.display="none";

  const progress=((index)/missions.length)*100;

  document.getElementById("progressBar").style.width=
    progress+"%";

  updateMenu();

  renderMission(missions[index]);

  startTimer();

}

function renderMission(mission){

  const content=document.getElementById("missionContent");

  content.innerHTML="";

  if(mission.type==="letters"){

    const answer=document.createElement("div");

    answer.className="answer";

    answer.id="answer";

    answer.textContent="؟";

    content.appendChild(answer);

    const letters=document.createElement("div");

    letters.className="letters";

    mission.letters.forEach(letter=>{

      const btn=document.createElement("button");

      btn.className="letter";

      btn.textContent=letter;

      btn.onclick=()=>selectLetter(btn,letter,mission.word);

      letters.appendChild(btn);

    });

    content.appendChild(letters);

  }

  else if(mission.type==="lettersImage"){

    const image=document.createElement("div");

    image.className="image-box";

    image.textContent=mission.emoji;

    content.appendChild(image);

    const answer=document.createElement("div");

    answer.className="answer";

    answer.id="answer";

    answer.textContent="؟";

    content.appendChild(answer);

    const letters=document.createElement("div");

    letters.className="letters";

    mission.letters.forEach(letter=>{

      const btn=document.createElement("button");

      btn.className="letter";

      btn.textContent=letter;

      btn.onclick=()=>selectLetter(btn,letter,mission.word);

      letters.appendChild(btn);

    });

    content.appendChild(letters);

  }

  else if(mission.type==="missing"){

    const image=document.createElement("div");

    image.className="image-box";

    image.textContent=mission.emoji;

    content.appendChild(image);

    const word=document.createElement("div");

    word.className="answer";

    word.textContent=mission.shown;

    content.appendChild(word);

    const choices=document.createElement("div");

    choices.className="choices";

    mission.choices.forEach(choice=>{

      const btn=document.createElement("button");

      btn.className="choice";

      btn.textContent=choice;

      btn.onclick=()=>checkChoice(btn,choice,mission.correct);

      choices.appendChild(btn);

    });

    content.appendChild(choices);

  }

  else if(mission.type==="choice"){

    if(currentMission===4){

      const sentence=document.createElement("div");

      sentence.style.fontSize="25px";
      sentence.style.fontWeight="bold";
      sentence.style.lineHeight="2";

      sentence.innerHTML=
        "شربَ ____ اللبنَ. 🥛";

      content.appendChild(sentence);

    }else{

      const image=document.createElement("div");

      image.className="image-box";

      image.textContent=mission.emoji;

      content.appendChild(image);

    }

    const choices=document.createElement("div");

    choices.className="choices";

    mission.choices.forEach(choice=>{

      const btn=document.createElement("button");

      btn.className="choice";

      btn.textContent=choice;

      btn.onclick=()=>checkChoice(btn,choice,mission.correct);

      choices.appendChild(btn);

    });

    content.appendChild(choices);

  }

}

function selectLetter(btn,letter,correctWord){

  if(btn.classList.contains("selected")) return;

  btn.classList.add("selected");

  selectedLetters.push(letter);

  document.getElementById("answer").textContent=
    selectedLetters.join("");

  if(selectedLetters.length===correctWord.length){

    const result=selectedLetters.join("");

    if(result===correctWord){

      correctAnswer();

    }else{

      wrongAnswer();

    }

  }

}

function checkChoice(btn,choice,correct){

  if(choice===correct){

    btn.classList.add("correct");

    correctAnswer();

  }else{

    btn.classList.add("wrong");

    wrongAnswer();

  }

}

function correctAnswer(){

  clearInterval(timerInterval);

  score+=10;
  clues+=1;

  document.getElementById("score").textContent=score;
  document.getElementById("clues").textContent=clues;

  document.getElementById("feedback").textContent=
    "🎉 إجابة صحيحة! أحسنت يا محقق اللغة!";

  document.getElementById("feedback").style.color="#16a34a";

  document.querySelectorAll(".letter,.choice")
  .forEach(btn=>btn.disabled=true);

  if(currentMission===missions.length-1){

    setTimeout(showFinal,700);

  }else{

    document.getElementById("next").style.display="block";

  }

}

function wrongAnswer(){

  document.getElementById("feedback").textContent=
    "❌ ليست الإجابة الصحيحة... ركّز وحاول مرة أخرى!";

  document.getElementById("feedback").style.color="#dc2626";

  document.getElementById("retry").style.display="block";

}

function retryMission(){

  clearInterval(timerInterval);

  selectedLetters=[];

  document.getElementById("feedback").textContent="";

  document.getElementById("retry").style.display="none";

  document.getElementById("next").style.display="none";

  renderMission(missions[currentMission]);

  startTimer();

}

function nextMission(){

  loadMission(currentMission+1);

}

function startTimer(){

  timeLeft=30;

  const timer=document.getElementById("timer");

  timer.textContent=timeLeft;

  timer.className="timer";

  clearInterval(timerInterval);

  timerInterval=setInterval(()=>{

    timeLeft--;

    timer.textContent=timeLeft;

    if(timeLeft<=15){

      timer.classList.add("warning");

    }

    if(timeLeft<=9){

      timer.classList.remove("warning");
      timer.classList.add("danger");

    }

    if(timeLeft<=0){

      clearInterval(timerInterval);

      document.getElementById("feedback").textContent=
        "⏰ انتهى الوقت! خُد نفسًا وحاول مرة أخرى.";

      document.getElementById("feedback").style.color="#dc2626";

      document.getElementById("retry").style.display="block";

    }

  },1000);

}

function showFinal(){

  document.getElementById("game").style.display="none";
  document.getElementById("final").style.display="block";

}

</script>

</body>
</html>
