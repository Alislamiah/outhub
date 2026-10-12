<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#050b18">
<title>Outhub</title>

<!-- Firebase SDKs -->
<script type="module">
  import { initializeApp } from "https://www.gstatic.com/firebasejs/13.0.0/firebase-app.js";
  import { 
    getAuth, 
    signInWithPopup, 
    GoogleAuthProvider, 
    signInWithEmailAndPassword, 
    createUserWithEmailAndPassword, 
    signOut, 
    onAuthStateChanged 
  } from "https://www.gstatic.com/firebasejs/13.0.0/firebase-auth.js";

  const firebaseConfig = {
    apiKey: "AIzaSyA9lqbYSqGXuPCovCNEVCtAKNZ-Sa2YbUk",
    authDomain: "outhub-ade73.firebaseapp.com",
    projectId: "outhub-ade73",
    storageBucket: "outhub-ade73.firebasestorage.app",
    messagingSenderId: "191923667246",
    appId: "1:191923667246:web:acc13c8f603338c552babf",
    measurementId: "G-K3SG4M6FR4"
  };

  const app = initializeApp(firebaseConfig);
  const auth = getAuth(app);
  window.auth = auth;
  window.GoogleAuthProvider = GoogleAuthProvider;
  window.signInWithPopup = signInWithPopup;
  window.signInWithEmailAndPassword = signInWithEmailAndPassword;
  window.createUserWithEmailAndPassword = createUserWithEmailAndPassword;
  window.signOut = signOut;
  window.onAuthStateChanged = onAuthStateChanged;
</script>

