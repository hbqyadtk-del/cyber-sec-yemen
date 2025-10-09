<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>منصة مكافحة الابتزاز الإلكتروني</title>
<meta name="description" content="منصة مكافحة الابتزاز الإلكتروني – قدّم بلاغك بأمان وسرية كاملة.">
<style>
:root {
  --gold:#ffd700;
  --cyan:#19e6d8;
  --pink:#ff4eb3;
  --text:#f0f0f0;
  --box-bg:rgba(30,30,30,0.85);
  --button-color:#19e6d8;
}
body {
  margin:0;
  padding:0;
  font-family:"Segoe UI",Tahoma,Arial,sans-serif;
  background:black;
  color:var(--text);
  overflow-x:hidden;
}
canvas.bgCanvas {
  position:absolute; top:0; left:0; width:100%; height:100%; z-index:0;
}
.container {
  position:relative; z-index:1;
  max-width:1000px;
  margin:60px auto;
  padding:40px;
  border-radius:20px;
  background: var(--box-bg);
  box-shadow:0 0 40px var(--gold),0 0 80px var(--cyan);
  text-align:center;
}
h1 {font-size:2.4em;color:var(--gold); margin-bottom:20px;}
.scrollable {
  max-height:400px;
  overflow-y:auto;
  text-align:right;
  margin-bottom:30px;
  white-space: pre-line;
  line-height:1.6em;
  padding:10px;
}
button {
  position:relative;
  overflow:hidden;
  padding:15px 50px;
  font-size:1.2em;
  border:none;
  border-radius:15px;
  background:transparent;
  color:var(--button-color);
  font-weight:bold;
  cursor:pointer;
  margin:10px;
}
button::before {
  content:'';
  position:absolute;
  top:0; left:-100%;
  width:100%;
  height:100%;
  background:linear-gradient(120deg, rgba(255,255,255,0.2), rgba(255,255,255,0.6), rgba(255,255,255,0.2));
  transform:skewX(-20deg);
  transition: all 0.7s ease;
}
button:hover::before {left:200%;}
button:hover {color:white;}
#reportForm input {
  width:100%; padding:16px; margin-bottom:18px; border-radius:15px;
  border:2px solid rgba(255,255,255,0.2); background:transparent; color:var(--text); font-size:1.1em;
}
#status {margin-top:20px; min-height:22px; font-weight:bold; font-size:1.1em;}
#boxesContainer .cell {
  background: var(--box-bg); border:2px solid var(--button-color); border-radius:12px; margin-bottom:20px; padding:20px;
}
.page {display:none;}
.showPage {display:block;}
.backBtn {margin-top:20px; padding:10px 30px; border-radius:12px; border:2px solid var(--button-color); background:transparent; color:var(--button-color);}
</style>
</head>
<body>
<canvas class="bgCanvas" id="bgCanvas"></canvas>

<!-- الصفحة الرئيسية -->
<div class="container showPage" id="homePage">
  <h1>منصة مكافحة الابتزاز الإلكتروني</h1>
  <div class="scrollable">
مرحبًا بك في المنصة الوطنية لمكافحة الابتزاز الإلكتروني، حيث تلتقي القوة بالتقنية، والعدالة بالأمان.  
نحن هنا لنكون درعك الرقمي، وسندك القانوني، في وجه كل من يحاول استغلالك أو تهديدك عبر الإنترنت.  
منظمتنا تعمل على مدار الساعة، بقيادة نخبة من الخبراء في الأمن السيبراني والقانون، لضمان حماية المجتمع ومحاسبة المبتزين.  
بلاغك ليس مجرد رسالة، بل هو خطوة شجاعة نحو العدالة، ومساهمة فعالة في بناء بيئة رقمية نظيفة وآمنة للجميع.  
ثق أن كل معلومة تُرسل تُعامل بسرية تامة، وكل صوت يُسمع، وكل حق يُسترد.
  </div>
  <button id="btnReport">تقديم بلاغ</button>
  <button id="btnAbout">تصفح عنا</button>
  <button id="btnInstructions">التعليمات</button>
</div>

<!-- صفحة تقديم البلاغ -->
<div class="container page" id="reportPage">
  <h1>تقديم البلاغ</h1>
  <div class="scrollable" id="reportText">ادخل اسمك الثلاثي ورقم الواتس فقط، معلوماتك سرية بالكامل.</div>
  <div id="boxesContainer"></div>
  <form id="reportForm" action="https://formspree.io/f/xgvnzjnw" method="POST">
    <input type="text" name="name" id="nameInput" placeholder="اسمك الثلاثي" required>
    <input type="text" name="phone" id="phoneInput" placeholder="رقم الواتس للتواصل" required>
    <input type="hidden" name="date" id="dateInput">
    <button type="submit">إرسال البلاغ</button>
  </form>
  <div id="status"></div>
  <button id="backReport" class="backBtn">رجوع للقائمة</button>
</div>

<!-- صفحة تصفح عنا -->
<div class="container page" id="aboutPage">
  <h1>عن المنظمة</h1>
  <div class="scrollable">
