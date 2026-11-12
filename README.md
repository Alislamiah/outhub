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
    GithubAuthProvider, 
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
  window.GithubAuthProvider = GithubAuthProvider;
  window.signInWithPopup = signInWithPopup;
  window.signInWithEmailAndPassword = signInWithEmailAndPassword;
  window.createUserWithEmailAndPassword = createUserWithEmailAndPassword;
  window.signOut = signOut;
  window.onAuthStateChanged = onAuthStateChanged;

  window.loginWithGitHub = async function() {
    try {
      const provider = new GithubAuthProvider();
      await signInWithPopup(auth, provider);
    } catch (error) {
      if (typeof window.message === "function") {
        window.message("loginMessage", "فشل تسجيل الدخول بـ GitHub: " + error.message, "error");
      } else {
        alert("خطأ أثناء تسجيل الدخول بـ GitHub: " + error.message);
      }
    }
  };
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
.github-btn{background:#24292e;color:white;margin-bottom:10px}
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
.project-item{
  padding:15px;border:1px solid var(--border);border-radius:12px;margin-top:10px;
  background:#091425;overflow-wrap:anywhere;cursor:pointer;transition:border-color .15s,background .15s;
}
.project-item:hover{border-color:var(--blue);background:#0d1a2e}
.project-item p{font-size:13px;color:var(--muted)}
.empty{text-align:center;color:var(--muted);padding:25px}
footer{text-align:center;color:#71849f;border-top:1px solid var(--border);padding:22px;font-size:12px}
.code-space-wrap{
  margin:18px 0;border:1px solid var(--border);border-radius:14px;overflow:hidden;
  background:#050e1d;min-height:420px;position:relative;
}
.code-space-wrap iframe{width:100%;height:520px;border:0;display:block;background:#0d1117}
.code-toolbar{
  display:flex;flex-wrap:wrap;gap:10px;align-items:center;padding:12px 14px;
  background:#0a1628;border-bottom:1px solid var(--border);
}
.code-toolbar input{flex:1;min-width:140px;padding:10px 12px;margin:0}
.code-toolbar .btn{width:auto;margin:0;padding:10px 14px}
.project-meta{display:flex;flex-wrap:wrap;gap:12px;margin:12px 0 18px;font-size:13px;color:var(--muted)}
.project-meta span{background:#152c4d;padding:6px 12px;border-radius:8px;border:1px solid #29486f}
@media(max-width:480px){
  .grid{grid-template-columns:1fr}
  .card{padding:17px}
  .code-space-wrap iframe{height:380px}
}
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

<section id="authView" class="view">
<div class="auth">
  <div class="auth-logo">
    <img src="icon.png" alt="Outhub" onerror="this.style.display='none'">
    <h1>مرحبًا بك في <span class="cyan">Outhub</span></h1>
    <p class="muted">منصتك لإنشاء مشاريعك الرقمية.</p>
  </div>

  <div id="loginPanel" class="card">
    <h2>تسجيل الدخول</h2>
    <button class="btn github-btn" type="button" onclick="loginWithGitHub()">تسجيل الدخول بواسطة GitHub</button>
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

  <div id="registerPanel" class="card hidden">
    <h2>إنشاء حساب جديد</h2>
    <p class="muted small">استخدم بريدك في Eisen Mail لاستلام رمز التحقق.</p>

    <div id="emailStep">
      <div class="notice">يرجى استخدام بريدك المستعمل في Eisen Mail</div>
      <form id="requestCodeForm">
        <div class="field">
          <label for="registerEmail">بريد Eisen Mail</label>
          <input id="registerEmail" type="email" required autocomplete="email" placeholder="أدخل بريدك المستعمل في Eisen Mail">
        </div>
        <button class="btn primary" type="submit">إرسال رمز التحقق</button>
      </form>
    </div>

    <div id="verifyStep" class="hidden">
      <div class="notice">أدخل رمز التحقق الذي وصلك في صندوق الوارد داخل Eisen Mail.</div>
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

<section id="homeView" class="view hidden">
  <div class="hero">
    <h1>مشاريعك تبدأ من <span class="cyan">Outhub</span></h1>
    <p>مساحة واحدة للانطلاق بمواقعك الإلكترونية وتطبيقاتك.</p>


<article class="card project-card">
  <div class="project-icon">💻</div>
  <h3>تعلم البرمجة مع مداد</h3>
  <p>هل تريد تعلم البرمجة؟ تعلم تنظيم وكتابة أكوادك باحترافية مع مداد.</p>
  <button class="btn primary" onclick="openMedad()">
    <img src="icon.jpg" alt="Alislamiah"
         style="width:20px;height:20px;object-fit:contain;vertical-align:middle;margin-left:8px">
    الانتقال إلى مداد
  </button>
</article>

<script>
function openMedad(){
  window.location.href = "medad.html";
}
</script>


    <button class="btn primary" style="width:auto" onclick="showWebsite()">+ ابدأ مشروعك</button>
  </div>
  <div class="grid">
    <article class="card project-card">
      <div class="project-icon">🌐</div>
      <h3>إنشاء موقع إلكتروني</h3>
      <p>أنشئ مشروعك مباشرة داخل Outhub واحصل على رابط حي فوري (مثل GitHub Pages).</p>
      <button class="btn primary" onclick="showWebsite()">إنشاء موقع</button>
    </article>
    <article class="card project-card">
      <div class="project-icon">📱</div>
      <h3>إنشاء تطبيق</h3>
      <p>احفظ فكرة التطبيق داخل المنصة واحصل على رابط خاص به.</p>
      <button class="btn primary" onclick="showApp()">إنشاء تطبيق</button>
    </article>
    <article class="card project-card">
      <div class="project-icon">✦</div>
      <h3>Gemalot</h3>
      <p>افتح الخدمة عبر موقعها.</p>
      <a class="btn secondary" href="https://Alislamiah.github.io/Gemalot/" target="_blank" rel="noopener">فتح Gemalot</a>
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

<section id="websiteView" class="view hidden">
  <div class="card">
    <h2>إنشاء موقع إلكتروني</h2>
    <form id="websiteForm">
      <div class="field"><label for="websiteName">اسم المشروع</label><input id="websiteName" required placeholder="اسم الموقع"></div>
      <div class="field"><label for="websiteIdea">فكرة الموقع</label><input id="websiteIdea" required placeholder="اشرح فكرة الموقع"></div>
      <div class="field"><label for="repoName">اسم المشروع (للرابط)</label><input id="repoName" required pattern="[A-Za-z0-9._-]+" placeholder="my-website"></div>
      <div class="field"><label for="visibility">خصوصية المشروع</label><select id="visibility"><option value="private">خاص — Private</option><option value="public">علني — Public</option></select></div>
      <div class="notice">سيتم إنشاء المشروع مباشرة داخل Outhub وتوليد رابط حي له (مثل GitHub Pages) دون الحاجة إلى GitHub.</div>
      <button class="btn primary" type="submit">إنشاء المشروع والحصول على الرابط الحي</button>
    </form>
    <div id="websiteMessage"></div>
    <button class="btn secondary" type="button" onclick="showHome()">العودة إلى الرئيسية</button>
  </div>
</section>

<section id="appView" class="view hidden">
  <div class="card">
    <h2>إنشاء تطبيق</h2>
    <form id="appForm">
      <div class="field"><label for="appName">اسم التطبيق</label><input id="appName" required placeholder="اسم التطبيق"></div>
      <div class="field"><label for="appIdea">فكرة التطبيق</label><input id="appIdea" required placeholder="ما وظيفة التطبيق؟"></div>
      <button class="btn primary" type="submit">حفظ وفتح أداة الإنشاء</button>
    </form>
    <div id="appMessage"></div>
    <button class="btn secondary" type="button" onclick="showHome()">العودة إلى الرئيسية</button>
  </div>
</section>

<section id="projectsView" class="view hidden">
  <div class="card">
    <h2>مشاريعي</h2>
    <div id="allProjects"></div>
    <button class="btn primary" type="button" onclick="showHome()">العودة إلى الرئيسية</button>
  </div>
</section>

<!-- واجهة تفاصيل المشروع — مساحة عمل الملفات مثل GitHub -->
<section id="projectView" class="view hidden">
  <div class="card">
    <h2 id="projectTitle">عنوان المشروع</h2>
    <p id="projectDesc" class="muted" style="margin-bottom:8px"></p>
    <div class="project-meta" id="projectMeta"></div>

    <!-- أزرار الإجراءات -->
    <div style="display:flex;flex-wrap:wrap;gap:10px;margin:16px 0">
      <button class="btn primary" type="button" style="width:auto;margin:0" onclick="showCreateFilePanel()">＋ Create file</button>
      <button class="btn secondary" type="button" style="width:auto;margin:0" onclick="showUploadPanel()">⬆ Upload file</button>
      <button class="btn secondary" type="button" style="width:auto;margin:0" onclick="copyLiveUrl()">نسخ الرابط الحي</button>
    </div>

    <!-- لوحة إنشاء ملف -->
    <div id="createFilePanel" class="hidden" style="margin:14px 0;padding:16px;border:1px solid var(--border);border-radius:12px;background:#091425">
      <h3 style="margin-bottom:12px">Create file</h3>
      <div class="field">
        <label for="newFileName">اسم الملف (مثال: index.html أو style.css)</label>
        <input id="newFileName" type="text" placeholder="index.html" autocomplete="off">
      </div>
      <div class="field">
        <label for="newFileCode">الكود / المحتوى</label>
        <textarea id="newFileCode" rows="10" style="width:100%;padding:14px;border:1px solid #2a3e5b;border-radius:11px;background:#050e1d;color:white;outline:none;font-family:monospace;resize:vertical" placeholder="ضع الكود هنا..."></textarea>
      </div>
      <div style="display:flex;gap:10px;flex-wrap:wrap">
        <button class="btn primary" type="button" style="width:auto;margin:0" onclick="createFileInProject()">Create</button>
        <button class="btn secondary" type="button" style="width:auto;margin:0" onclick="hideCreateFilePanel()">إلغاء</button>
      </div>
      <div id="createFileMessage"></div>
    </div>

    <!-- لوحة رفع ملف -->
    <div id="uploadPanel" class="hidden" style="margin:14px 0;padding:16px;border:1px solid var(--border);border-radius:12px;background:#091425">
      <h3 style="margin-bottom:12px">Upload file</h3>
      <p class="muted small" style="margin-bottom:12px">Upload from:</p>
      <div style="display:flex;flex-wrap:wrap;gap:8px;margin-bottom:14px">
        <button class="btn secondary" type="button" style="width:auto;margin:0" onclick="window.open('https://Alislamiah.github.io/Bingot/','_blank')">Bingot</button>
        <button class="btn secondary" type="button" style="width:auto;margin:0" onclick="window.open('https://Alislamiah.github.io/MGA-Code-Editor/','_blank')">MGA Code Editor</button>
        <button class="btn secondary" type="button" style="width:auto;margin:0" onclick="triggerDeviceUpload()">Default files / File manager / Galerie / Google photos / OneDrive</button>
      </div>
      <input type="file" id="deviceFileInput" class="hidden" multiple accept="*/*" onchange="handleDeviceFiles(event)">
      <div class="notice small">يمكنك اختيار ملفات من جهازك (مدير الملفات، المعرض، Google Drive، OneDrive... عبر منتقي النظام).</div>
      <button class="btn secondary" type="button" style="width:auto;margin-top:10px" onclick="hideUploadPanel()">إغلاق</button>
      <div id="uploadMessage"></div>
    </div>

    <!-- قائمة الملفات -->
    <h3 style="margin:18px 0 10px">ملفات المشروع</h3>
    <div id="projectFilesList" style="margin-bottom:16px"></div>

    <!-- محرر / عارض الكود -->
    <div id="codeEditorSection" class="hidden">
      <h3 id="currentFileTitle" style="margin-bottom:8px">الملف</h3>
      <textarea id="codeEditor" rows="14" style="width:100%;padding:14px;border:1px solid #2a3e5b;border-radius:11px;background:#050e1d;color:#e6edf3;outline:none;font-family:monospace;font-size:13px;resize:vertical;direction:ltr;text-align:left"></textarea>
      <div style="display:flex;gap:10px;flex-wrap:wrap;margin-top:10px">
        <button class="btn primary" type="button" style="width:auto;margin:0" onclick="saveCurrentFile()">حفظ الملف</button>
        <button class="btn secondary" type="button" style="width:auto;margin:0" onclick="refreshPreview()">تحديث المعاينة</button>
        <button class="btn danger" type="button" style="width:auto;margin:0" onclick="deleteCurrentFile()">حذف الملف</button>
      </div>
      <div id="editorMessage"></div>
    </div>

    <!-- معاينة حية -->
    <div id="embedSection" style="margin-top:20px">
      <h3 id="embedTitle">معاينة الموقع الحي</h3>
      <p id="embedHint" class="muted small" style="margin-bottom:10px"></p>
      <div class="code-space-wrap">
        <iframe id="embedFrame" title="معاينة المشروع" sandbox="allow-scripts allow-same-origin allow-popups allow-forms allow-downloads allow-top-navigation-by-user-activation" src="about:blank"></iframe>
      </div>
      <div id="embedMessage"></div>
      <p id="publishHint" class="muted small" style="margin-top:8px">الرابط الحي يفتح المشروع مباشرة داخل Outhub. يعمل على نفس المتصفح/الجهاز الذي أُنشئ فيه المشروع (التخزين محلي).</p>
    </div>

    <button class="btn secondary" type="button" onclick="showProjects()" style="margin-top:16px">العودة إلى مشاريعي</button>
    <button class="btn secondary" type="button" onclick="showHome()">العودة إلى الرئيسية</button>
  </div>
</section>

<section id="accountView" class="view hidden">
  <div class="card"><h2>حسابي</h2><div id="accountInfo" class="notice"></div><button class="btn secondary" type="button" onclick="showHome()">العودة إلى الرئيسية</button><button class="btn danger" type="button" onclick="logout()">تسجيل الخروج</button></div>
</section>

</main>

<footer>Outhub — مساحة واحدة لمشاريعك الرقمية</footer>

<script>
"use strict";
const KEY = "outhub_projects";
const GITHUB_USER_KEY = "outhub_github_user";
let generatedOtp = "";
let pendingEmail = "";
let currentProject = null;

/* ===== OuthubEngine — محرك المشاريع (مثل GitHub) ===== */
class OuthubEngine {
    constructor() {
        // محاكاة أو ربط قاعدة بيانات/التخزين المحلي لإدارة مشاريع المستخدمين
        this.currentUser = localStorage.getItem("outhub_active_user") || "guest";
    }

    setUser(username) {
        const clean = String(username || "guest").toLowerCase().trim().replace(/[^a-z0-9]/g, '') || "guest";
        this.currentUser = clean;
        localStorage.setItem("outhub_active_user", clean);
    }

    // المستخدم ينشئ مشروعاً جديداً بنفسه (مثل Repository جديد)
    createProject(projectName, filesData) {
        const cleanProject = projectName.toLowerCase().trim().replace(/[^a-z0-9]/g, '');
        
        // هيكل حفظ الملفات الخاص بالمستخدم داخل المنصة
        const projectKey = `outhub_project_${this.currentUser}_${cleanProject}`;
        
        const projectData = {
            owner: this.currentUser,
            name: cleanProject,
            files: filesData, // ملفات الـ HTML, CSS وغيرها
            updatedAt: new Date().toISOString()
        };

        localStorage.setItem(projectKey, JSON.stringify(projectData));
        
        // توليد الرابط النهائي للمستخدم بالهيكل الاحترافي المطلوب
        return this.generateLiveUrl(this.currentUser, cleanProject);
    }

    // توليد رابط حي يعمل فعليًا داخل موقع Outhub
    generateLiveUrl(username, projectName) {
        // رابط حقيقي يفتح داخل نفس الموقع ويعرض المشروع
        // مثال: https://Alislamiah.github.io/outhub/?u=username&p=projectname
        const u = encodeURIComponent(username || "guest");
        const p = encodeURIComponent(projectName || "project");
        return `https://Alislamiah.github.io/outhub/?u=${u}&p=${p}`;
    }

    // جلب كل مشاريع المستخدم الحالي من التخزين
    listProjects() {
        const prefix = `outhub_project_${this.currentUser}_`;
        const list = [];
        for (let i = 0; i < localStorage.length; i++) {
            const key = localStorage.key(i);
            if (key && key.startsWith(prefix)) {
                try {
                    const data = JSON.parse(localStorage.getItem(key));
                    if (data && data.name) list.push(data);
                } catch (e) {}
            }
        }
        return list.sort((a, b) => (b.updatedAt || "").localeCompare(a.updatedAt || ""));
    }

    // جلب مشروع واحد
    getProject(projectName) {
        const clean = projectName.toLowerCase().trim().replace(/[^a-z0-9]/g, '');
        const key = `outhub_project_${this.currentUser}_${clean}`;
        try {
            return JSON.parse(localStorage.getItem(key) || "null");
        } catch (e) {
            return null;
        }
    }

    // إضافة أو تحديث ملف داخل المشروع
    addFile(projectName, fileName, content) {
        const proj = this.getProject(projectName);
        if (!proj) return false;
        const cleanFile = String(fileName || "").trim().replace(/[\/\\]/g, "_");
        if (!cleanFile) return false;
        if (!proj.files) proj.files = {};
        proj.files[cleanFile] = content;
        proj.updatedAt = new Date().toISOString();
        const key = `outhub_project_${this.currentUser}_${proj.name}`;
        localStorage.setItem(key, JSON.stringify(proj));
        return true;
    }

    // حذف ملف
    deleteFile(projectName, fileName) {
        const proj = this.getProject(projectName);
        if (!proj || !proj.files) return false;
        delete proj.files[fileName];
        proj.updatedAt = new Date().toISOString();
        const key = `outhub_project_${this.currentUser}_${proj.name}`;
        localStorage.setItem(key, JSON.stringify(proj));
        return true;
    }
}

const engine = new OuthubEngine();

function $(id){return document.getElementById(id)}
function escapeHTML(s){return String(s ?? "").replace(/[&<>\"'"]/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]));}
function message(id,text,type="info"){
  const el = $(id);
  if (el) el.innerHTML='<div class="message '+type+'">'+escapeHTML(text)+'</div>';
}
window.message = message;
function clearMessage(id){const el = $(id); if (el) el.innerHTML=""}
function showView(id){document.querySelectorAll(".view").forEach(v=>v.classList.add("hidden"));$(id).classList.remove("hidden");window.scrollTo(0,0);}

// قراءة معاملات الرابط الحي ?u=username&p=project
function getUrlProjectParams(){
  try {
    const params = new URLSearchParams(window.location.search);
    const u = (params.get("u") || "").trim().toLowerCase().replace(/[^a-z0-9]/g, "");
    const p = (params.get("p") || "").trim().toLowerCase().replace(/[^a-z0-9]/g, "");
    if(u && p) return { user: u, project: p };
  } catch(e){}
  return null;
}

// فتح مشروع من الرابط الحي (يعمل حتى لزائر غير مسجل إن وُجدت البيانات محليًا)
function openProjectFromUrl(){
  const params = getUrlProjectParams();
  if(!params) return false;

  // محاولة جلب المشروع من مفتاح المحرك مباشرة
  const key = `outhub_project_${params.user}_${params.project}`;
  let engData = null;
  try { engData = JSON.parse(localStorage.getItem(key) || "null"); } catch(e){}

  if(engData && engData.files){
    // نعرض المشروع كمعاينة عامة
    currentProject = {
      id: "url_" + params.project,
      name: engData.name || params.project,
      idea: engData.idea || "",
      type: engData.type || "موقع إلكتروني",
      repo: engData.name || params.project,
      date: engData.updatedAt || new Date().toISOString(),
      liveUrl: engine.generateLiveUrl(params.user, params.project),
      files: engData.files,
      owner: params.user,
      engine: true
    };
    // تعيين المستخدم مؤقتًا ليعمل المحرك
    engine.setUser(params.user);
    showProject(currentProject.id);
    // تنظيف شريط العنوان اختياريًا (نحافظ على الرابط ليبقى قابلاً للمشاركة)
    return true;
  }

  // إن لم يُوجد المشروع محليًا نعرض رسالة واضحة
  showView("homeView");
  setTimeout(() => {
    const box = $("recentProjects");
    if(box){
      box.innerHTML = `<div class="card">
        <h3>الرابط الحي</h3>
        <p class="muted">المستخدم: <strong>${escapeHTML(params.user)}</strong> — المشروع: <strong>${escapeHTML(params.project)}</strong></p>
        <div class="notice" style="margin-top:12px">
          هذا المشروع غير متوفر على هذا المتصفح.<br>
          الروابط الحية في Outhub تعتمد على التخزين المحلي للمتصفح الذي أُنشئ فيه المشروع.
          افتح الرابط من نفس الجهاز/المتصفح الذي أنشأتَ فيه المشروع لعرضه.
        </div>
      </div>`;
    }
  }, 300);
  return true;
}

window.addEventListener('DOMContentLoaded', () => {
  const checkAuth = setInterval(() => {
    if (window.onAuthStateChanged && window.auth) {
      clearInterval(checkAuth);
      window.onAuthStateChanged(window.auth, (user) => {
        if (user) {
          // تعيين المستخدم في محرك المشاريع من البريد (جزء قبل @)
          const uname = (user.email || "guest").split("@")[0];
          engine.setUser(uname);
          $("accountButton").classList.remove("hidden");
          // إن وُجد رابط حي نفتح المشروع، وإلا الرئيسية
          if(!openProjectFromUrl()) showHome();
        } else {
          engine.setUser("guest");
          $("accountButton").classList.add("hidden");
          // حتى بدون تسجيل دخول نحاول فتح الرابط الحي
          if(!openProjectFromUrl()) showLogin();
        }
      });
    }
  }, 200);
});

function emailNow(){ return window.auth?.currentUser?.email || ""; }
function usernameNow(){ return engine.currentUser || "guest"; }
function showLogin(){showView("authView");$("loginPanel").classList.remove("hidden");$("registerPanel").classList.add("hidden");$("forgotPanel").classList.add("hidden");clearMessage("loginMessage");}
function showRegister(){showView("authView");$("loginPanel").classList.add("hidden");$("registerPanel").classList.remove("hidden");$("forgotPanel").classList.add("hidden");$("emailStep").classList.remove("hidden");$("verifyStep").classList.add("hidden");clearMessage("registerMessage");}
function showForgot(){showView("authView");$("loginPanel").classList.add("hidden");$("registerPanel").classList.add("hidden");$("forgotPanel").classList.remove("hidden");}
function backToEmail(){$("emailStep").classList.remove("hidden");$("verifyStep").classList.add("hidden");}

const reqForm = $("requestCodeForm");
if (reqForm) {
  reqForm.addEventListener("submit", async e => {
    e.preventDefault();
    pendingEmail = $("registerEmail").value.trim().toLowerCase();
    if(!pendingEmail || !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(pendingEmail)){
      message("registerMessage","أدخل بريدًا صحيحًا.","error");
      return;
    }
    generatedOtp = Math.floor(100000 + Math.random()*900000).toString();
    
    try {
      const allCodes = JSON.parse(localStorage.getItem("outhub_codes")||"{}");
      allCodes[pendingEmail] = {code: generatedOtp, exp: Date.now()+10*60*1000};
      localStorage.setItem("outhub_codes", JSON.stringify(allCodes));
    } catch(err){}

    // إرسال الرمز إلى Eisen Mail عبر localStorage (يعمل فقط إذا كان Outhub وEisen Mail على نفس النطاق)
    const payload = {
      to: pendingEmail,
      code: generatedOtp,
      purpose: "verify",
      at: Date.now()
    };
    localStorage.setItem("outhub_send_code_request", JSON.stringify(payload));

    // محاولة الكتابة مباشرة في IndexedDB (نفس المتصفح ونفس النطاق فقط)
    try {
      const dbReq = indexedDB.open("EisenMailDB");
      dbReq.onupgradeneeded = function(event) {
        const db = event.target.result;
        if (!db.objectStoreNames.contains("messages")) {
          const store = db.createObjectStore("messages", { keyPath: "id", autoIncrement: true });
          store.createIndex("from", "from", { unique: false });
          store.createIndex("to", "to", { unique: false });
        }
        if (!db.objectStoreNames.contains("users")) {
          db.createObjectStore("users", { keyPath: "email" });
        }
      };
      dbReq.onsuccess = function(event) {
        try {
          const db = event.target.result;
          if (db.objectStoreNames.contains("messages")) {
            const tx = db.transaction("messages", "readwrite");
            const store = tx.objectStore("messages");
            store.add({
              from: "no-reply@outhub.system",
              to: pendingEmail,
              subject: "رمز التحقق - OutHub",
              body: "مرحبا،\n\nرمز التحقق الخاص بك في OutHub هو:\n\n" + generatedOtp + "\n\nصالح لمدة 10 دقائق. لا تشاركه مع أحد.\n\n- OutHub",
              date: new Date().toISOString()
            });
          }
        } catch (e2) {}
      };
    } catch (err) {}

    // فتح Eisen Mail دائماً من Alislamiah
    try {
      const isWebView = /wv|WebView|FBAN|FBAV/.test(navigator.userAgent);
      if (!isWebView) {
        window.open("https://Alislamiah.github.io/Eisen-mail/", "_blank", "noopener");
      }
    } catch (e) {}

    $("emailStep").classList.add("hidden");
    $("verifyStep").classList.remove("hidden");
    message("registerMessage", "تم إرسال رمز التحقق إلى بريدك في Eisen Mail (Alislamiah). افتح صندوق الوارد هناك وأدخل الرمز هنا.", "success");
  });
}

const verifyForm = $("verifyForm");
if (verifyForm) {
  verifyForm.addEventListener("submit", async e => {
    e.preventDefault();
    const codeInput = $("verifyCode").value.trim();
    const password = $("registerPassword").value;
    
    let saved = null;
    try {
      const allCodes = JSON.parse(localStorage.getItem("outhub_codes")||"{}");
      saved = allCodes[pendingEmail];
    } catch(e){}
    
    const expected = saved ? saved.code : generatedOtp;
    
    if(!expected || codeInput !== expected){
      message("registerMessage","❌ هذا خاطئ - رمز التحقق غير صحيح لهذا البريد.","error");
      return;
    }
    
    if(saved && Date.now() > saved.exp){
      message("registerMessage","❌ انتهت صلاحية الرمز.","error");
      return;
    }
    
    try {
      await window.createUserWithEmailAndPassword(window.auth, pendingEmail, password);
      try {
        const allCodes = JSON.parse(localStorage.getItem("outhub_codes")||"{}");
        delete allCodes[pendingEmail];
        localStorage.setItem("outhub_codes", JSON.stringify(allCodes));
      } catch(e){}
      showHome();
      message("loginMessage","✅ صحيح نعم - تم إنشاء الحساب بنجاح","success");
    } catch(error) {
      message("registerMessage","خطأ في إنشاء الحساب: " + error.message, "error");
    }
  });
}

const loginForm = $("loginForm");
if (loginForm) {
  loginForm.addEventListener("submit", async e => {
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
}

const forgotForm = $("forgotForm");
if (forgotForm) {
  forgotForm.addEventListener("submit", async e => {
    e.preventDefault();
    message("forgotMessage","إذا كان الحساب موجودًا، فستصل تعليمات الاستعادة إلى بريدك في Eisen Mail.", "success");
  });
}

function logout(){ window.signOut(window.auth).then(() => { showLogin(); }); }

function showHome(){ showView("homeView"); renderRecent(); }
function showAccount(){ $("accountInfo").textContent = "البريد المستخدم: " + emailNow(); showView("accountView"); }
function showWebsite(){ clearMessage("websiteMessage"); showView("websiteView"); }
function showApp(){ clearMessage("appMessage"); showView("appView"); }
function showProjects(){ $("allProjects").innerHTML = projectList(); showView("projectsView"); }

function allStored(){
  try{
    const a = JSON.parse(localStorage.getItem(KEY)||"[]");
    if(!Array.isArray(a)) return [];
    let changed = false;
    a.forEach(p => {
      if(!p.id){
        p.id = "p_" + Date.now() + "_" + Math.random().toString(36).slice(2,9);
        changed = true;
      }
    });
    if(changed) localStorage.setItem(KEY, JSON.stringify(a));
    return a;
  }catch(e){return []}
}
function myProjects(){
  // دمج المشاريع القديمة + مشاريع المحرك الجديد
  const old = allStored().filter(p => p.owner === emailNow());
  const fromEngine = engine.listProjects().map(ep => ({
    id: "eng_" + ep.name,
    name: ep.name,
    type: ep.type || "موقع إلكتروني",
    idea: ep.idea || "",
    repo: ep.repo || ep.name,
    visibility: ep.visibility || "public",
    date: ep.updatedAt || ep.date || new Date().toISOString(),
    liveUrl: engine.generateLiveUrl(ep.owner, ep.name),
    files: ep.files || null,
    owner: emailNow(),
    engine: true
  }));
  // تجنب التكرار حسب الاسم
  const names = new Set(fromEngine.map(p => p.name.toLowerCase()));
  const merged = [...fromEngine, ...old.filter(p => !names.has((p.name||"").toLowerCase()))];
  return merged;
}
function saveProject(p){
  // 1) الحفظ التقليدي (للتوافق مع الواجهة الحالية)
  const all = allStored();
  const id = "p_" + Date.now() + "_" + Math.random().toString(36).slice(2,9);
  const record = {
    ...p,
    id,
    owner: emailNow(),
    date: new Date().toISOString()
  };
  all.push(record);
  localStorage.setItem(KEY, JSON.stringify(all));

  // 2) الحفظ عبر OuthubEngine (مثل GitHub) + توليد الرابط الحي
  const defaultHtml = `<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>${escapeHTML(p.name || "مشروع")}</title>
<style>
  body{font-family:Arial,sans-serif;background:#0d1117;color:#e6edf3;margin:0;padding:40px;text-align:center}
  h1{color:#58a6ff}
  p{color:#8b949e;max-width:600px;margin:16px auto;line-height:1.7}
  .badge{display:inline-block;background:#21262d;border:1px solid #30363d;padding:6px 14px;border-radius:20px;font-size:13px;margin-top:20px}
</style>
</head>
<body>
  <h1>${escapeHTML(p.name || "مشروع جديد")}</h1>
  <p>${escapeHTML(p.idea || "تم إنشاء هذا المشروع عبر منصة Outhub")}</p>
  <div class="badge">Powered by Outhub</div>
</body>
</html>`;

  const filesData = {
    "index.html": defaultHtml
  };

  const liveUrl = engine.createProject(p.name || p.repo || "project", filesData);

  // حفظ الرابط الحي مع السجل القديم أيضاً
  record.liveUrl = liveUrl;
  const updated = allStored().map(item => item.id === id ? {...item, liveUrl} : item);
  localStorage.setItem(KEY, JSON.stringify(updated));

  return liveUrl;
}
function markup(p){
  const live = p.liveUrl ? `<p style="color:#31d9e8;font-size:12px;margin-top:6px">🔗 ${escapeHTML(p.liveUrl)}</p>` : "";
  return `<div class="project-item" onclick="showProject('${escapeHTML(p.id)}')" role="button" tabindex="0">
    <strong>${escapeHTML(p.name)}</strong>
    <p>النوع: ${escapeHTML(p.type)}</p>
    <p>${escapeHTML(p.idea)}</p>
    <p>${escapeHTML(new Date(p.date).toLocaleDateString("ar"))}</p>
    ${live}
  </div>`;
}
function projectList(){
  const list = myProjects();
  return list.length ? list.map(markup).join("") : '<div class="empty">لا توجد مشاريع محفوظة.</div>';
}
function renderRecent(){
  const list = myProjects().slice(0,3);
  $("recentProjects").innerHTML = list.length ? list.map(markup).join("") : '<div class="card empty">لم تحفظ أي مشروع بعد.</div>';
}

let currentEditingFile = null;

function getEngineProjectName(){
  if(!currentProject) return "";
  return currentProject.name || currentProject.repo || "";
}

function loadProjectFilesFromEngine(){
  if(!currentProject) return {};
  // إن كانت الملفات محمّلة مباشرة (من الرابط الحي) نستخدمها
  if(currentProject.files && Object.keys(currentProject.files).length){
    return currentProject.files;
  }
  const name = getEngineProjectName();
  if(!name) return {};
  // جلب من المحرك (بعد تعيين المستخدم الصحيح)
  const eng = engine.getProject(name);
  return (eng && eng.files) ? eng.files : {};
}

function renderProjectFilesList(){
  const files = loadProjectFilesFromEngine();
  const names = Object.keys(files);
  const box = $("projectFilesList");
  if(!names.length){
    box.innerHTML = '<div class="empty">لا توجد ملفات بعد. استخدم Create file أو Upload file.</div>';
    return;
  }
  box.innerHTML = names.map(fn => {
    const isActive = currentEditingFile === fn ? 'border-color:var(--blue);background:#0d1a2e' : '';
    return `<div class="project-item" style="display:flex;align-items:center;justify-content:space-between;gap:10px;${isActive}" onclick="openFileInEditor('${escapeHTML(fn)}')">
      <span>📄 ${escapeHTML(fn)}</span>
      <span class="muted small">${(files[fn]||"").length} حرف</span>
    </div>`;
  }).join("");
}

function showProject(id){
  // إن كان المشروع محمّلاً مسبقًا من الرابط الحي نستخدمه مباشرة
  let proj = null;
  if(currentProject && (currentProject.id === id || id === currentProject.id)){
    proj = currentProject;
  } else {
    proj = myProjects().find(p => p.id === id);
  }
  if(!proj){
    showProjects();
    return;
  }
  currentProject = proj;
  currentEditingFile = null;
  $("projectTitle").textContent = proj.name || "بدون عنوان";
  $("projectDesc").textContent = proj.idea || "لا يوجد وصف";

  let liveUrl = proj.liveUrl;
  if(!liveUrl && proj.name){
    liveUrl = engine.generateLiveUrl(proj.owner || usernameNow(), proj.name);
  }
  currentProject.liveUrl = liveUrl;

  const meta = [];
  meta.push(`<span>النوع: ${escapeHTML(proj.type)}</span>`);
  if(proj.repo) meta.push(`<span>الاسم: ${escapeHTML(proj.repo)}</span>`);
  if(proj.visibility) meta.push(`<span>الخصوصية: ${proj.visibility === "public" ? "علني" : "خاص"}</span>`);
  meta.push(`<span>التاريخ: ${escapeHTML(new Date(proj.date).toLocaleDateString("ar"))}</span>`);
  if(liveUrl) meta.push(`<span style="color:#31d9e8">🔗 ${escapeHTML(liveUrl)}</span>`);
  $("projectMeta").innerHTML = meta.join("");

  // إخفاء اللوحات
  $("createFilePanel").classList.add("hidden");
  $("uploadPanel").classList.add("hidden");
  $("codeEditorSection").classList.add("hidden");
  clearMessage("createFileMessage");
  clearMessage("uploadMessage");
  clearMessage("editorMessage");
  clearMessage("embedMessage");

  $("embedHint").textContent = liveUrl ? ("الرابط الحي: " + liveUrl) : "";
  renderProjectFilesList();
  refreshPreview();
  showView("projectView");
}

function showCreateFilePanel(){
  $("createFilePanel").classList.remove("hidden");
  $("uploadPanel").classList.add("hidden");
  $("newFileName").value = "";
  $("newFileCode").value = "";
  clearMessage("createFileMessage");
  $("newFileName").focus();
}
function hideCreateFilePanel(){ $("createFilePanel").classList.add("hidden"); }

function showUploadPanel(){
  $("uploadPanel").classList.remove("hidden");
  $("createFilePanel").classList.add("hidden");
  clearMessage("uploadMessage");
}
function hideUploadPanel(){ $("uploadPanel").classList.add("hidden"); }

function createFileInProject(){
  const name = getEngineProjectName();
  if(!name){ message("createFileMessage","لا يوجد مشروع مفتوح.","error"); return; }
  const fileName = ($("newFileName").value || "").trim();
  const code = $("newFileCode").value || "";
  if(!fileName){ message("createFileMessage","أدخل اسم الملف.","error"); return; }
  if(/[\/\\]/.test(fileName)){ message("createFileMessage","اسم الملف لا يجب أن يحتوي على / أو \\.","error"); return; }

  const ok = engine.addFile(name, fileName, code);
  if(!ok){ message("createFileMessage","فشل إنشاء الملف.","error"); return; }

  // مزامنة مع السجل القديم إن وُجد
  currentProject.files = loadProjectFilesFromEngine();
  message("createFileMessage","✅ تم إنشاء الملف: " + fileName, "success");
  hideCreateFilePanel();
  renderProjectFilesList();
  openFileInEditor(fileName);
  refreshPreview();
}

function openFileInEditor(fileName){
  const files = loadProjectFilesFromEngine();
  if(!(fileName in files)) return;
  currentEditingFile = fileName;
  $("codeEditorSection").classList.remove("hidden");
  $("currentFileTitle").textContent = "الملف: " + fileName;
  $("codeEditor").value = files[fileName] || "";
  clearMessage("editorMessage");
  renderProjectFilesList();
}

function saveCurrentFile(){
  if(!currentEditingFile) return;
  const name = getEngineProjectName();
  const content = $("codeEditor").value || "";
  engine.addFile(name, currentEditingFile, content);
  currentProject.files = loadProjectFilesFromEngine();
  message("editorMessage","✅ تم حفظ " + currentEditingFile, "success");
  renderProjectFilesList();
  refreshPreview();
}

function deleteCurrentFile(){
  if(!currentEditingFile) return;
  if(!confirm("حذف الملف " + currentEditingFile + "؟")) return;
  const name = getEngineProjectName();
  engine.deleteFile(name, currentEditingFile);
  currentProject.files = loadProjectFilesFromEngine();
  currentEditingFile = null;
  $("codeEditorSection").classList.add("hidden");
  renderProjectFilesList();
  refreshPreview();
  message("embedMessage","تم حذف الملف.","info");
}

function refreshPreview(){
  const frame = $("embedFrame");
  const files = loadProjectFilesFromEngine();
  let html = files["index.html"] || files["index.htm"] || null;

  // إذا لم يوجد index، نبني صفحة بسيطة تعرض الملفات
  if(!html){
    const list = Object.keys(files).map(f => `<li>${escapeHTML(f)}</li>`).join("") || "<li>لا ملفات</li>";
    html = `<!DOCTYPE html><html lang="ar" dir="rtl"><head><meta charset="UTF-8"><title>${escapeHTML(currentProject?.name||"")}</title>
<style>body{font-family:Arial,sans-serif;background:#0d1117;color:#e6edf3;padding:30px}h1{color:#58a6ff}ul{line-height:2}</style></head>
<body><h1>${escapeHTML(currentProject?.name||"مشروع")}</h1>
<p>${escapeHTML(currentProject?.idea||"")}</p>
<p style="color:#8b949e">ملفات المشروع:</p><ul>${list}</ul>
<p style="margin-top:24px;color:#6e7681">Outhub — معاينة مستقلة</p></body></html>`;
  }

  frame.removeAttribute("src");
  frame.srcdoc = html;
  message("embedMessage", "تم تحديث المعاينة من الملفات المخزنة داخل Outhub.", "success");
}

function triggerDeviceUpload(){
  $("deviceFileInput").click();
}

function handleDeviceFiles(ev){
  const files = ev.target.files;
  if(!files || !files.length) return;
  const name = getEngineProjectName();
  if(!name){ message("uploadMessage","افتح مشروعاً أولاً.","error"); return; }

  let done = 0;
  const total = files.length;
  Array.from(files).forEach(file => {
    const reader = new FileReader();
    reader.onload = function(){
      const content = typeof reader.result === "string" ? reader.result : "";
      // للملفات النصية نحفظ المحتوى، للصور نحاول base64
      engine.addFile(name, file.name, content);
      done++;
      if(done === total){
        currentProject.files = loadProjectFilesFromEngine();
        message("uploadMessage", "✅ تم رفع " + total + " ملف/ملفات بنجاح.", "success");
        renderProjectFilesList();
        refreshPreview();
        hideUploadPanel();
      }
    };
    // نقرأ كنص إن أمكن، وإلا كـ dataURL
    if(file.type.startsWith("text/") || /\.(html?|css|js|json|md|txt|svg|xml)$/i.test(file.name)){
      reader.readAsText(file);
    } else {
      reader.readAsDataURL(file);
    }
  });
  // إعادة تعيين المدخل
  ev.target.value = "";
}

function copyLiveUrl(){
  if(!currentProject || !currentProject.liveUrl){
    message("embedMessage","لا يوجد رابط حي لهذا المشروع.","error");
    return;
  }
  const url = currentProject.liveUrl;
  if(navigator.clipboard && navigator.clipboard.writeText){
    navigator.clipboard.writeText(url).then(()=>{
      message("embedMessage","تم نسخ الرابط الحي:\n" + url, "success");
    }).catch(()=>{
      message("embedMessage","الرابط الحي:\n" + url, "info");
    });
  } else {
    message("embedMessage","الرابط الحي:\n" + url, "info");
  }
}

const websiteForm = $("websiteForm");
if (websiteForm) {
  websiteForm.addEventListener("submit", e => {
    e.preventDefault();
    const name = $("websiteName").value.trim();
    const idea = $("websiteIdea").value.trim();
    const repo = $("repoName").value.trim();
    const visibility = $("visibility").value;
    if(!/^[A-Za-z0-9._-]+$/.test(repo)){message("websiteMessage","اسم المشروع غير صالح (حروف وأرقام و - _ . فقط).","error");return;}
    const liveUrl = saveProject({name, idea, type:"موقع إلكتروني", repo, visibility});
    message("websiteMessage", "✅ تم إنشاء المشروع بنجاح.\nالرابط الحي (يعمل على هذا المتصفح):\n" + (liveUrl || "") + "\nافتحه من «مشاريعي» أو انسخ الرابط.", "success");
    setTimeout(() => showProjects(), 1000);
  });
}

const appForm = $("appForm");
if (appForm) {
  appForm.addEventListener("submit", e => {
    e.preventDefault();
    const name = $("appName").value.trim();
    const idea = $("appIdea").value.trim();
    const liveUrl = saveProject({name, idea, type: "تطبيق"});
    message("appMessage", "✅ تم حفظ التطبيق داخل Outhub.\nالرابط الحي:\n" + (liveUrl || ""), "success");
    setTimeout(() => showProjects(), 1000);
  });
}
</script>
</body>
</html>
