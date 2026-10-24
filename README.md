<!DOCTYPE html>
<html lang="ar" dir="rtl" class="dark">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NexusAI Pro Studio | المنصة السحابية المتكاملة</title>
<script src="https://cdn.tailwindcss.com"></script>
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
<style>
.glass { background: rgba(15, 23, 42, 0.85); backdrop-filter: blur(16px); border: 1px solid rgba(255, 255, 255, 0.08); }
</style>
</head>
<body class="bg-slate-950 text-slate-100 min-h-screen flex flex-col font-sans">

<!-- Header -->
<header class="sticky top-0 z-50 glass border-b border-slate-800">
<div class="max-w-7xl mx-auto px-4 h-16 flex items-center justify-between">
<div class="flex items-center space-x-3 space-x-reverse">
<div class="bg-gradient-to-tr from-emerald-600 to-teal-500 p-2.5 rounded-xl text-white shadow-lg shadow-emerald-900/30">
<i class="fa-solid fa-brain text-xl"></i>
</div>
<div>
<span class="text-lg font-bold bg-gradient-to-r from-white via-slate-200 to-emerald-400 bg-clip-text text-transparent">NexusAI Studio</span>
<span class="block text-[10px] text-emerald-400 font-medium">النسخة السحابية المتقدمة (12 خدمة)</span>
</div>
</div>
<button onclick="connectWallet()" class="flex items-center gap-2 bg-gradient-to-r from-emerald-600 to-teal-600 hover:from-emerald-500 hover:to-teal-500 text-white text-sm font-medium px-4 py-2.5 rounded-xl transition shadow-lg shadow-emerald-950">
<i class="fa-solid fa-wallet"></i>
<span id="walletText">ربط المحفظة (USDT)</span>
</button>
</div>
</header>

<!-- App Layout -->
<div class="flex-1 max-w-7xl w-full mx-auto px-4 py-6 flex flex-col md:flex-row gap-6">

<!-- Sidebar Navigation -->
<aside class="w-full md:w-72 glass rounded-2xl p-4 flex flex-col gap-2 h-fit">
<div class="text-[11px] font-bold text-slate-400 px-3 py-1 uppercase tracking-wider">الخدمات الأساسية (12 ميزة)</div>

<button onclick="switchTab('planner')" id="nav-planner" class="nav-btn flex items-center justify-between px-4 py-3 rounded-xl text-slate-200 bg-slate-800/90 border border-emerald-500/40 text-right w-full transition">
<div class="flex items-center gap-3">
<i class="fa-solid fa-calendar-check text-emerald-400 text-lg"></i>
<span class="font-medium text-sm">مولد الخطط الشهرية</span>
</div>
<span class="text-[10px] bg-emerald-500/20 text-emerald-300 px-2 py-0.5 rounded-full">نشط</span>
</button>

<button onclick="switchTab('reels')" id="nav-reels" class="nav-btn flex items-center justify-between px-4 py-3 rounded-xl text-slate-400 hover:bg-slate-800/50 hover:text-slate-200 text-right w-full transition">
<div class="flex items-center gap-3">
<i class="fa-solid fa-clapperboard text-indigo-400 text-lg"></i>
<span class="font-medium text-sm">سيناريو المونتاج Reels</span>
</div>
</button>

<button onclick="switchTab('summary')" id="nav-summary" class="nav-btn flex items-center justify-between px-4 py-3 rounded-xl text-slate-400 hover:bg-slate-800/50 hover:text-slate-200 text-right w-full transition">
<div class="flex items-center gap-3">
<i class="fa-solid fa-file-contract text-amber-400 text-lg"></i>
<span class="font-medium text-sm">تلخيص وتحليل النصوص</span>
</div>
</button>

<button onclick="switchTab('ads')" id="nav-ads" class="nav-btn flex items-center justify-between px-4 py-3 rounded-xl text-slate-400 hover:bg-slate-800/50 hover:text-slate-200 text-right w-full transition">
<div class="flex items-center gap-3">
<i class="fa-solid fa-bullhorn text-rose-400 text-lg"></i>
<span class="font-medium text-sm">صانع الإعلانات التسويقية</span>
</div>
</button>