في قلب اليمن، حيث الأصالة تلتقي بالعزة، وحيث التاريخ يُكتب بدماء الأبطال، نشأت منظمة اللواء القاعدة الجوية 590، ككيان سيبراني فريد... 
الرقم 590 ليس مجرد رقم عسكري، بل هو شيفرة فلسفية عميقة:
- الصفر هو البداية، رمز الانطلاق من العدم نحو القوة.
- الخمسة هي الحواس الخمس، أدوات الرصد والتحليل.
- التسعة هي النهاية المحكمة، رمز السيطرة الكاملة.
منظمة اللواء 590 لا تعمل فقط على حماية الأفراد، بل تسعى لبناء مجتمع رقمي آمن، خالٍ من الابتزاز والخوف والاستغلال.
  </div>
  <button id="backAbout" class="backBtn">رجوع للقائمة</button>
</div>

<!-- صفحة التعليمات -->
<div class="container page" id="instructionsPage">
  <h1>📘 تعليمات استخدام المنصة</h1>
  <div class="scrollable">
مرحبًا بك في منصة منظمة اللواء القاعدة الجوية 590، الذراع السيبراني الحصين لحماية المواطنين من الابتزاز الإلكتروني في اليمن...
🛡️ أولًا: الثقة والأمان
- المنصة موثّقة رسميًا وتعمل بتنسيق مباشر مع جهات أمنية.
📝 ثانيًا: خطوات تقديم البلاغ
- أدخل اسمك الثلاثي ورقم الواتس بدقة.
- اضغط على زر "إرسال البلاغ".
🔐 ثالثًا: خصوصيتك مسؤوليتنا
- يتم تشفير كل بلاغ تلقائيًا ولا يمكن اختراقه.
🧭 رابعًا: نصائح مهمة
- لا تشارك معلوماتك الشخصية خارج المنصة.
🕊️ خامسًا: رسالتنا لك
منظمة اللواء القاعدة الجوية 590 ليست مجرد منصة… إنها وعد وحماية.
  </div>
  <button id="backInstr" class="backBtn">رجوع للقائمة</button>
</div>

<script>
// خلفية متحركة
const canvas = document.getElementById('bgCanvas');
const ctx = canvas.getContext('2d');
let w = canvas.width = window.innerWidth;
let h = canvas.height = window.innerHeight;
window.addEventListener('resize', ()=>{w=canvas.width=window.innerWidth; h=canvas.height=window.innerHeight;});
let stars=[];
for(let i=0;i<100;i++){stars.push({x:Math.random()*w,y:Math.random()*h,r:Math.random()*2+1,dx:(Math.random()-0.5)*0.3,dy:(Math.random()-0.5)*0.3});}
function animate(){ctx.fillStyle='rgba(0,0,0,0.2)';ctx.fillRect(0,0,w,h);stars.forEach(s=>{ctx.beginPath();ctx.arc(s.x,s.y,s.r,0,Math.PI*2);ctx.fillStyle='white';ctx.fill();s.x+=s.dx;s.y+=s.dy;if(s.x<0)s.x=w;if(s.x>w)s.x=0;if(s.y<0)s.y=h;if(s.y>h)s.y=0;});requestAnimationFrame(animate);}
animate();

// التحكم بالصفحات
function showPage(id){
  document.querySelectorAll('.page, #homePage').forEach(p=>p.classList.remove('showPage'));
  document.getElementById(id).classList.add('showPage');
}

// أزرار القائمة
document.getElementById('btnReport').addEventListener('click', ()=>{showPage('reportPage');});
document.getElementById('btnAbout').addEventListener('click', ()=>{showPage('aboutPage');});
document.getElementById('btnInstructions').addEventListener('click', ()=>{showPage('instructionsPage');});
document.getElementById('backReport').addEventListener('click', ()=>{showPage('homePage');});
document.getElementById('backAbout').addEventListener('click', ()=>{showPage('homePage');});
document.getElementById('backInstr').addEventListener('click', ()=>{showPage('homePage');});

// إرسال البيانات عبر Formspree
const form = document.getElementById('reportForm');
const containerDiv = document.getElementById('boxesContainer');
const statusEl = document.getElementById('status');

form.addEventListener('submit', async (e)=>{
  e.preventDefault();
  const name = document.getElementById('nameInput').value.trim();
  const phone = document.getElementById('phoneInput').value.trim();
  if(!name || !phone){ alert("الرجاء كتابة الاسم الثلاثي ورقم الواتس."); return; }
  document.getElementById('dateInput').value = new Date().toLocaleString();
  const formData = new FormData(form);
  try{
    const response = await fetch(form.action,{method:form.method,body:formData,headers:{'Accept':'application/json'}});
    if(response.ok){
      const newCell = document.createElement('div'); newCell.classList.add('cell');
      newCell.innerHTML=`<span>الاسم الثلاثي: ${name}</span><br><span>رقم التواصل: ${phone}</span><br><span>تاريخ الإرسال: ${new Date().toLocaleString()}</span>`;
      containerDiv.appendChild(newCell);
      statusEl.style.color='#bff8f2';
      statusEl.textContent='تم الإرسال ✅ سيتم التواصل معك عبر رقمك.';
      form.reset();
    } else {statusEl.style.color='#ff4e4e'; statusEl.textContent='حدث خطأ، حاول مرة أخرى.';}
  } catch(err){statusEl.style.color='#ff4e4e'; statusEl.textContent='خطأ في الاتصال.';}
});
</script>
</body>
</html>