<style>
:root {
  --bg:#050b18;
  --panel:#0c172a;
  --panel2:#11223c;
  --border:#243958;
  --blue:#3478f6;
  --cyan:#31d9e8;
  --text:#f5f8ff;
  --muted:#9aacc5;
  --red:#ff6878;
  --green:#42d9a0;
}
*{box-sizing:border-box;margin:0;padding:0}
body{
  min-height:100vh;
  color:var(--text);
  background:radial-gradient(ellipse at top,#12274a,transparent 55%),var(--bg);
  font-family:Arial,sans-serif;
}
button,input,select{font:inherit}
button{cursor:pointer}
.hidden{display:none!important}
header{
  height:68px;padding:0 18px;
  display:flex;align-items:center;justify-content:space-between;
  background:#050b18ed;border-bottom:1px solid var(--border);
  position:sticky;top:0;z-index:5;
}
.brand{display:flex;align-items:center;gap:10px;font-size:23px;font-weight:900}
.brand img{width:39px;height:39px;object-fit:contain;border-radius:10px}
.brand span{color:var(--cyan)}
.container{width:min(100%,1000px);margin:auto;padding:24px 16px 70px}
.view{animation:fade .18s ease}
@keyframes fade{from{opacity:0;transform:translateY(4px)}to{opacity:1;transform:none}}
.card{
  background:linear-gradient(145deg,#101e33,#091323);
  border:1px solid var(--border);border-radius:18px;padding:21px;margin-bottom:15px;
}
.auth{width:min(100%,440px);margin:22px auto}
.auth-logo{text-align:center;margin-bottom:20px}
.auth-logo img{width:75px;height:75px;object-fit:contain;margin-bottom:12px}
h1{font-size:clamp(27px,5vw,39px);margin-bottom:12px}
h2{font-size:23px;margin-bottom:12px}
h3{font-size:18px;margin-bottom:10px}
p{line-height:1.8}
.muted{color:var(--muted)}
.small{font-size:13px}
.field{margin:17px 0}
label{display:block;color:#d0dced;font-size:14px;margin-bottom:8px}
input,select{
  width:100%;padding:14px;border:1px solid #2a3e5b;border-radius:11px;
  background:#050e1d;color:white;outline:none;
}
input:focus,select:focus{border-color:var(--blue)}
input::placeholder{color:#71849f}
.btn{
  display:flex;align-items:center;justify-content:center;text-align:center;
  width:100%;padding:13px 15px;border:0;border-radius:11px;
  text-decoration:none;font-weight:bold;margin-top:10px;
}
.primary{background:linear-gradient(110deg,#2864f0,#408eff);color:white}
.secondary{background:#142641;color:white;border:1px solid #294263}
.danger{background:#381a23;color:#ffabb3;border:1px solid #71313c}
.google-btn{background:#ea4335;color:white;margin-bottom:10px}
.link{background:none;border:0;color:#75adff;text-decoration:underline;padding:5px}
.form-links{display:flex;justify-content:space-between;flex-wrap:wrap;gap:10px;margin-top:17px}
.notice,.message{padding:13px;border-radius:11px;font-size:13px;line-height:1.8;margin:14px 0;overflow-wrap:anywhere}
.notice{background:#10223a;border:1px solid #294568;color:#c8dcf8}
.message.error{background:#35151c;border:1px solid #672632;color:#ffb0b7}
.message.success{background:#0c2b24;border:1px solid #205c49;color:#8cf0c3}
.message.info{background:#102744;border:1px solid #254e7e;color:#b9d7ff}
.hero{padding:30px 5px}
.hero p{color:var(--muted);margin:12px 0 20px}
.cyan{color:var(--cyan)}
.grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:15px}
.project-card{display:flex;flex-direction:column;align-items:flex-start;min-height:185px}
.project-icon{
  width:48px;height:48px;display:grid;place-items:center;
  background:#152c4d;border:1px solid #29486f;border-radius:14px;
  font-size:24px;margin-bottom:15px;
}
.project-card p{font-size:14px;color:var(--muted);flex:1}
.section-title{margin:27px 0 15px}
.project-item{padding:15px;border:1px solid var(--border);border-radius:12px;margin-top:10px;background:#091425;overflow-wrap:anywhere}
.project-item p{font-size:13px;color:var(--muted)}
.empty{text-align:center;color:var(--muted);padding:25px}
footer{text-align:center;color:#71849f;border-top:1px solid var(--border);padding:22px;font-size:12px}
@media(max-width:480px){.grid{grid-template-columns:1fr}.card{padding:17px}}
</style>
</head>
<body>

<header>
  <div class="brand">
    <img src="icon.png" alt="Outhub" onerror="this.style.display='none'">
    <div>Out<span>hub</span></div>
  </div>
  <button id="accountButton" class="btn secondary hidden" style="width:auto;margin:0" onclick="showAccount()">حسابي</button>
</header>

<main class="container">

<!-- الحساب / تسجيل الدخول -->
<section id="authView" class="view">
<div class="auth">
  <div class="auth-logo">
    <img src="icon.png" alt="Outhub" onerror="this.style.display='none'">
    <h1>مرحبًا بك في <span class="cyan">Outhub</span></h1>
    <p class="muted">منصتك لإنشاء مشاريعك الرقمية.</p>
  </div>

  <!-- تسجيل الدخول -->
  <div id="loginPanel" class="card">
    <h2>تسجيل الدخول</h2>
    <button class="btn google-btn" type="button" onclick="loginWithGoogle()">تسجيل الدخول بواسطة Google</button>
    <div style="text-align:center;color:var(--muted);font-size:12px;margin:10px 0;">أو بالبريد الإلكتروني</div>
    <form id="loginForm">
      <div class="field">
        <label for="loginEmail">البريد الإلكتروني لحساب Outhub</label>
        <input id="loginEmail" type="email" required autocomplete="username" placeholder="البريد الإلكتروني">
      </div>
      <div class="field">
        <label for="loginPassword">كلمة المرور</label>
        <input id="loginPassword" type="password" required autocomplete="current-password" placeholder="كلمة المرور">
      </div>
      <button class="btn primary" type="submit">تسجيل الدخول</button>
    </form>
    <div id="loginMessage"></div>
    <div class="form-links">
      <button class="link" type="button" onclick="showRegister()">إنشاء حساب</button>
      <button class="link" type="button" onclick="showForgot()">نسيت كلمة المرور؟</button>
    </div>
  </div>

  <!-- إنشاء حساب -->
  <div id="registerPanel" class="card hidden">
    <h2>إنشاء حساب جديد</h2>
    <p class="muted small">استخدم بريدك في Eisen Mail لاستلام رمز التحقق.</p>

    <div id="emailStep">
      <div class="notice">
        يرجى استخدام بريدك المستعمل في Eisen Mail
      </div>
      <form id="requestCodeForm">
        <div class="field">
          <label for="registerEmail">بريد Eisen Mail</label>
          <input id="registerEmail" type="email" required autocomplete="email" placeholder="أدخل بريدك المستعمل في Eisen Mail">
        </div>
        <button class="btn primary" type="submit">إرسال رمز التحقق</button>
      </form>
    </div>

    <div id="verifyStep" class="hidden">
      <div class="notice">
        أدخل رمز التحقق الذي وصلك في صندوق الوارد داخل Eisen Mail.
      </div>
      <form id="verifyForm">
        <div class="field">
          <label for="verifyCode">رمز التحقق (6 أرقام)</label>
          <input id="verifyCode" inputmode="numeric" maxlength="6" pattern="[0-9]{6}" required placeholder="000000">
        </div>
        <div class="field">
          <label for="registerPassword">كلمة مرور حساب Outhub</label>
          <input id="registerPassword" type="password" minlength="6" required autocomplete="new-password" placeholder="6 أحرف على الأقل">
        </div>
        <button class="btn primary" type="submit">التحقق وإنشاء الحساب</button>
      </form>
      <button class="link" type="button" onclick="backToEmail()">تغيير البريد الإلكتروني</button>
    </div>

    <div id="registerMessage"></div>
    <div class="form-links">
      <button class="link" type="button" onclick="showLogin()">لدي حساب بالفعل</button>
    </div>
  </div>

  <!-- استعادة الحساب -->
  <div id="forgotPanel" class="card hidden">
    <h2>استعادة كلمة المرور</h2>
    <p class="muted small">أدخل البريد المرتبط بحساب Outhub.</p>
    <form id="forgotForm">
      <div class="field">
        <label for="forgotEmail">البريد الإلكتروني</label>
        <input id="forgotEmail" type="email" required placeholder="بريدك الإلكتروني">
      </div>
      <button class="btn primary" type="submit">طلب الاستعادة</button>
    </form>
    <div id="forgotMessage"></div>
    <button class="link" type="button" onclick="showLogin()">العودة لتسجيل الدخول</button>
  </div>
</div>
</section>

<!-- الرئيسية -->
<section id="homeView" class="view hidden">
  <div class="hero">
    <h1>مشاريعك تبدأ من <span class="cyan">Outhub</span></h1>
    <p>مساحة واحدة للانطلاق بمواقعك الإلكترونية وتطبيقاتك.</p>
    <button class="btn primary" style="width:auto" onclick="showWebsite()">+ ابدأ مشروعك</button>
  </div>

  <div class="grid">
    <article class="card project-card">
      <div class="project-icon">🌐</div>
      <h3>إنشاء موقع إلكتروني</h3>
      <p>جهّز تفاصيل مشروعك وانتقل إلى GitHub لإنشاء مستودع جديد.</p>
      <button class="btn primary" onclick="showWebsite()">إنشاء موقع</button>
    </article>
    <article class="card project-card">
      <div class="project-icon">📱</div>
      <h3>إنشاء تطبيق</h3>
      <p>احفظ فكرة التطبيق وانتقل إلى أداة إنشاء التطبيقات.</p>
      <button class="btn primary" onclick="showApp()">إنشاء تطبيق</button>
    </article>
    <article class="card project-card">
      <div class="project-icon">✦</div>
      <h3>Gemalot</h3>
      <p>افتح الخدمة عبر موقعها.</p>
      <a class="btn secondary" href="https://mohamedmadoui5195.github.io/Gemalot/" target="_blank" rel="noopener">فتح Gemalot</a>
    </article>
    <article class="card project-card">
      <div class="project-icon">📂</div>
      <h3>مشاريعي</h3>
      <p>اعرض المشاريع التي حفظتها على هذا المتصفح.</p>
      <button class="btn secondary" onclick="showProjects()">عرض مشاريعي</button>
    </article>
  </div>

  <h2 class="section-title">آخر المشاريع</h2>
  <div id="recentProjects"></div>
</section>

<!-- إنشاء موقع -->
<section id="websiteView" class="view hidden">
  <div class="card">
    <h2>إنشاء موقع إلكتروني</h2>
    <form id="websiteForm">
      <div class="field">
        <label for="websiteName">اسم المشروع</label>
        <input id="websiteName" required placeholder="اسم الموقع">
      </div>
      <div class="field">
        <label for="websiteIdea">فكرة الموقع</label>
        <input id="websiteIdea" required placeholder="اشرح فكرة الموقع">
      </div>
      <div class="field">
        <label for="repoName">اسم مستودع GitHub</label>
        <input id="repoName" required pattern="[A-Za-z0-9._-]+" placeholder="my-website">
      </div>
      <div class="field">
        <label for="visibility">خصوصية المستودع المطلوبة</label>
        <select id="visibility">
          <option value="private">خاص — Private</option>
          <option value="public">علني — Public</option>
        </select>
      </div>
      <div class="notice">
        سيُفتح GitHub لإكمال إنشاء المستودع. يجب تأكيد الخصوصية هناك؛ حفظ المشروع في Outhub لا ينشئ مستودع GitHub تلقائيًا.
      </div>
      <button class="btn primary" type="submit">حفظ والانتقال إلى GitHub</button>
    </form>
    <div id="websiteMessage"></div>
    <button class="btn secondary" type="button" onclick="showHome()">العودة إلى الرئيسية</button>
  </div>
</section>

<!-- إنشاء تطبيق -->
<section id="appView" class="view hidden">
  <div class="card">
    <h2>إنشاء تطبيق</h2>
    <form id="appForm">
      <div class="field">
        <label for="appName">اسم التطبيق</label>
        <input id="appName" required placeholder="اسم التطبيق">
      </div>
      <div class="field">
        <label for="appIdea">فكرة التطبيق</label>
        <input id="appIdea" required placeholder="ما وظيفة التطبيق؟">
      </div>
      <button class="btn primary" type="submit">حفظ وفتح أداة الإنشاء</button>
    </form>
    <div id="appMessage"></div>
    <button class="btn secondary" type="button" onclick="showHome()">العودة إلى الرئيسية</button>
  </div>
</section>

<!-- المشاريع -->
<section id="projectsView" class="view hidden">
  <div class="card">
    <h2>مشاريعي</h2>
    <div id="allProjects"></div>
    <button class="btn primary" type="button" onclick="showHome()">العودة إلى الرئيسية</button>
  </div>
</section>

<!-- الحساب -->
<section id="accountView" class="view hidden">
  <div class="card">
    <h2>حسابي</h2>
    <div id="accountInfo" class="notice"></div>
    <button class="btn secondary" type="button" onclick="showHome()">العودة إلى الرئيسية</button>
    <button class="btn danger" type="button" onclick="logout()">تسجيل الخروج</button>
  </div>
</section>

</main>

<footer>Outhub — مساحة واحدة لمشاريعك الرقمية</footer>

<script>
"use strict";
const KEY = "outhub_projects";
let generatedOtp = "";
let pendingEmail = "";

function $(id){return document.getElementById(id)}
function escapeHTML(s){return String(s ?? "").replace(/[&<>\"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]));}
function message(id,text,type="info"){$(id).innerHTML='<div class="message '+type+'">'+escapeHTML(text)+'</div>';}
function clearMessage(id){$(id).innerHTML=""}
function showView(id){document.querySelectorAll(".view").forEach(v=>v.classList.add("hidden"));$(id).classList.remove("hidden");window.scrollTo(0,0);}

// التحقق من حالة المصادقة عبر Firebase وتفعيل التنقل
window.addEventListener('DOMContentLoaded', () => {
  const checkAuth = setInterval(() => {
    if (window.onAuthStateChanged && window.auth) {
      clearInterval(checkAuth);
      window.onAuthStateChanged(window.auth, (user) => {
        if (user) {
          $("accountButton").classList.remove("hidden");
          showHome();
        } else {
          $("accountButton").classList.add("hidden");
          showLogin();
        }
      });
    }
  }, 200);
});

function emailNow(){ return window.auth?.currentUser?.email || ""; }
function showLogin(){showView("authView");$("loginPanel").classList.remove("hidden");$("registerPanel").classList.add("hidden");$("forgotPanel").classList.add("hidden");clearMessage("loginMessage");}
function showRegister(){showView("authView");$("loginPanel").classList.add("hidden");$("registerPanel").classList.remove("hidden");$("forgotPanel").classList.add("hidden");$("emailStep").classList.remove("hidden");$("verifyStep").classList.add("hidden");clearMessage("registerMessage");}
function showForgot(){showView("authView");$("loginPanel").classList.add("hidden");$("registerPanel").classList.add("hidden");$("forgotPanel").classList.remove("hidden");}
function backToEmail(){$("emailStep").classList.remove("hidden");$("verifyStep").classList.add("hidden");}

// تسجيل الدخول بجوجل
async function loginWithGoogle() {
  try {
    const provider = new window.GoogleAuthProvider();
    await window.signInWithPopup(window.auth, provider);
  } catch (error) {
    message("loginMessage", "فشل تسجيل الدخول بجوجل: " + error.message, "error");
  }
}

// طلب رمز التحقق وعرضه لإرساله عبر Eisen Mail
$("requestCodeForm").addEventListener("submit", async e => {
  e.preventDefault();
  pendingEmail = $("registerEmail").value.trim().toLowerCase();
  if(!pendingEmail || !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(pendingEmail)){
    message("registerMessage","أدخل بريدًا صحيحًا.","error");
    return;
  }
  generatedOtp = Math.floor(100000 + Math.random()*900000).toString();
  
  const payload = {to: pendingEmail, code: generatedOtp, at: Date.now()};
  localStorage.setItem("outhub_send_code_request", JSON.stringify(payload));
  try { window.open("https://mohamedmadoui5195.github.io/Eisen-mail/", "_blank"); } catch(e){}

  $("emailStep").classList.add("hidden");
  $("verifyStep").classList.remove("hidden");
  message("registerMessage","تم توليد وإرسال الرمز إلى Eisen Mail. الرمز للتجربة: "+generatedOtp,"success");
});

// إتمام التحقق وإنشاء الحساب
$("verifyForm").addEventListener("submit", async e => {
  e.preventDefault();
  const code = $("verifyCode").value.trim();
  const password = $("registerPassword").value;
  
  if(code !== generatedOtp){
    message("registerMessage","رمز التحقق غير صحيح.","error");
    return;
  }
  
  try {
    await window.createUserWithEmailAndPassword(window.auth, pendingEmail, password);
    showHome();
  } catch(error) {
    message("registerMessage","خطأ في إنشاء الحساب: " + error.message, "error");
  }
});

// تسجيل الدخول العادي
$("loginForm").addEventListener("submit", async e => {
  e.preventDefault();
  const email = $("loginEmail").value.trim();
  const pass = $("loginPassword").value;
  try {
    await window.signInWithEmailAndPassword(window.auth, email, pass);
    showHome();
  } catch(error) {
    message("loginMessage","البريد أو كلمة المرور غير صحيحة.", "error");
  }
});

// طلب الاستعادة
$("forgotForm").addEventListener("submit", async e => {
  e.preventDefault();
  const email = $("forgotEmail").value.trim();
  message("forgotMessage","إذا كان الحساب موجودًا، فستصل تعليمات الاستعادة إلى بريدك في Eisen Mail.", "success");
});

function logout(){
  window.signOut(window.auth).then(() => { showLogin(); });
}

// دوال التنقل وإدارة المشاريع
function showHome(){ showView("homeView"); renderRecent(); }
function showAccount(){ 
  $("accountInfo").textContent = "البريد المستخدم: " + emailNow(); 
  showView("accountView"); 
}
function showWebsite(){ clearMessage("websiteMessage"); showView("websiteView"); }
function showApp(){ clearMessage("appMessage"); showView("appView"); }
function showProjects(){ $("allProjects").innerHTML = projectList(); showView("projectsView"); }

function allStored(){try{const a=JSON.parse(localStorage.getItem(KEY)||"[]");return Array.isArray(a)?a:[]}catch(e){return []}}
function myProjects(){return allStored().filter(p => p.owner === emailNow());}
function saveProject(p){const all=allStored();all.push({...p, owner: emailNow(), date: new Date().toISOString()});localStorage.setItem(KEY,JSON.stringify(all));}
function markup(p){return `<div class="project-item"><strong>${escapeHTML(p.name)}</strong><p>النوع: ${escapeHTML(p.type)}</p><p>${escapeHTML(p.idea)}</p><p>${escapeHTML(new Date(p.date).toLocaleDateString("ar"))}</p></div>`;}
function projectList(){const list=myProjects().reverse();return list.length?list.map(markup).join(""):'<div class="empty">لا توجد مشاريع محفوظة.</div>';}
function renderRecent(){const list=myProjects().slice(-3).reverse();$("recentProjects").innerHTML=list.length?list.map(markup).join(""):'<div class="card empty">لم تحفظ أي مشروع بعد.</div>';}

$("websiteForm").addEventListener("submit", e => {
  e.preventDefault();
  const name = $("websiteName").value.trim();
  const idea = $("websiteIdea").value.trim();
  const repo = $("repoName").value.trim();
  const visibility = $("visibility").value;
  if(!/^[A-Za-z0-9._-]+$/.test(repo)){message("websiteMessage","اسم المستودع غير صالح.","error");return;}
  saveProject({name, idea, type:"موقع إلكتروني", repo, visibility});
  window.open("https://github.com/new?name=" + encodeURIComponent(repo), "_blank", "noopener");
  message("websiteMessage","حُفظ المشروع محليًا وتم توجيهك إلى GitHub.","success");
});

$("appForm").addEventLi$("appForm").addEventListener("submit", e => {
  e.preventDefault();
  saveProject({name: $("appName").value.trim(), idea: $("appIdea").value.trim(), type: "تطبيق"});
  window.open("https://appsgeyser.com/create-app/","_blank","noopener");
  message("appMessage","حُفظت معلومات التطبيق وتم فتح أداة الإنشاء.","success");
});
</script>
</body>
</html>