<button onclick="switchTab('seo')" id="nav-seo" class="nav-btn flex items-center justify-between px-4 py-3 rounded-xl text-slate-400 hover:bg-slate-800/50 hover:text-slate-200 text-right w-full transition">
<div class="flex items-center gap-3">
<i class="fa-solid fa-magnifying-glass-chart text-cyan-400 text-lg"></i>
<span class="font-medium text-sm">استخراج الكلمات المفتاحية SEO</span>
</div>
</button>

<button onclick="switchTab('pricing')" id="nav-pricing" class="nav-btn flex items-center justify-between px-4 py-3 rounded-xl text-slate-400 hover:bg-slate-800/50 hover:text-slate-200 text-right w-full transition">
<div class="flex items-center gap-3">
<i class="fa-solid fa-gem text-teal-400 text-lg"></i>
<span class="font-medium text-sm">اشتراكات وبوابة Web3</span>
</div>
</button>
</aside>

<!-- Main Workspace -->
<main class="flex-1 space-y-6">

<!-- Service 1: Content Planner -->
<section id="tab-planner" class="glass rounded-2xl p-6 sm:p-8 space-y-6">
<div>
<h2 class="text-xl font-bold text-white flex items-center gap-2">
<i class="fa-solid fa-calendar-check text-emerald-400"></i>مولد خطط المحتوى الذكية
</h2>
<p class="text-slate-400 text-sm mt-1">أدخل مجال عملك واستخرج جدول محتوى احترافي لشهر كامل.</p>
</div>
<div class="space-y-4">
<input type="text" id="plannerInput" placeholder="مثال: متجر إلكتروني، خدمات مونتاج CapCut، برمجة..." class="w-full bg-slate-900 border border-slate-700/80 rounded-xl p-3.5 text-white text-sm focus:outline-none focus:border-emerald-500 shadow-inner">
<button onclick="runService('planner')" class="w-full bg-emerald-600 hover:bg-emerald-500 text-white font-semibold py-3.5 rounded-xl transition shadow-lg shadow-emerald-950 flex items-center justify-center gap-2">
<i class="fa-solid fa-wand-magic-sparkles"></i> توليد الخطة الشهرية
</button>
</div>
<div id="out-planner" class="hidden bg-slate-900/90 border border-slate-800 rounded-xl p-5 text-slate-200 whitespace-pre-line text-sm leading-relaxed"></div>
</section>

<!-- Service 2: Reels Script -->
<section id="tab-reels" class="glass rounded-2xl p-6 sm:p-8 space-y-6 hidden">
<div>
<h2 class="text-xl font-bold text-white flex items-center gap-2">
<i class="fa-solid fa-clapperboard text-indigo-400"></i>صانع سيناريوهات المونتاج Reels & TikTok
</h2>
<p class="text-slate-400 text-sm mt-1">صمم سكربت فيديو قصير مقسم بالثواني مع زوايا التصوير والخطاف.</p>
</div>
<div class="space-y-4">
<input type="text" id="reelsInput" placeholder="مثال: 3 أسرار لتسريع المونتاج وحفظ وقتك..." class="w-full bg-slate-900 border border-slate-700/80 rounded-xl p-3.5 text-white text-sm focus:outline-none focus:border-indigo-500">
<button onclick="runService('reels')" class="w-full bg-indigo-600 hover:bg-indigo-500 text-white font-semibold py-3.5 rounded-xl transition shadow-lg shadow-indigo-950 flex items-center justify-center gap-2">
<i class="fa-solid fa-film"></i> إنشاء سكربت المونتاج
</button>
</div>
<div id="out-reels" class="hidden bg-slate-900/90 border border-slate-800 rounded-xl p-5 text-slate-200 whitespace-pre-line text-sm leading-relaxed"></div>
</section>

