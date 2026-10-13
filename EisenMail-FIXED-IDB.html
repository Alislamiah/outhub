<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<meta name="theme-color" content="#07162b">
<title>Eisen Mail — Alislamiah</title>
<link rel="icon" href="icon.png" type="image/png">
<style>
:root{
  --bg:#06101f;--panel:#0c1b31;--blue:#1769ff;--cyan:#39c6ff;--text:#f2f6ff;
  --muted:#a5b6d0;--border:#233a58;--green:#23c483;--red:#ff5d70;--gold:#f5c542;
  --header-h:64px;--nav-h:68px;
}
*{box-sizing:border-box}
body{
  margin:0;font-family:system-ui,-apple-system,"Segoe UI",Tahoma,Arial,sans-serif;
  background:linear-gradient(160deg,#030914 0%,#07172c 50%,#0b2140 100%);
  color:var(--text);min-height:100vh;min-height:100dvh;
}
button,input,textarea{font:inherit}
button{cursor:pointer;transition:background .15s,transform .12s,opacity .15s}
button:disabled{opacity:.5;cursor:not-allowed}

/* ===== SPLASH / LOADING ===== */
#splash{
  position:fixed;inset:0;z-index:9999;
  background:#0a0e1a;
  background-image:
    linear-gradient(rgba(20,40,70,.18) 1px, transparent 1px),
    linear-gradient(90deg, rgba(20,40,70,.18) 1px, transparent 1px);
  background-size:40px 40px;
  display:flex;align-items:center;justify-content:center;
  transition:opacity .55s ease,visibility .55s;
}
#splash.hide{opacity:0;visibility:hidden;pointer-events:none}
.splash-inner{
  position:relative;width:160px;height:160px;
  display:flex;align-items:center;justify-content:center;
}
/* مربع أزرق يدور خلف الأيقونة */
.splash-blob{
  position:absolute;width:118px;height:118px;z-index:1;
  border-radius:28px;
  background:linear-gradient(135deg,#1769ff 0%,#2a9dff 50%,#4d7cff 100%);
  opacity:0;
  box-shadow:0 0 28px #1769ffaa,0 0 56px #39c6ff55;
  animation:
    blobAppear .3s ease 1.3s forwards,
    blobSpin 1.8s linear 1.3s infinite;
}
@keyframes blobAppear{to{opacity:1}}
@keyframes blobSpin{to{transform:rotate(360deg)}}
.splash-icon{
  width:88px;height:88px;border-radius:22px;object-fit:contain;
  position:relative;z-index:2;
  background:#fff;padding:5px;
  box-shadow:0 10px 36px #0009,0 0 0 3px rgba(255,255,255,.2);
  animation:iconFlip 1.3s cubic-bezier(.34,1.15,.64,1) forwards;
}
.splash-icon-fallback{
  width:88px;height:88px;border-radius:22px;
  background:linear-gradient(145deg,#1769ff,#39c6ff);
  display:none;align-items:center;justify-content:center;
  font-size:32px;font-weight:800;color:#fff;
  position:relative;z-index:2;
  box-shadow:0 10px 36px #0009;
  animation:iconFlip 1.3s cubic-bezier(.34,1.15,.64,1) forwards;
}
@keyframes iconFlip{
  0%{transform:translateY(-240px) rotate(-30deg) scale(.3);opacity:0}
  30%{opacity:1}
  48%{transform:translateY(20px) rotate(14deg) scale(1.1)}
  62%{transform:translateY(-12px) rotate(-8deg) scale(.95)}
  75%{transform:translateY(6px) rotate(4deg) scale(1.03)}
  88%{transform:translateY(-3px) rotate(-1deg) scale(.99)}
  100%{transform:translateY(0) rotate(0deg) scale(1);opacity:1}
}
.splash-text{
  position:absolute;bottom:-50px;left:50%;transform:translateX(-50%);
  font-size:15px;font-weight:600;color:#9db8d8;white-space:nowrap;
  letter-spacing:.4px;
  opacity:0;animation:fadeText .4s ease 1.45s forwards;
}
@keyframes fadeText{to{opacity:1}}

/* ===== HEADER ===== */
header{
  height:var(--header-h);display:flex;align-items:center;justify-content:space-between;
  padding:0 14px;border-bottom:1px solid var(--border);
  background:rgba(7,19,38,.94);backdrop-filter:blur(14px);
  position:fixed;top:0;left:0;right:0;z-index:30;
}
.brand{display:flex;align-items:center;gap:9px;font-size:20px;font-weight:700}
.brand img{width:36px;height:36px;object-fit:contain;border-radius:10px}
.brand span{color:var(--cyan)}
.header-right{display:flex;align-items:center;gap:10px}
#headerUser{font-size:11px;color:var(--muted);max-width:140px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.gemalot-btn{
  display:flex;flex-direction:column;align-items:center;justify-content:center;gap:1px;
  padding:5px 12px;border-radius:12px;background:linear-gradient(135deg,#1a2a4a,#0f1c33);
  border:1px solid #3a5080;color:var(--text);text-decoration:none;min-width:78px;
}
.gemalot-btn:hover{border-color:var(--gold);box-shadow:0 0 16px #f5c54233}
.gemalot-btn .star{font-size:17px;line-height:1;filter:drop-shadow(0 0 5px #f5c54299)}
.gemalot-btn .label{font-size:9px;font-weight:700;color:var(--gold);letter-spacing:.2px}

/* ===== MAIN CONTENT ===== */
main{
  max-width:720px;margin:0 auto;
  padding:calc(var(--header-h) + 14px) 12px calc(var(--nav-h) + 24px);
  min-height:100vh;min-height:100dvh;
}
.card{
  background:linear-gradient(155deg,#0d1e35,#0a1729);
  border:1px solid var(--border);border-radius:16px;padding:16px 16px 18px;
  box-shadow:0 10px 28px #0003;
}
h1{font-size:22px;margin:0 0 6px;font-weight:700}
h2{font-size:18px;margin:0 0 12px;font-weight:700}
h3{font-size:15px;margin:0 0 8px}
p{line-height:1.7;color:var(--muted);margin:0 0 10px}
label{display:block;margin:12px 0 5px;color:#dce9ff;font-size:13px;font-weight:500}
input,textarea{
  width:100%;padding:12px 13px;background:#061326;border:1px solid #2b4567;
  border-radius:11px;color:white;outline:none;
}
input:focus,textarea:focus{border-color:var(--cyan);box-shadow:0 0 0 3px #39c6ff22}
textarea{min-height:120px;resize:vertical}
.btn,button.btn{
  display:inline-block;border:0;padding:11px 15px;border-radius:11px;
  background:var(--blue);color:white;font-weight:600;text-decoration:none;margin:4px 2px 0 0;
}
button.secondary,.secondary{background:#1b304c;border:1px solid #35516f}
button.green,.green{background:#087b58}button.red,.red{background:#a82d43}
.full{width:100%;margin-top:10px}
.hidden{display:none!important}
.muted{color:var(--muted);font-size:12px}
.notice{padding:11px 13px;border-radius:11px;background:#102944;color:#dceeff;margin:10px 0;line-height:1.65;font-size:13px}
.error{background:#451b2a;color:#ffd8de}.success{background:#103b31;color:#bfffe8}
.tabs{display:flex;gap:7px;margin-bottom:14px}
.tabs button{flex:1;padding:10px;border-radius:10px;border:0;background:#1b304c;color:white;font-weight:600}
.tabs button.active-tab{background:var(--blue)}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:12px}
.plan{
  border:1px solid #2c5279;border-radius:14px;padding:14px;
  background:linear-gradient(155deg,#102745,#0b192d);
}
.plan .price{font-size:22px;font-weight:700;color:var(--cyan);margin:8px 0}
.plan .space{font-size:16px;font-weight:700}
.plan.active{border-color:var(--green)}
.badge{display:inline-block;padding:4px 9px;border-radius:16px;background:#143e39;color:#aaffdf;font-size:11px;font-weight:600}
.item{padding:13px 0;border-bottom:1px solid var(--border);overflow-wrap:anywhere}
.item:last-child{border-bottom:0}
.item strong{display:block;margin-bottom:4px;font-size:15px}
.item small{color:var(--muted);font-size:12px}
.item p{white-space:pre-wrap;margin:8px 0;font-size:14px;color:#d0dceb}
.row{display:flex;gap:10px;flex-wrap:wrap}
.row>*{flex:1;min-width:130px}
.stat{background:#071529;border:1px solid var(--border);border-radius:12px;padding:12px}
.stat strong{display:block;font-size:18px;color:var(--cyan);margin-bottom:3px}
.stat span{font-size:12px;color:var(--muted)}
hr{border:0;border-top:1px solid var(--border);margin:14px 0}

/* ===== BOTTOM NAV ===== */
.bottom-nav{
  position:fixed;bottom:0;left:0;right:0;z-index:30;
  height:var(--nav-h);display:none;
  background:rgba(7,19,38,.96);backdrop-filter:blur(14px);
  border-top:1px solid var(--border);
  padding:4px 4px calc(4px + env(safe-area-inset-bottom));
  justify-content:space-around;align-items:stretch;
}
.bottom-nav.visible{display:flex}
.nav-btn{
  flex:1;display:flex;flex-direction:column;align-items:center;justify-content:center;
  gap:3px;background:transparent;border:0;color:var(--muted);font-size:10px;font-weight:600;
  padding:6px 2px;border-radius:10px;max-width:80px;
}
.nav-btn .ico{font-size:20px;line-height:1}
.nav-btn.active{color:var(--cyan)}
.nav-btn:active{transform:scale(.94)}
.nav-btn.danger{color:#ff8a9a}

/* auth only footer space */
#authView{padding-bottom:20px}
footer{text-align:center;color:#8195b1;padding:16px;font-size:11px}

@media(max-width:420px){
  #headerUser{max-width:90px;font-size:10px}
  .gemalot-btn{min-width:68px;padding:4px 8px}
  .nav-btn{font-size:9px}
}
</style>
</head>
<body>

<!-- شاشة التحميل -->
<div id="splash">
  <div class="splash-inner">
    <div class="splash-blob"></div>
    <img class="splash-icon" src="icon.png" alt="" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'">
    <div class="splash-icon-fallback" style="display:none">E</div>
    <div class="splash-text">Eisen Mail</div>
  </div>
</div>

<header>
  <div class="brand">
    <img src="icon.png" alt="Eisen Mail" onerror="this.style.display='none'">
    <div>Eisen <span>Mail</span></div>
  </div>
  <div class="header-right">
    <div id="headerUser">البريد المستقل من Alislamiah</div>
    <a class="gemalot-btn" href="https://mohamedmadoui5195.github.io/Gemalot/" target="_blank" rel="noopener" title="Ask Gemalot">
      <span class="star">✦</span>
      <span class="label">Ask Gemalot</span>
    </a>
  </div>
</header>

<main>
  <!-- ========== AUTH ========== -->
  <section id="authView">
    <div class="card">
      <h1>مرحبًا بك في Eisen Mail</h1>
      <p>بريد محلي مستقل. الحسابات والرسائل تُحفظ على هذا المتصفح فقط.</p>
      <div class="tabs">
        <button type="button" id="tabLogin" class="active-tab" onclick="showAuth('login')">تسجيل الدخول</button>
        <button type="button" id="tabSignup" onclick="showAuth('signup')">إنشاء حساب</button>
      </div>
      <div id="loginForm">
        <label for="loginEmail">عنوان البريد</label>
        <input id="loginEmail" type="email" placeholder="name@eisen.local" autocomplete="username">
        <label for="loginPassword">كلمة المرور</label>
        <input id="loginPassword" type="password" autocomplete="current-password">
        <button class="full btn" onclick="login()">دخول إلى البريد</button>
      </div>
      <div id="signupForm" class="hidden">
        <label for="signupName">الاسم</label>
        <input id="signupName" maxlength="60" placeholder="اسمك">
        <label for="signupEmail">عنوان البريد</label>
        <input id="signupEmail" type="email" placeholder="name@eisen.local" autocomplete="username">
        <label for="signupPassword">كلمة المرور (8 أحرف على الأقل)</label>
        <input id="signupPassword" type="password" minlength="8" autocomplete="new-password">
        <label for="signupPassword2">تأكيد كلمة المرور</label>
        <input id="signupPassword2" type="password" minlength="8" autocomplete="new-password">
        <button class="full btn" onclick="signup()">إنشاء الحساب</button>
      </div>
      <div id="authMessage" class="notice hidden" role="status"></div>
    </div>
  </section>

  <!-- ========== APP (messages in center) ========== -->
  <section id="appView" class="hidden">
    <!-- INBOX -->
    <div id="page-inbox" class="card">
      <h2>📥 صندوق الوارد</h2>
      <p class="muted">الرسائل التي وصلتك من حسابات أخرى على هذا المتصفح.</p>
      <div id="inboxList"></div>
    </div>
    <!-- SENT -->
    <div id="page-sent" class="card hidden">
      <h2>📤 الرسائل المرسلة</h2>
      <p class="muted">الرسائل التي أرسلتها إلى حسابات محلية أخرى.</p>
      <div id="sentList"></div>
    </div>
    <!-- COMPOSE -->
    <div id="page-compose" class="card hidden">
      <h2>✉️ رسالة جديدة</h2>
      <p class="muted">أدخل عنوان حساب موجود على هذا المتصفح. الرسالة تُحفظ محليًا وتظهر فورًا في وارد المستلم.</p>
      <label for="toEmail">إلى (عنوان الحساب المحلي)</label>
      <input id="toEmail" type="email" placeholder="مثلاً: friend@eisen.local">
      <label for="mailSubject">الموضوع</label>
      <input id="mailSubject" maxlength="160" placeholder="موضوع الرسالة">
      <label for="mailBody">نص الرسالة</label>
      <textarea id="mailBody" maxlength="50000" placeholder="اكتب رسالتك هنا..."></textarea>
      <button class="full btn" onclick="sendMessage()">إرسال الرسالة</button>
      <div class="notice" style="margin-top:12px">
        الإرسال والاستقبال يعملان فقط بين الحسابات المحفوظة في <b>نفس المتصفح</b>. لا يوجد خادم خارجي.
      </div>
    </div>
    <!-- PLANS -->
    <div id="page-plans" class="card hidden">
      <h2>💎 مساحة التخزين</h2>
      <div class="row" style="margin-bottom:12px">
        <div class="stat"><strong id="usedSpace">0 MB</strong><span>المستخدم التقريبي</span></div>
        <div class="stat"><strong id="totalSpace">100 MB</strong><span>المساحة الحالية</span></div>
      </div>
      <button type="button" class="full secondary" id="plansToggleBtn" onclick="togglePlansPanel()" style="margin-top:4px">
        عرض باقات التخزين ▼
      </button>
      <div id="plansPanel" class="hidden" style="margin-top:14px">
        <div id="userPlans" class="grid"></div>
        <div class="notice">طلب الشراء عبر واتساب. الضغط على الدفع لا يفعّل الاشتراك تلقائيًا.</div>
      </div>
    </div>
    <!-- SETTINGS -->
    <div id="page-settings" class="card hidden">
      <h2>⚙️ الحساب والنسخ</h2>
      <div id="accountDetails"></div>
      <hr>
      <h3>النسخ الاحتياطي</h3>
      <p>صدّر أو استورد الحسابات والرسائل المحفوظة محليًا.</p>
      <button class="btn" onclick="exportBackup()">تصدير نسخة احتياطية</button>
      <label for="importFile">استيراد ملف JSON</label>
      <input id="importFile" type="file" accept="application/json">
      <button class="secondary full" onclick="importBackup()">استيراد النسخة</button>
      <hr>
      <button class="red full" onclick="logout()">تسجيل الخروج</button>
    </div>
  </section>
</main>

<!-- BOTTOM NAV (only when logged in) -->
<nav class="bottom-nav" id="bottomNav">
  <button type="button" class="nav-btn active" data-page="inbox" onclick="openPage('inbox')">
    <span class="ico">📥</span><span>الوارد</span>
  </button>
  <button type="button" class="nav-btn" data-page="sent" onclick="openPage('sent')">
    <span class="ico">📤</span><span>المرسلة</span>
  </button>
  <button type="button" class="nav-btn" data-page="compose" onclick="openPage('compose')">
    <span class="ico">✉️</span><span>جديد</span>
  </button>
  <button type="button" class="nav-btn" data-page="plans" onclick="openPage('plans')">
    <span class="ico">💎</span><span>الباقات</span>
  </button>
  <button type="button" class="nav-btn" data-page="settings" onclick="openPage('settings')">
    <span class="ico">⚙️</span><span>الحساب</span>
  </button>
</nav>

<footer id="authFooter">© Alislamiah — Eisen Mail</footer>

<script>

// ===== IDB FIX - يحل مشكل transaction stores was not found =====
function openDB(){
  return new Promise((resolve, reject)=>{
    // نحاول نفتح، إذا فشل بسبب version قديم، نمسح ونعاود
    const req = indexedDB.open('eisen_mail_db', 3);
    req.onupgradeneeded = (e)=>{
      const db = e.target.result;
      // انشئ stores إذا مش موجودين
      if(!db.objectStoreNames.contains('users')){
        db.createObjectStore('users', {keyPath:'email'});
      }
      if(!db.objectStoreNames.contains('messages')){
        db.createObjectStore('messages', {keyPath:'id', autoIncrement:true});
      }
      if(!db.objectStoreNames.contains('accounts')){
        db.createObjectStore('accounts', {keyPath:'email'});
      }
    };
    req.onsuccess = (e)=>{
      const db = e.target.result;
      // تأكد أن الـ stores موجودة فعلا، وإلا امسح DB وعاود
      if(!db.objectStoreNames.contains('users') || !db.objectStoreNames.contains('messages')){
        db.close();
        const del = indexedDB.deleteDatabase('eisen_mail_db');
        del.onsuccess = ()=>{ openDB().then(resolve).catch(reject); };
        del.onerror = ()=>{ reject(del.error); };
        return;
      }
      resolve(db);
    };
    req.onerror = ()=> reject(req.error);
    req.onblocked = ()=>{ console.warn('DB blocked'); };
  });
}

// استبدال أي استخدام قديم لـ indexedDB.open مباشرة بـ openDB()
window.eisenOpenDB = openDB;

async function safeTransaction(storeNames, mode){
  const db = await openDB();
  // تحقق أن كل store موجود
  for(const s of [].concat(storeNames)){
    if(!db.objectStoreNames.contains(s)){
      db.close();
      await new Promise(res=>{ const del=indexedDB.deleteDatabase('eisen_mail_db'); del.onsuccess=del.onerror=res; });
      const db2 = await openDB();
      return db2.transaction(storeNames, mode);
    }
  }
  return db.transaction(storeNames, mode);
}



"use strict";
const WHATSAPP_NUMBER = "213777543015";
const PLANS = [
  {id:"free",name:"Eisen Free",bytes:100*1024*1024,label:"100 MB",price:0,priceLabel:"مجانًا"},
  {id:"plus",name:"Eisen Plus",bytes:1*1024**3,label:"1 Go",price:2,priceLabel:"2 دولار"},
  {id:"pro",name:"Eisen Pro",bytes:5*1024**3,label:"5 Go",price:5,priceLabel:"5 دولارات"},
  {id:"max",name:"Eisen Max",bytes:7*1024**3,label:"7 Go",price:12,priceLabel:"12 دولارًا"}
];
let db = null, currentUser = null, currentPage = "inbox";
const $ = id => document.getElementById(id);

function openDB(){
  return new Promise((resolve,reject)=>{
    const r = indexedDB.open("EisenMailDB",1);
    r.onupgradeneeded = e => {
      const d = e.target.result;
      if(!d.objectStoreNames.contains("users")) d.createObjectStore("users",{keyPath:"email"});
      if(!d.objectStoreNames.contains("messages")){
        const s = d.createObjectStore("messages",{keyPath:"id",autoIncrement:true});
        s.createIndex("to","to"); s.createIndex("from","from");
      }
    };
    r.onsuccess = ()=>{ db = r.result; resolve(); };
    r.onerror = ()=> reject(r.error);
  });
}

function request(storeName, method, value){
  return new Promise((resolve,reject)=>{
    const tx = db.transaction(storeName, method==="get"||method==="getAll" ? "readonly" : "readwrite");
    const s = tx.objectStore(storeName);
    let r;
    if(method==="get") r = s.get(value);
    else if(method==="getAll") r = s.getAll();
    else if(method==="delete") r = s.delete(value);
    else if(method==="add") r = s.add(value);
    else r = s.put(value);
    r.onsuccess = ()=> resolve(r.result);
    r.onerror = ()=> reject(r.error);
  });
}

const getUser = email => request("users","get",email);
const getUsers = () => request("users","getAll");
const getMessages = () => request("messages","getAll");

function esc(v){
  return String(v??"").replace(/[&<>"']/g, c => ({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]));
}
function emailNorm(v){ return String(v||"").trim().toLowerCase(); }
function plan(id){ return PLANS.find(p => p.id === id) || PLANS[0]; }
function bytesText(n){
  if(n < 1024*1024) return Math.round(n/1024) + " KB";
  if(n < 1024**3) return (n/1024**2).toFixed(1) + " MB";
  return (n/1024**3).toFixed(2) + " Go";
}

function message(text, type=""){
  const e = $("authMessage");
  e.className = "notice " + type;
  e.textContent = text;
  e.classList.remove("hidden");
}

function showAuth(which){
  $("loginForm").classList.toggle("hidden", which !== "login");
  $("signupForm").classList.toggle("hidden", which !== "signup");
  $("tabLogin").classList.toggle("active-tab", which === "login");
  $("tabSignup").classList.toggle("active-tab", which === "signup");
  $("authMessage").classList.add("hidden");
}

function drawPlans(id, interactive){
  $(id).innerHTML = PLANS.map(p => `
    <div class="plan ${currentUser && currentUser.plan === p.id ? "active" : ""}">
      <h3>${esc(p.name)}</h3>
      <div class="space">${esc(p.label)}</div>
      <div class="price">${esc(p.priceLabel)}</div>
      ${currentUser && currentUser.plan === p.id ? '<span class="badge">باقتك الحالية</span>' : ""}
      ${interactive && p.id !== "free" ? `<button class="full btn" onclick="buyPlan('${p.id}')">الدفع عبر WhatsApp</button>` : ""}
    </div>
  `).join("");
}

async function signup(){
  const name = $("signupName").value.trim();
  const email = emailNorm($("signupEmail").value);
  const pass = $("signupPassword").value;
  const pass2 = $("signupPassword2").value;
  if(!name || !email || !pass || !pass2) return message("يرجى ملء جميع الحقول.","error");
  if(!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) return message("أدخل عنوان بريد صحيحًا.","error");
  if(pass.length < 8) return message("كلمة المرور يجب أن تكون 8 أحرف على الأقل.","error");
  if(pass !== pass2) return message("كلمتا المرور غير متطابقتين.","error");
  try{
    if(await getUser(email)) return message("الحساب موجود بالفعل. سجّل الدخول.","error");
    await request("users","add",{email,name,password:pass,plan:"free",createdAt:new Date().toISOString()});
    $("loginEmail").value = email;
    $("loginPassword").value = "";
    showAuth("login");
    message("تم إنشاء الحساب محليًا. يمكنك تسجيل الدخول.","success");
  }catch(e){ message("تعذر إنشاء الحساب: "+e.message,"error"); }
}

async function login(){
  const email = emailNorm($("loginEmail").value);
  const pass = $("loginPassword").value;
  if(!email || !pass) return message("أدخل البريد وكلمة المرور.","error");
  try{
    const u = await getUser(email);
    if(!u) return message("الحساب غير موجود. أنشئ حسابًا جديدًا.","error");
    if(u.password !== pass) return message("كلمة المرور غير صحيحة.","error");
    currentUser = u;
    enterApp();
  }catch(e){ message("تعذر تسجيل الدخول.","error"); }
}

function enterApp(){
  $("authView").classList.add("hidden");
  $("appView").classList.remove("hidden");
  $("bottomNav").classList.add("visible");
  $("authFooter").classList.add("hidden");
  $("headerUser").textContent = currentUser.email;
  openPage("inbox");
  refreshQuota();
}

function logout(){
  currentUser = null;
  $("appView").classList.add("hidden");
  $("authView").classList.remove("hidden");
  $("bottomNav").classList.remove("visible");
  $("authFooter").classList.remove("hidden");
  $("headerUser").textContent = "البريد المستقل من Alislamiah";
  $("loginPassword").value = "";
  showAuth("login");
}

function hidePages(){
  document.querySelectorAll('[id^="page-"]').forEach(e => e.classList.add("hidden"));
}

function setNavActive(page){
  document.querySelectorAll(".nav-btn").forEach(b => {
    b.classList.toggle("active", b.dataset.page === page);
  });
}

function openPage(p){
  if(!currentUser) return;
  currentPage = p;
  hidePages();
  $("page-"+p).classList.remove("hidden");
  setNavActive(p);
  if(p === "inbox" || p === "sent") renderMessages(p);
  if(p === "plans"){
    drawPlans("userPlans", true);
    refreshQuota();
    $("plansPanel").classList.add("hidden");
    $("plansToggleBtn").textContent = "عرض باقات التخزين ▼";
  }
  if(p === "settings") renderAccount();
}

function togglePlansPanel(){
  const panel = $("plansPanel");
  const open = panel.classList.toggle("hidden") === false;
  $("plansToggleBtn").textContent = open ? "إخفاء الباقات ▲" : "عرض باقات التخزين ▼";
}

async function renderMessages(which){
  const target = $(which === "inbox" ? "inboxList" : "sentList");
  try{
    let arr = (await getMessages()).filter(m =>
      which === "inbox" ? m.to === currentUser.email : m.from === currentUser.email
    );
    arr.sort((a,b) => b.date.localeCompare(a.date));
    if(!arr.length){
      target.innerHTML = `<div class="notice">${which==="inbox"?"لا توجد رسائل واردة بعد.":"لا توجد رسائل مرسلة بعد."}</div>`;
      return;
    }
    target.innerHTML = arr.map(m => `
      <div class="item">
        <strong>${esc(m.subject || "(بدون موضوع)")}</strong>
        <small>${which==="inbox" ? "من: "+esc(m.from) : "إلى: "+esc(m.to)} · ${esc(new Date(m.date).toLocaleString("ar"))}</small>
        <p>${esc(m.body)}</p>
        <div>
          ${which==="inbox" ? `<button class="secondary" onclick='replyTo(${JSON.stringify(m.from)},${JSON.stringify(m.subject||"")})'>رد</button>` : ""}
          <button class="red" onclick="deleteMessage(${m.id})">حذف</button>
        </div>
      </div>
    `).join("");
  }catch(e){
    target.innerHTML = '<div class="notice error">تعذر تحميل الرسائل.</div>';
  }
}

async function sendMessage(){
  const to = emailNorm($("toEmail").value);
  const subject = $("mailSubject").value.trim();
  const body = $("mailBody").value.trim();
  if(!to || !body) return alert("أدخل عنوان المستلم ونص الرسالة.");
  if(to === currentUser.email) return alert("لا يمكنك الإرسال إلى نفسك.");
  try{
    const recipient = await getUser(to);
    if(!recipient) return alert("الحساب المستلم غير موجود في هذا المتصفح.\nأنشئ حسابًا ثانيًا بنفس المتصفح ثم أرسل إليه.");
    const all = await getMessages();
    const used = all
      .filter(m => m.from === currentUser.email || m.to === currentUser.email)
      .reduce((s,m) => s + new Blob([m.subject||"", m.body||""]).size, 0);
    if(used + new Blob([subject, body]).size > plan(currentUser.plan).bytes){
      alert("المساحة غير كافية. اختر باقة أكبر.");
      openPage("plans");
      return;
    }
    await request("messages","add",{
      from: currentUser.email, to, subject, body, date: new Date().toISOString()
    });
    $("toEmail").value = "";
    $("mailSubject").value = "";
    $("mailBody").value = "";
    alert("تم إرسال الرسالة.\nستظهر في صندوق وارد المستلم فورًا (على نفس المتصفح).");
    refreshQuota();
    openPage("sent");
  }catch(e){ alert("تعذر إرسال الرسالة: " + e.message); }
}

function replyTo(email, subject){
  openPage("compose");
  $("toEmail").value = email;
  $("mailSubject").value = subject.startsWith("Re:") ? subject : "Re: " + subject;
  $("mailBody").focus();
}

async function deleteMessage(id){
  if(!confirm("حذف الرسالة؟")) return;
  await request("messages","delete", Number(id));
  renderMessages(currentPage);
  refreshQuota();
}

async function refreshQuota(){
  if(!currentUser) return;
  const arr = await getMessages();
  const used = arr
    .filter(m => m.from === currentUser.email || m.to === currentUser.email)
    .reduce((s,m) => s + new Blob([m.subject||"", m.body||""]).size, 0);
  const p = plan(currentUser.plan);
  $("usedSpace").textContent = bytesText(used);
  $("totalSpace").textContent = p.label;
}

function buyPlan(id){
  const p = plan(id);
  const msg = `السلام عليكم، أريد شراء مساحة تخزين في Eisen Mail.\nالحساب: ${currentUser.email}\nالباقة: ${p.name}\nالمساحة: ${p.label}\nالسعر: ${p.priceLabel}\nأرجو إعلامي بطريقة الدفع.`;
  window.open("https://wa.me/"+WHATSAPP_NUMBER+"?text="+encodeURIComponent(msg),"_blank","noopener");
}

function renderAccount(){
  const p = plan(currentUser.plan);
  $("accountDetails").innerHTML = `
    <div class="item"><strong>الاسم</strong>${esc(currentUser.name)}</div>
    <div class="item"><strong>عنوان الحساب</strong>${esc(currentUser.email)}</div>
    <div class="item"><strong>الباقة</strong>${esc(p.name)} — ${esc(p.label)}</div>
    <div class="item"><strong>تاريخ الإنشاء</strong>${esc(new Date(currentUser.createdAt).toLocaleString("ar"))}</div>
  `;
}

async function exportBackup(){
  const data = {app:"Eisen Mail",version:1,users:await getUsers(),messages:await getMessages()};
  const blob = new Blob([JSON.stringify(data,null,2)],{type:"application/json"});
  const url = URL.createObjectURL(blob);
  const a = document.createElement("a");
  a.href = url; a.download = "eisen-mail-backup.json"; a.click();
  setTimeout(()=> URL.revokeObjectURL(url), 1000);
}

async function importBackup(){
  const f = $("importFile").files[0];
  if(!f) return alert("اختر ملف JSON.");
  if(!confirm("سيتم استيراد الحسابات والرسائل إلى هذا المتصفح. المتابعة؟")) return;
  try{
    const d = JSON.parse(await f.text());
    if(d.app !== "Eisen Mail" || !Array.isArray(d.users) || !Array.isArray(d.messages)) throw Error("invalid");
    for(const u of d.users) if(u.email) await request("users","put",u);
    for(const m of d.messages){
      if(m.id) await request("messages","put",m);
      else await request("messages","add",m);
    }
    alert("اكتمل الاستيراد.");
    $("importFile").value = "";
  }catch(e){ alert("تعذر الاستيراد: الملف غير صالح."); }
}


// ================== OutHub Bridge - لا يمس الشكل ==================
window.EisenMailAPI = {
  sendVerification: async function(toEmail, code, purpose){
    try{
      toEmail = String(toEmail||"").trim().toLowerCase();
      if(!toEmail) return false;
      if(!db) await openDB();
      await request("messages","add",{
        from: "no-reply@outhub.system",
        to: toEmail,
        subject: purpose==="reset" ? "رمز استعادة كلمة المرور - OutHub" : "رمز التحقق - OutHub",
        body: "مرحبا،\n\nرمز التحقق الخاص بك في OutHub هو:\n\n"+code+"\n\nصالح لمدة 10 دقائق. لا تشاركه مع أحد.\n\n- OutHub",
        date: new Date().toISOString()
      });
      if(currentUser && currentUser.email===toEmail){ renderMessages(currentPage); refreshQuota(); }
      return true;
    }catch(e){ return false; }
  }
};
window.addEventListener("storage", async function(e){
  if(e.key==="outhub_send_code_request" && e.newValue){
    try{ const r=JSON.parse(e.newValue); if(r&&r.to&&r.code) await window.EisenMailAPI.sendVerification(r.to,r.code,r.purpose); }catch{}
  }
});



// ===== استقبال رمز OutHub - بسيط ومضمون =====
(function(){
  const KEY="outhub_send_code_request";
  let lastAt=0;
  async function check(){
    try{
      const raw=localStorage.getItem(KEY);
      if(!raw) return;
      const d=JSON.parse(raw);
      if(!d || !d.to || !d.code) return;
      if(d.at && d.at<=lastAt) return;
      lastAt=d.at||Date.now();
      const email=String(d.to).toLowerCase();
      if(!email) return;
      if(!window.db) { try{ await openDB(); }catch{} }
      if(window.db){
        const req = window.db.transaction("messages","readwrite").objectStore("messages").add({
          from:"no-reply@outhub.system",
          to:email,
          subject: d.purpose==="reset"?"رمز استعادة - OutHub":"رمز التحقق - OutHub",
          body:"رمز التحقق الخاص بك في OutHub هو:\n\n"+d.code+"\n\nصالح لمدة 10 دقائق.",
          date:new Date().toISOString()
        });
      }
      if(currentUser && currentUser.email===email){
        setTimeout(()=>{ try{ renderMessages(currentPage); refreshQuota(); }catch{} }, 500);
      }
    }catch(e){}
  }
  setInterval(check, 1000);
  window.addEventListener("storage", (e)=>{ if(e.key===KEY) check(); });
  setTimeout(check, 800);
})();

(async ()=>{
  try{
    await openDB();
    showAuth("login");
  }catch(e){
    $("authView").innerHTML = '<div class="card"><h2>تعذر فتح قاعدة البيانات</h2><p>استخدم متصفحًا حديثًا وافتح الصفحة عبر HTTPS أو من بيئة محلية تدعم IndexedDB.</p></div>';
  }
  // إخفاء شاشة التحميل بعد انتهاء الأنيميشن
  setTimeout(()=>{
    const splash = $("splash");
    if(splash){ splash.classList.add("hide"); setTimeout(()=> splash.remove(), 600); }
  }, 2800);
})();
</script>
</body>
</html>
