<!doctype html>
<html lang="ar" dir="rtl">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1">
<title>CASE 003 | سرّ الكلمات المبعثرة</title>

<style>
*{box-sizing:border-box}

body{
margin:0;
font-family:Tahoma,Arial,sans-serif;
background:linear-gradient(145deg,#eaf6ff,#fff4fb 55%,#fff8d9);
color:#25324a;
}

button{
font:inherit;
border:0;
cursor:pointer;
}

.app{
min-height:100vh;
padding:12px 11px 30px;
}

.top{
max-width:760px;
margin:auto;
display:flex;
justify-content:space-between;
align-items:center;
background:#ffffffdc;
border:2px solid #dbe7f5;
border-radius:22px;
padding:10px 13px;
box-shadow:0 8px 25px #63799c20;
position:sticky;
top:8px;
z-index:9;
}

.logo{
font-weight:900;
color:#354783;
}

.badge{
background:#7055c9;
color:white;
padding:7px 12px;
border-radius:14px;
font-weight:900;
}

.hero,.screen,.stats,.progress,.missions{
max-width:760px;
margin-left:auto;
margin-right:auto;
}

.hero{
margin-top:15px;
background:linear-gradient(135deg,#7359c9,#3978c8);
color:#fff;
border-radius:30px;
padding:27px 17px;
text-align:center;
box-shadow:0 15px 35px #536ab83b;
overflow:hidden;
}

.hero .detective{
font-size:58px;
}

.hero h1{
font-size:clamp(32px,9vw,55px);
margin:5px 0 9px;
}

.hero p{
line-height:1.9;
margin:0 auto 15px;
max-width:600px;
}

.start{
background:#ffd44f;
color:#4c3a00;
padding:13px 27px;
border-radius:17px;
font-weight:900;
font-size:19px;
box-shadow:0 5px 0 #c8a22b;
}

.start:active{
transform:translateY(4px);
box-shadow:0 1px 0 #c8a22b;
}

.stats{
display:flex;
gap:8px;
margin-top:12px;
}

.stat{
flex:1;
background:white;
border:2px solid #e1e9f5;
border-radius:18px;
text-align:center;
padding:8px;
font-size:13px;
font-weight:800;
}

.stat b{
display:block;
font-size:21px;
color:#5b59bd;
}

.progress{
margin-top:12px;
height:11px;
background:#dfe7f3;
border-radius:20px;
overflow:hidden;
}

.fill{
height:100%;
width:0;
background:linear-gradient(90deg,#ffbc43,#685bd0);
transition:.35s;
}

.missions{
display:grid;
grid-template-columns:repeat(2,1fr);
gap:9px;
margin-top:13px;
}

.mission{
background:#fff;
border:2px solid #e0e8f4;
border-radius:18px;
padding:12px;
text-align:center;
font-weight:900;
}

.mission span{
font-size:27px;
display:block;
}

.mission.done{
background:#e9ffef;
border-color:#7bd18c;
}

.screen{
margin-top:15px;
background:#fff;
border:2px solid #e4ebf5;
border-radius:28px;
padding:18px;
box-shadow:0 12px 30px #53617d18;
}

.screen h2{
text-align:center;
color:#514795;
margin:4px 0 7px;
font-size:25px;
}

.instruction{
text-align:center;
color:#637087;
line-height:1.8;
margin-bottom:14px;
}

.timerWrap{
display:flex;
align-items:center;
justify-content:center;
gap:8px;
margin:4px auto 14px;
}

.timer{
width:67px;
height:67px;
border-radius:50%;
display:grid;
place-items:center;
background:#fff;
border:7px solid #6a61c9;
color:#4d478d;
font-weight:900;
font-size:18px;
box-shadow:0 4px 15px #6a61c92b;
}

.timer.warn{
border-color:#e9a52d;
color:#9a6700;
}

.timer.danger{
border-color:#df5b5b;
color:#b63e3e;
animation:shake .35s infinite alternate;
}

@keyframes shake{
to{transform:translateX(2px)}
}

.game{
background:#f7faff;
border-radius:23px;
padding:17px;
}

.letters{
display:flex;
justify-content:center;
gap:9px;
flex-wrap:wrap;
margin:12px 0;
}

.letter{
width:61px;
height:61px;
border-radius:16px;
background:#ffe39a;
border:3px solid #f1c650;
font-size:27px;
font-weight:900;
box-shadow:0 4px 0 #d4af45;
transition:.18s;
}

.letter:hover{
transform:translateY(-3px) rotate(-2deg);
}

.letter:disabled{
opacity:.45;
transform:scale(.94);
}

.slots{
display:flex;
direction:rtl;
justify-content:center;
gap:8px;
min-height:64px;
margin:15px 0;
}

.slot{
width:61px;
height:61px;
border:3px dashed #b8c5d9;
border-radius:15px;
background:#fff;
display:grid;
place-items:center;
font-size:27px;
font-weight:900;
}

.picture{
font-size:76px;
text-align:center;
background:#dff5ff;
border-radius:20px;
padding:13px;
margin-bottom:13px;
letter-spacing:7px;
}

.wordMissing{
font-size:39px;
text-align:center;
font-weight:900;
background:#fff4d7;
border-radius:18px;
padding:14px;
margin:10px 0 15px;
letter-spacing:4px;
}

.choices{
display:grid;
grid-template-columns:repeat(2,1fr);
gap:10px;
}

.choice{
background:#fff;
border:3px solid #dce5f1;
border-radius:17px;
padding:14px;
font-size:23px;
font-weight:900;
transition:.18s;
position:relative;
overflow:hidden;
}

.choice:hover{
transform:translateY(-5px) rotate(-1deg);
box-shadow:0 9px 18px #52617d22;
}

.choice:active{
transform:scale(.94);
}

.choice.pop{
animation:pop .35s ease;
}

@keyframes pop{
0%{transform:scale(.9)}
70%{transform:scale(1.08)}
100%{transform:scale(1)}
}

.choice.selected{
border-color:#6b60cf;
background:#eeebff;
}

.suspect:before{
content:'🚨';
position:absolute;
left:9px;
top:7px;
font-size:18px;
}

.sentence{
font-size:25px;
font-weight:900;
background:#fff;
border-radius:19px;
padding:18px;
text-align:center;
line-height:2;
margin-bottom:14px;
}

.blank{
display:inline-block;
min-width:90px;
border-bottom:4px dashed #6b60cf;
color:#6b60cf;
}

.screen.correctFlash{
animation:correctFlash .55s ease;
}

@keyframes correctFlash{
0%{box-shadow:0 0 0 0 #45ba6244}
50%{box-shadow:0 0 0 12px #45ba6200}
100%{box-shadow:none}
}

.screen.wrongShake{
animation:wrongShake .38s ease;
}

@keyframes wrongShake{
0%,100%{transform:translateX(0)}
25%{transform:translateX(-8px)}
50%{transform:translateX(8px)}
75%{transform:translateX(-5px)}
}

.feedback{
text-align:center;
min-height:30px;
margin:12px 0 0;
font-weight:900;
}

.success{
color:#2c9a4d;
}

.wrong{
color:#d04b4b;
}

.actions{
text-align:center;
margin-top:13px;
}

.check,.next{
background:#45ba62;
color:#fff;
padding:12px 27px;
border-radius:16px;
font-weight:900;
box-shadow:0 4px 0 #32934c;
}

.hint{
background:#fff0a6;
color:#5e4b00;
padding:11px 17px;
border-radius:15px;
font-weight:900;
margin-right:6px;
}

.hidden{
display:none!important;
}

.end{
max-width:760px;
margin:15px auto;
background:linear-gradient(135deg,#263d78,#5e55b5);
color:#fff;
border-radius:28px;
padding:28px 18px;
text-align:center;
}

.end .cup{
font-size:75px;
}

.end h2{
font-size:34px;
margin:7px;
}

.end p{
line-height:2;
font-size:19px;
}

.secret{
background:#f0efff;
border-radius:20px;
padding:17px;
color:#3f3a76;
font-weight:900;
}

.again{
margin-top:15px;
background:#ffd44f;
color:#493800;
padding:12px 24px;
border-radius:15px;
font-weight:900;
}

footer{
text-align:center;
color:#718096;
font-weight:800;
margin-top:18px;
}

@media(max-width:420px){

.logo{
font-size:13px;
}

.missions{
font-size:13px;
}

.letter,.slot{
width:53px;
height:53px;
}

.choices{
grid-template-columns:1fr;
}

.picture{
font-size:62px;
}

.sentence{
font-size:21px;
}

}
</style>
</head>

<body>

<div class="app">

<div class="top">
<div class="logo">🔎 مُحَرِّك اللغة 001</div>
<div class="badge">CASE 003</div>
</div>

<section class="hero" id="hero">

<div class="detective">🕵️‍♂️</div>

<h1>سرّ الكلمات المبعثرة</h1>

<p>
حدث خلل غامض في مدينة اللغة!
الكلمات تبعثرت، وبعض الحروف اختفت.
مهمتك أن تعيد النظام وتجمع الأدلة.
</p>

<button class="start" onclick="startCase()">
ابدأ التحقيق 🔍
</button>

</section>

<div class="stats">

<div class="stat">
⭐ النقاط
<b id="score">0</b>
</div>

<div class="stat">
🏅 المهمة
<b id="level">0/5</b>
</div>

<div class="stat">
🔎 الأدلة
<b id="clues">0/5</b>
</div>

</div>

<div class="progress">
<div class="fill" id="fill"></div>
</div>

<div class="missions" id="missions">

<div class="mission">
<span>🔤</span>
فكّ الكلمة
</div>

<div class="mission">
<span>🖼️</span>
الصورة والكلمة
</div>

<div class="mission">
<span>🕳️</span>
الحرف المفقود
</div>

<div class="mission">
<span>🚨</span>
الكلمة المشبوهة
</div>

<div class="mission">
<span>🚪</span>
بوابة الجملة
</div>

<div class="mission">
<span>🔐</span>
الملف السري
</div>

</div>

<section class="screen hidden" id="screen"></section>

<section class="end hidden" id="end"></section>

<footer>
إعداد: الأستاذة شهد سعد عودة 💙
</footer>

</div>

<script>

const data=[

{
title:'المهمة 01 — فكّ الكلمة 🔤',
type:'letters',
letters:['ب','ا','ب'],
word:'باب',
text:'رتّب الحروف لتكوّن الكلمة الصحيحة.'
},

{
title:'المهمة 02 — الصورة والكلمة 🖼️',
type:'picture',
emoji:'🐟',
letters:['ة','ك','م','س'],
word:'سمكة',
text:'انظر إلى الصورة، ثم رتّب الحروف لتكتب اسمها.'
},

{
title:'المهمة 03 — الحرف المفقود 🕳️',
type:'missing',
emoji:'📚',
shown:'كـتـا _',
correct:'ب',
choices:['ت','ب','ج','م'],
text:'🔎 اكتشف الحرف المفقود!'
},

{
title:'المهمة 04 — الكلمة المشبوهة 🚨',
type:'odd',
choices:['قلم','كلم','قمل'],
correct:'قلم',
text:'🚨 هناك كلمة واحدة سليمة! اكتشفها.'
},

{
title:'المهمة 05 — بوابة الجملة 🚪',
type:'sentence',
choices:['أحمد','الكتاب','الشجرة'],
correct:'أحمد',
text:'أكمل الجملة وافتح البوابة!'
}

];

let i=0;
let score=0;
let clues=0;
let answer=[];
let selected=null;
let time=30;
let timer=null;

function startCase(){

document.getElementById('hero').classList.add('hidden');

document.getElementById('missions').classList.add('hidden');

document.getElementById('screen').classList.remove('hidden');

render();

}

function render(){

clearInterval(timer);

answer=[];
selected=null;
time=30;

const m=data[i];
const s=document.getElementById('screen');

let body='';

if(m.type==='letters'||m.type==='picture'){

body=
(m.type==='picture'
?`<div class="picture">${m.emoji}</div>`
:'')
+
`
<div class="letters">

${shuffle([...m.letters]).map(x=>
`
<button class="letter"
onclick="pick('${x}',this)">
${x}
</button>
`
).join('')}

</div>

<div class="slots">

${m.letters.map(()=>
'<div class="slot"></div>'
).join('')}

</div>
`;

}

if(m.type==='missing'){

body=`

<div class="picture">
${m.emoji}
</div>

<div class="wordMissing">
${m.shown}
</div>

<div class="choices">

${m.choices.map(x=>
`
<button class="choice"
onclick="choose('${x}',this)">
${x}
</button>
`
).join('')}

</div>

`;

}

if(m.type==='odd'){

body=`

<div class="choices">

${m.choices.map(x=>
`
<button class="choice suspect"
onclick="choose('${x}',this)">
${x}
</button>
`
).join('')}

</div>

`;

}

if(m.type==='sentence'){

body=`

<div class="sentence">

ذهبَ
<span class="blank">؟</span>
إلى المدرسة. 🏫

</div>

<div class="choices">

<button class="choice"
onclick="choose('أحمد',this)">
👦🏻 أحمد
</button>

<button class="choice"
onclick="choose('الكتاب',this)">
📖 الكتاب
</button>

<button class="choice"
onclick="choose('الشجرة',this)">
🌳 الشجرة
</button>

</div>

`;

}

s.innerHTML=

`

<h2>${m.title}</h2>

<div class="instruction">
${m.text}
</div>

<div class="timerWrap">

⏳

<div class="timer" id="timer">
30
</div>

ثانية

</div>

<div class="game">

${body}

<div class="feedback"
id="feedback">
</div>

<div class="actions">

<button class="check"
onclick="check()">
تحقّق ✓
</button>

<button class="hint"
onclick="hint()">
💡 تلميح
</button>

</div>

</div>

`;

update();

runTimer();

}

function runTimer(){

timer=setInterval(()=>{

time--;

const t=document.getElementById('timer');

if(!t)return;

t.textContent=time;

t.className=
'timer '+
(time<=9?'danger':
time<=15?'warn':'');

if(time<=0){

clearInterval(timer);

feedback(
'⏰ انتهى الوقت! حاول مرة أخرى.',
'wrong'
);

document.querySelector('.check').disabled=true;

}

},1000);

}

function pick(x,b){

answer.push(x);

b.disabled=true;

const slots=document.querySelectorAll('.slot');

slots[answer.length-1].textContent=x;

}

function choose(x,b){

selected=x;

document
.querySelectorAll('.choice')
.forEach(e=>
e.classList.remove('selected','pop')
);

b.classList.add('selected','pop');

}

function check(){

const m=data[i];

let ok=false;

if(
m.type==='letters'||
m.type==='picture'
){

ok=answer.join('')===m.word;

}

if(
m.type==='missing'||
m.type==='odd'||
m.type==='sentence'
){

ok=selected===m.correct;

}

if(ok){

clearInterval(timer);

document
.getElementById('screen')
.classList.add('correctFlash');

setTimeout(()=>
document
.getElementById('screen')
?.classList.remove('correctFlash'),
600
);

score+=50;
clues++;

document
.querySelectorAll('.mission')[i]
?.classList.add('done');

feedback(
'🎉 صحيح! حصلت على دليل جديد ⭐',
'success'
);

document.querySelector('.check').disabled=true;

setTimeout(()=>{

i++;

if(i<data.length){

render();

}else{

finish();

}

},850);

}

else{

document
.getElementById('screen')
.classList.add('wrongShake');

setTimeout(()=>
document
.getElementById('screen')
?.classList.remove('wrongShake'),
450
);

feedback(
'❌ ليست الإجابة الصحيحة... راجع الأدلة وحاول!',
'wrong'
);

}

update();

}

function hint(){

feedback(
'💡 ركّز في الصورة، وترتيب الحروف، ومعنى الجملة.',
'success'
);

}

function feedback(t,c){

const f=document.getElementById('feedback');

if(f){

f.textContent=t;

f.className='feedback '+c;

}

}

function update(){

document.getElementById('score').textContent=score;

document.getElementById('clues').textContent=clues+'/5';

document.getElementById('level').textContent=
Math.min(i,5)+'/5';

document.getElementById('fill').style.width=
(Math.min(i,5)/5*100)+'%';

}

function finish(){

document.getElementById('screen').classList.add('hidden');

const e=document.getElementById('end');

e.classList.remove('hidden');

e.innerHTML=`

<div class="cup">
🏆🔐
</div>

<h2>
الملف السري
</h2>

<p>
أحسنت أيها المحقق! 🎉
<br>
جمعت كل الأدلة وأعدت الكلمات إلى مدينة اللغة.
</p>

<div class="secret">

تم حل CASE 003 بنجاح ✅

<br><br>

لكن... النظام اكتشف ملفًا جديدًا 👀

<br><br>

<strong style="font-size:25px">
CASE 004 // ???
</strong>

</div>

<button class="again"
onclick="location.reload()">

إعادة التحقيق ↻

</button>

`;

update();

}

function shuffle(a){

for(
let j=a.length-1;
j>0;
j--
){

let k=Math.floor(
Math.random()*(j+1)
);

[a[j],a[k]]=
[a[k],a[j]];

}

return a;

}

</script>

</body>
</html>