<!-- Service 3: Text Summarizer -->
<section id="tab-summary" class="glass rounded-2xl p-6 sm:p-8 space-y-6 hidden">
<div>
<h2 class="text-xl font-bold text-white flex items-center gap-2">
<i class="fa-solid fa-file-contract text-amber-400"></i>محلل وملخص النصوص والمقالات
</h2>
<p class="text-slate-400 text-sm mt-1">ضع أي نص مطول لاستخراج أبرز الأفكار والملخص التنفيذي.</p>
</div>
<div class="space-y-4">
<textarea id="summaryInput" rows="5" placeholder="ضع النص المطول هنا..." class="w-full bg-slate-900 border border-slate-700/80 rounded-xl p-3.5 text-white text-sm focus:outline-none focus:border-amber-500"></textarea>
<button onclick="runService('summary')" class="w-full bg-amber-600 hover:bg-amber-500 text-white font-semibold py-3.5 rounded-xl transition shadow-lg shadow-amber-950 flex items-center justify-center gap-2">
<i class="fa-solid fa-bolt"></i> تحليل واستخراج النقاط
</button>
</div>
<div id="out-summary" class="hidden bg-slate-900/90 border border-slate-800 rounded-xl p-5 text-slate-200 whitespace-pre-line text-sm leading-relaxed"></div>
</section>

<!-- Service 4: Ad Copywriter -->
<section id="tab-ads" class="glass rounded-2xl p-6 sm:p-8 space-y-6 hidden">
<div>
<h2 class="text-xl font-bold text-white flex items-center gap-2">
<i class="fa-solid fa-bullhorn text-rose-400"></i>صانع الإعلانات التسويقية الجذابة
</h2>
<p class="text-slate-400 text-sm mt-1">اكتب اسم منتجك أو خدمتك واحصل على نصوص إعلانية موجهة للجمهور.</p>
</div>
<div class="space-y-4">
<input type="text" id="adsInput" placeholder="مثال: تطبيق سحابي لإدارة المهام الرقمية..." class="w-full bg-slate-900 border border-slate-700/80 rounded-xl p-3.5 text-white text-sm focus:outline-none focus:border-rose-500">
<button onclick="runService('ads')" class="w-full bg-rose-600 hover:bg-rose-500 text-white font-semibold py-3.5 rounded-xl transition shadow-lg shadow-rose-950 flex items-center justify-center gap-2">
<i class="fa-solid fa-bullseye"></i> توليد النصوص الإعلانية
</button>
</div>
<div id="out-ads" class="hidden bg-slate-900/90 border border-slate-800 rounded-xl p-5 text-slate-200 whitespace-pre-line text-sm leading-relaxed"></div>
</section>

<!-- Service 5: SEO Keywords -->
<section id="tab-seo" class="glass rounded-2xl p-6 sm:p-8 space-y-6 hidden">
<div>
<h2 class="text-xl font-bold text-white flex items-center gap-2">
<i class="fa-solid fa-magnifying-glass-chart text-cyan-400"></i>استخراج الكلمات المفتاحية SEO
</h2>
<p class="text-slate-400 text-sm mt-1">حدد موضوع مقالك أو فيديوك للحصول على أقوى الكلمات والهاشتاغات.</p>
</div>
<div class="space-y-4">
<input type="text" id="seoInput" placeholder="مثال: دورة تعلم البرمجة من الصفر..." class="w-full bg-slate-900 border border-slate-700/80 rounded-xl p-3.5 text-white text-sm focus:outline-none focus:border-cyan-500">
<button onclick="runService('seo')" class="w-full bg-cyan-600 hover:bg-cyan-500 text-white font-semibold py-3.5 rounded-xl transition shadow-lg shadow-cyan-950 flex items-center justify-center gap-2">
<i class="fa-solid fa-key"></i> استخراج الكلمات والهاشتاغات
</button>
</div>
<div id="out-seo" class="hidden bg-slate-900/90 border border-slate-800 rounded-xl p-5 text-slate-200 whitespace-pre-line text-sm leading-relaxed"></div>
</section>

<!-- Service 6: Web3 Pricing -->
<section id="tab-pricing" class="glass rounded-2xl p-6 sm:p-8 space-y-6 hidden">
<div>
<h2 class="text-xl font-bold text-white flex items-center gap-2">
<i class="fa-solid fa-gem text-teal-400"></i>بوابة الاشتراكات والدفع عبر Web3 (USDT)
</h2>
<p class="text-slate-400 text-sm mt-1">اشترك في الباقات الاحترافية عبر عقود الضمان الآمنة مباشرة لمحفظتك.</p>
</div>
<div class="grid grid-cols-1 md:grid-cols-2 gap-5 pt-2">
<div class="bg-slate-900 border border-slate-800 rounded-2xl p-6 flex flex-col justify-between space-y-4">
<div>
<span class="text-xs font-bold bg-slate-800 text-slate-300 px-3 py-1 rounded-full">باقة المحترفين</span>
<div class="text-3xl font-extrabold text-white mt-4">25 USDT <span class="text-xs text-slate-400 font-normal">/ شهرياً</span></div>
<ul class="text-sm text-slate-300 space-y-2 mt-4">
<li><i class="fa-solid fa-check text-emerald-400 ml-2"></i>توليد غير محدود لخطط المحتوى</li>
<li><i class="fa-solid fa-check text-emerald-400 ml-2"></i>سكربتات مونتاج Reels احترافية</li>
<li><i class="fa-solid fa-check text-emerald-400 ml-2"></i>تلخيص وتحليل النصوص المتقدم</li>
</ul>
</div>
<button onclick="payWeb3(25)" class="w-full bg-emerald-600 hover:bg-emerald-500 text-white font-semibold py-3 rounded-xl transition">
اشتراك بـ 25 USDT
</button>
</div>

<div class="bg-gradient-to-b from-slate-900 to-slate-900/80 border border-emerald-500/50 rounded-2xl p-6 flex flex-col justify-between space-y-4 relative overflow-hidden">
<div>
<span class="text-xs font-bold bg-emerald-500/20 text-emerald-400 border border-emerald-500/30 px-3 py-1 rounded-full">الباقة الشاملة VIP</span>
<div class="text-3xl font-extrabold text-white mt-4">50 USDT <span class="text-xs text-slate-400 font-normal">/ شهرياً</span></div>
<ul class="text-sm text-slate-300 space-y-2 mt-4">
<li><i class="fa-solid fa-check text-emerald-400 ml-2"></i>جميع مميزات باقة المحترفين</li>
<li><i class="fa-solid fa-check text-emerald-400 ml-2"></i>أدوات صانع الإعلانات وتحليل SEO</li>
<li><i class="fa-solid fa-check text-emerald-400 ml-2"></i>أولوية المعالجة والدعم الشخصي</li>
</ul>
</div>
<button onclick="payWeb3(50)" class="w-full bg-gradient-to-r from-emerald-600 to-teal-600 hover:from-emerald-500 hover:to-teal-500 text-white font-semibold py-3 rounded-xl transition">
اشتراك بـ 50 USDT
</button>
</div>
</div>
</section>

</main>
</div>

<!-- Application Script Logic -->
<script>
// ==========================================
// 🚨 ضع عنوان محفظتك هنا بين علامتي التنصيص
// ==========================================
const MY_USDT_WALLET = "ضع_عنوان_محفظتك_هنا";

function switchTab(tabId) {
document.querySelectorAll('main > section').forEach(s => s.classList.add('hidden'));
document.querySelectorAll('.nav-btn').forEach(b => {
b.classList.remove('bg-slate-800/90', 'border', 'border-emerald-500/40', 'text-slate-200');
b.classList.add('text-slate-400');
});

document.getElementById('tab-' + tabId).classList.remove('hidden');
const activeBtn = document.getElementById('nav-' + tabId);
if(activeBtn) {
activeBtn.classList.add('bg-slate-800/90', 'border', 'border-emerald-500/40', 'text-slate-200');
activeBtn.classList.remove('text-slate-400');
}
}

function runService(type) {
let inputVal = '';
let outBox = null;
let resultText = '';

if (type === 'planner') {
inputVal = document.getElementById('plannerInput').value;
outBox = document.getElementById('out-planner');
if(!inputVal) { alert('يرجى ادخال مجال العمل أولاً'); return; }
resultText = "🗓️ خطة المحتوى الشهرية المقترحة لمجال (" + inputVal + "):\n\n" +
"• الأسبوع 1: منشور افتتاحي يعرض المشكلة الأساسية التي يعاني منها العميل وكيف تحلها.\n" +
"• الأسبوع 2: فيديو Reels قصير (30 ثانية) يعرض خطوات عملية وتطبيقاً سريعاً.\n" +
"• الأسبوع 3: دراسة حالة أو قصة نجاح توضح نتائج العملاء السابقين.\n" +
"• الأسبوع 4: عرض ترويجي مباشر ودعوة لاتخاذ إجراء (Call to Action).";
} else if (type === 'reels') {
inputVal = document.getElementById('reelsInput').value;
outBox = document.getElementById('out-reels');
if(!inputVal) { alert('يرجى ادخال فكرة الفيديو أولاً'); return; }
resultText = "🎬 سكربت سيناريو الفيديو (" + inputVal + "):\n\n" +
"⏱️ 0-3 ثوانٍ (الخطاف): "هل تفعل هذا الخطأ الفادح في " + inputVal + "؟"\n" +
"📹 3-15 ثانية: استعراض الخطوات العملية مع تصوير زاويّة قريبة.\n" +
"✂️ 15-25 ثانية: تسريع وتيرة المونتاج وعرض النتيجة النهائية.\n" +
"🎯 25-30 ثانية: احفظ الميديو وشاركه مع زملائك!";
} else if (type === 'summary') {
inputVal = document.getElementById('summaryInput').value;
outBox = document.getElementById('out-summary');
if(!inputVal) { alert('يرجى إدخال النص المراد تلخيصه أولاً'); return; }
resultText = "📌 الملخص التنفيذي وأبرز النقاط:\n\n" +
"1. التركيز على القيمة الأساسية المباشرة بدون إطالة.\n" +
"2. استغلال الأدوات المجانية لتحقيق أعلى إنتاجية بتكلفة صفرية.\n\n" +
"🏷️ الهاشتاغات المستخرجة:\n#تطوير_أعمال #ذكاء_اصطناعي #صناعة_محتوى";
} else if (type === 'ads') {
inputVal = document.getElementById('adsInput').value;
outBox = document.getElementById('out-ads');
if(!inputVal) { alert('يرجى إدخال اسم المنتج أو الخدمة أولاً'); return; }
resultText = "📢 النصوص الإعلانية المقترحة لـ (" + inputVal + "):\n\n" +
"• الإعلان الأول (جذاب ومباشر): "هل تبحث عن الطريقة الأسرع لتطوير عملك؟ اكتشف قوة " + inputVal + " الآن وحقق نتائج مضاعفة بجهد أقل!"\n" +
"• الإعلان الثاني (مبني على المشكلة والحل): "توقف عن إضاعة الوقت في الطرق التقليدية. جرب حلولنا الذكية اليوم واستمتع بتجربة فريدة."";
} else if (type === 'seo') {
inputVal = document.getElementById('seoInput').value;
outBox = document.getElementById('out-seo');
if(!inputVal) { alert('يرجى إدخال الموضوع أولاً'); return; }
resultText = "🔍 تحليل الكلمات المفتاحية لـ (" + inputVal + "):\n\n" +
"• الكلمات ذات البحث العالي: " + inputVal + " الاحترافي، دليل " + inputVal + " الشامل.\n" +
"• الكلمات طويلة الذيل: أفضل استراتيجيات " + inputVal + " بدون تجربة معقدة.\n" +
"• الهاشتاغات: #" + inputVal.replace(/\s+/g, '_') + " #تطوير #تقنية";
}

outBox.classList.remove('hidden');
outBox.innerText = resultText;
}

function connectWallet() {
alert('عنوان محفظة الاستلام: ' + MY_USDT_WALLET + '\n\n(تم نسخه تلقائياً)');
navigator.clipboard.writeText(MY_USDT_WALLET);
}

function payWeb3(amount) {
if(MY_USDT_WALLET === "TWz45uauDNkroso1VLjJcEYsj81t1Lsxfu") {
alert('تنبيه: لم يتم ضبط عنوان محفظة استلام الأرباح بعد في ملف الكود البرمجي!');
return;
}
navigator.clipboard.writeText(MY_USDT_WALLET);
alert('يرجى تحويل مبلغ ' + amount + ' USDT إلى المحفظة التالية:\n\n' + MY_USDT_WALLET + '\n\n✅ تم نسخ العنوان تلقائياً إلى الحافظة!');
}
</script>
</body>
</html>

