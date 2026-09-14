```html
<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>FATHER.EXE // Programmer's Day</title>

<style>
:root{
    --bg:#030509;
    --panel:#070b12;
    --panel2:#0b111b;
    --line:#1b2a3d;
    --text:#edf5ff;
    --muted:#8190a5;
    --green:#58f5b2;
    --blue:#5ba7ff;
    --purple:#bd7cff;
    --cyan:#49e9ff;
    --yellow:#ffd166;
    --red:#ff5577;
}

*{
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    margin:0;
    background:var(--bg);
    color:var(--text);
    font-family:Tahoma,Arial,sans-serif;
    overflow-x:hidden;
}

/* ================= BACKGROUND ================= */

body:before{
    content:"";
    position:fixed;
    inset:0;
    pointer-events:none;
    opacity:.07;
    background-image:
        linear-gradient(#fff 1px,transparent 1px),
        linear-gradient(90deg,#fff 1px,transparent 1px);
    background-size:45px 45px;
    z-index:-5;
}

body:after{
    content:"";
    position:fixed;
    inset:0;
    pointer-events:none;
    background:
        radial-gradient(circle at 50% 0,
        rgba(73,233,255,.13),
        transparent 32%),
        radial-gradient(circle at 15% 80%,
        rgba(88,245,178,.06),
        transparent 25%),
        radial-gradient(circle at 90% 60%,
        rgba(189,124,255,.06),
        transparent 25%);
    z-index:-4;
}

/* floating particles */

.particle{
    position:fixed;
    width:2px;
    height:2px;
    background:#fff;
    border-radius:50%;
    opacity:.4;
    pointer-events:none;
    animation:floatParticle linear infinite;
}

@keyframes floatParticle{
    from{
        transform:translateY(110vh);
    }
    to{
        transform:translateY(-20vh);
    }
}

/* ================= NAV ================= */

nav{
    position:fixed;
    z-index:100;
    top:0;
    left:0;
    right:0;
    height:70px;
    padding:0 7%;
    display:flex;
    align-items:center;
    justify-content:space-between;
    background:rgba(3,5,9,.68);
    backdrop-filter:blur(20px);
    border-bottom:1px solid rgba(91,167,255,.15);
}

.brand{
    font:700 18px Consolas,monospace;
    color:var(--green);
}

.brand span{
    color:var(--blue);
}

nav a{
    color:#8291a7;
    text-decoration:none;
    margin-right:25px;
    font:12px Consolas;
    transition:.2s;
}

nav a:hover{
    color:#fff;
}

/* ================= HERO ================= */

.hero{
    min-height:100vh;
    display:grid;
    place-items:center;
    padding:120px 6% 80px;
    position:relative;
}

.heroBox{
    max-width:1100px;
    width:100%;
    text-align:center;
}

.eyebrow{
    font:12px Consolas;
    color:var(--green);
    letter-spacing:4px;
    margin-bottom:20px;
}

.hero h1{
    font-size:clamp(55px,9vw,110px);
    margin:0;
    letter-spacing:-7px;
    line-height:1;
    text-shadow:
        0 0 25px rgba(88,245,178,.12);
}

.hero h1 span{
    color:var(--green);
}

.hero p{
    color:#9aaabd;
    font-size:18px;
    line-height:2;
    max-width:720px;
    margin:25px auto;
}

/* ================= TERMINAL ================= */

.window{
    margin:45px auto 30px;
    max-width:900px;
    background:#05080d;
    border:1px solid #25364c;
    border-radius:18px;
    overflow:hidden;
    box-shadow:
        0 30px 100px rgba(0,0,0,.65),
        0 0 50px rgba(73,233,255,.04);
    text-align:left;
    direction:ltr;
}

.bar{
    height:44px;
    border-bottom:1px solid #1b2939;
    display:flex;
    align-items:center;
    padding:0 16px;
    gap:8px;
}

.ball{
    width:10px;
    height:10px;
    border-radius:50%;
    background:#334154;
}

.path{
    margin-left:13px;
    font:12px Consolas;
    color:#65758a;
}

.screen{
    padding:25px;
    font:14px/2 Consolas;
    color:#bac8d8;
    min-height:190px;
}

.g{color:var(--green)}
.b{color:var(--blue)}
.p{color:var(--purple)}
.c{color:var(--cyan)}
.y{color:var(--yellow)}
.r{color:var(--red)}

.cursor{
    display:inline-block;
    width:8px;
    height:16px;
    background:var(--green);
    vertical-align:-3px;
    animation:blink 1s infinite;
}

@keyframes blink{
    50%{opacity:0}
}

/* ================= BUTTONS ================= */

.btn{
    border:0;
    border-radius:10px;
    padding:14px 25px;
    background:var(--green);
    color:#03110b;
    font-weight:800;
    cursor:pointer;
    font-family:Tahoma;
    transition:.25s;
}

.btn:hover{
    transform:translateY(-3px) scale(1.02);
    box-shadow:0 15px 45px rgba(88,245,178,.2);
}

.ghost{
    background:transparent;
    color:#c9d4e3;
    border:1px solid #2b3c51;
    margin-right:8px;
}

.hint{
    color:#65748a;
    font-size:11px;
    margin-top:13px;
}

/* ================= SECTIONS ================= */

section{
    padding:105px 6%;
}

.container{
    max-width:1100px;
    margin:auto;
}

.title{
    text-align:center;
    margin-bottom:45px;
}

.title small{
    font:11px Consolas;
    color:var(--green);
    letter-spacing:3px;
}

.title h2{
    font-size:36px;
    margin:11px 0;
}

.title p{
    color:var(--muted);
}

/* ================= CARDS ================= */

.grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:18px;
}

.card{
    position:relative;
    background:
        linear-gradient(145deg,#0b121c,#070b12);
    border:1px solid var(--line);
    border-radius:17px;
    padding:26px;
    min-height:210px;
    transition:.3s;
    overflow:hidden;
}

.card:before{
    content:"";
    position:absolute;
    width:100px;
    height:100px;
    background:var(--green);
    filter:blur(80px);
    opacity:.04;
    top:-40px;
    left:-40px;
}

.card:hover{
    transform:translateY(-9px);
    border-color:#3d5876;
    box-shadow:0 20px 50px rgba(0,0,0,.3);
}

.num{
    font:11px Consolas;
    color:#53647a;
}

.card h3{
    margin:15px 0 10px;
}

.card p{
    color:#8998aa;
    line-height:1.9;
    font-size:14px;
}

/* ================= CODE ================= */

.codeSection{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:25px;
    align-items:center;
}

.info h2{
    font-size:34px;
}

.info p{
    color:#9aa7b9;
    line-height:2;
}

.pill{
    display:inline-block;
    border:1px solid #26374b;
    border-radius:999px;
    padding:7px 11px;
    color:#9caabd;
    font-size:11px;
    margin:4px;
}

.codeCard{
    background:#060a10;
    border:1px solid var(--line);
    border-radius:17px;
    overflow:hidden;
    box-shadow:0 25px 70px rgba(0,0,0,.3);
}

.codeHead{
    padding:14px 18px;
    border-bottom:1px solid var(--line);
    font:12px Consolas;
    color:#7f8da0;
}

.codeBody{
    padding:20px;
    font:13px/2 Consolas;
    direction:ltr;
    text-align:left;
    min-height:270px;
}

.codeLine{
    padding:3px 8px;
    border-radius:6px;
    transition:.2s;
    cursor:pointer;
}

.codeLine:hover{
    background:#101b29;
    color:#fff;
    transform:translateX(-4px);
    box-shadow:inset 3px 0 var(--green);
}

/* ================= CODING CHALLENGE ================= */

.challenge{
    background:
        linear-gradient(145deg,#080e17,#050910);
    border:1px solid #26384e;
    border-radius:20px;
    padding:28px;
    box-shadow:0 25px 80px rgba(0,0,0,.35);
}

.challengeTop{
    display:flex;
    justify-content:space-between;
    align-items:center;
}

.challengeTop h3{
    margin:0;
}

.level{
    color:var(--green);
    font:11px Consolas;
}

.progress{
    height:5px;
    background:#142031;
    border-radius:99px;
    margin:18px 0;
    overflow:hidden;
}

.progressBar{
    width:0%;
    height:100%;
    background:linear-gradient(90deg,var(--green),var(--cyan));
    transition:.5s;
}

.miniCode{
    background:#03060a;
    border:1px solid #1e2b3c;
    border-radius:13px;
    padding:20px;
    margin:18px 0;
    font:14px/2 Consolas;
    direction:ltr;
    text-align:left;
}

.inputRow{
    display:flex;
    gap:10px;
}

.inputRow input{
    flex:1;
    background:#060a10;
    color:#e8eef7;
    border:1px solid #2a3a4e;
    border-radius:9px;
    padding:14px;
    font:14px Consolas;
    outline:none;
}

.inputRow input:focus{
    border-color:var(--green);
    box-shadow:0 0 20px rgba(88,245,178,.08);
}

.result{
    margin-top:15px;
    min-height:25px;
    color:var(--green);
    font-size:13px;
    font-family:Consolas;
}

/* ================= MESSAGE ================= */

.letter{
    max-width:800px;
    margin:auto;
    background:
        linear-gradient(145deg,#0a111b,#070b12);
    border:1px solid var(--line);
    border-radius:20px;
    padding:38px;
    line-height:2.5;
    color:#b7c3d2;
    box-shadow:0 20px 70px rgba(0,0,0,.25);
}

.letter strong{
    color:var(--green);
}

/* ================= FINAL ================= */

.final{
    text-align:center;
}

.lock{
    width:125px;
    height:125px;
    border-radius:50%;
    border:1px solid #30445c;
    display:grid;
    place-items:center;
    margin:0 auto 25px;
    font-size:48px;
    background:#080e16;
    box-shadow:
        0 0 50px rgba(73,233,255,.05),
        inset 0 0 30px rgba(73,233,255,.03);
    transition:.5s;
}

.final h2{
    font-size:40px;
}

.final p{
    color:#99a7b9;
}

.hidden{
    display:none;
}

.glow{
    animation:glow 1.2s infinite alternate;
}

@keyframes glow{
    from{
        box-shadow:0 0 20px rgba(88,245,178,.1);
    }
    to{
        box-shadow:0 0 65px rgba(88,245,178,.4);
    }
}

/* ================= FOOTER ================= */

footer{
    text-align:center;
    padding:45px;
    color:#536174;
    border-top:1px solid #172131;
    font:11px Consolas;
}

/* ================= MOBILE ================= */

@media(max-width:800px){

    .grid,
    .codeSection{
        grid-template-columns:1fr;
    }

    nav a{
        display:none;
    }

    .hero h1{
        letter-spacing:-4px;
    }

    .inputRow{
        flex-direction:column;
    }

    .letter{
        padding:25px;
    }
}
</style>
</head>

<body>

<!-- ================= PARTICLES ================= -->

<script>
for(let i=0;i<70;i++){

    const p=document.createElement("div");

    p.className="particle";

    p.style.left=Math.random()*100+"vw";
    p.style.animationDuration=(5+Math.random()*15)+"s";
    p.style.animationDelay=Math.random()*10+"s";

    document.body.appendChild(p);
}
</script>

<!-- ================= NAV ================= -->

<nav>

<div class="brand">
Roham<span>.dev</span>
</div>

<div>
<a href="#story">STORY</a>
<a href="#code">CODE</a>
<a href="#challenge">CHALLENGE</a>
<a href="#final">SURPRISE</a>
</div>

</nav>


<!-- ================= HERO ================= -->

<header class="hero">

<div class="heroBox">

<div class="eyebrow">
// SPECIAL BUILD FOR MY FATHER
</div>

<h1>
Father<span>.exe</span>
</h1>

<p>
امروز قرار نیست فقط یک سایت ببینی؛
<br>
قرار است یک پروژه‌ی کوچک، مخصوص <b>پدر</b> اجرا شود. ❤️
</p>


<div class="window">

<div class="bar">

<i class="ball"></i>
<i class="ball"></i>
<i class="ball"></i>

<span class="path">
~/special-project/Father.exe
</span>

</div>

<div class="screen" id="boot"></div>

</div>


<button
class="btn"
onclick="document.querySelector('#story').scrollIntoView()">

START EXPERIENCE →

</button>

<div class="hint">
Tip: وارد پروژه شو؛ چند خط کد هم منتظر تو هستند.
</div>

</div>

</header>


<!-- ================= STORY ================= -->

<section id="story">

<div class="container">

<div class="title">

<small>01 / WHY THIS EXISTS</small>

<h2>
برای بهترین پدر پشت سیستم
</h2>

<p>
کمی کد، کمی خاطره و یک عالمه قدردانی.
</p>

</div>


<div class="grid">

<div class="card">

<div class="num">
01 — LESSON
</div>

<h3>
تلاش
</h3>

<p>
از تو یاد گرفتم اگر یک راه جواب نداد،
می‌شود راه دیگری ساخت.
</p>

</div>


<div class="card">

<div class="num">
02 — DEBUG
</div>

<h3>
صبوری
</h3>

<p>
اشتباه کردن پایان کار نیست؛
گاهی فقط یک باگ کوچک است که باید پیدایش کرد.
</p>

</div>


<div class="card">

<div class="num">
03 — LIFE
</div>

<h3>
الهام
</h3>

<p>
ممنونم که همیشه با رفتار و کارت به من نشان دادی
دنبال چیزی بروم که واقعاً دوستش دارم.
</p>

</div>

</div>

</div>

</section>


<!-- ================= CODE ================= -->

<section id="code">

<div class="container">

<div class="codeSection">


<div class="info">

<div class="title"
style="text-align:right;margin-bottom:15px">

<small>
02 / SOURCE CODE
</small>

<h2>
کدی که برای پدر نوشته شد
</h2>

</div>

<p>
این قسمت فقط یک نمایش نیست.
روی خطوط کد برو و ببین چطور پروژه زنده می‌شود.
</p>

<span class="pill">
JavaScript
</span>

<span class="pill">
FatherOS
</span>

<span class="pill">
Love.js
</span>

<span class="pill">
Roham.exe
</span>

</div>


<div class="codeCard">

<div class="codeHead">
father.js — hover / click to type
</div>

<div class="codeBody">

<div class="codeLine typeLine">
const father = {
</div>

<div class="codeLine typeLine">
&nbsp;&nbsp;developer:
<span class="g">true</span>,
</div>

<div class="codeLine typeLine">
&nbsp;&nbsp;patience:
<span class="g">"∞"</span>,
</div>

<div class="codeLine typeLine">
&nbsp;&nbsp;kindness:
<span class="g">"infinite"</span>,
</div>

<div class="codeLine typeLine">
&nbsp;&nbsp;support:
<span class="g">"always"</span>,
</div>

<div class="codeLine typeLine">
&nbsp;&nbsp;status:
<span class="g">"BEST_FATHER"</span>
</div>

<div class="codeLine typeLine">
};
</div>

<br>

<div class="codeLine typeLine">
<span class="b">console</span>.log(
<span class="g">
"Happy Programmer's Day, Father!"
</span>);
</div>

</div>

</div>

</div>

</div>

</section>


<!-- ================= CHALLENGE ================= -->

<section id="challenge">

<div class="container">

<div class="title">

<small>
03 / LIVE CODING
</small>

<h2>
حالا نوبت خود برنامه‌نویسه 👨‍💻
</h2>
```html
<section id="challenge">

<div class="container">

<div class="title">
    <small>03 / WRITE YOUR CODE</small>
    <h2>حالا خودت کد بزن 👨‍💻</h2>
    <p>
        یک پیام برای خودت بنویس و با JavaScript اجراش کن.
    </p>
</div>


<div class="challenge">

<div class="challengeTop">
    <h3>⌨️ Father Coding Terminal</h3>
    <span class="level">LIVE CODE</span>
</div>


<div class="codeEditor">

<div class="editorTop">
    <span class="dot red"></span>
    <span class="dot yellow"></span>
    <span class="dot green"></span>

    <span class="fileName">
        message.js
    </span>
</div>


<div class="editorBody">

<div class="lineNumber">1</div>

<textarea
id="codeInput"
spellcheck="false"
placeholder='console.log("روزت مبارک پدر ❤️");'
></textarea>

</div>

</div>


<div class="codeHelp">

💡 راهنما:

<br>

با دستور

<code>console.log()</code>

یک پیام بنویس.

<br><br>

مثلاً:

<code>
console.log("روزت مبارک پدر ❤️");
</code>

</div>


<button
class="btn"
onclick="runFatherCode()">

▶ RUN CODE

</button>


<div class="terminalOutput">

<div class="terminalHeader">
    TERMINAL
</div>

<div id="terminalText">
    منتظر اجرای کد...
</div>

</div>


</div>

</div>

</section>


<style>

/* ================= CODE EDITOR ================= */

.codeEditor{
    margin-top:25px;
    background:#03060a;
    border:1px solid #26384d;
    border-radius:15px;
    overflow:hidden;
    box-shadow:
        0 25px 80px rgba(0,0,0,.4),
        0 0 35px rgba(88,245,178,.03);
}

.editorTop{
    height:45px;
    display:flex;
    align-items:center;
    gap:8px;
    padding:0 16px;
    border-bottom:1px solid #1b2939;
    background:#080d14;
}

.dot{
    width:10px;
    height:10px;
    border-radius:50%;
}

.red{
    background:#ff5f57;
}

.yellow{
    background:#ffbd2e;
}

.green{
    background:#28c840;
}

.fileName{
    margin-right:10px;
    color:#7d8da3;
    font:12px Consolas,monospace;
    direction:ltr;
}

.editorBody{
    display:flex;
    min-height:180px;
}

.lineNumber{
    width:55px;
    padding:20px 15px;
    background:#05080d;
    color:#43536a;
    font:14px/2 Consolas,monospace;
    text-align:right;
    user-select:none;
}

#codeInput{
    flex:1;
    resize:none;
    border:0;
    outline:0;
    padding:20px;
    background:#05080d;
    color:#6ee7b7;
    font:15px/2 Consolas,monospace;
    direction:ltr;
    text-align:left;
    min-height:180px;
}

#codeInput::placeholder{
    color:#34465c;
}

#codeInput:focus{
    box-shadow:
        inset 3px 0 #58f5b2;
}


/* ================= HELP ================= */

.codeHelp{
    margin:18px 0;
    padding:16px 18px;
    border:1px solid #203147;
    border-radius:12px;
    background:#080e16;
    color:#8998aa;
    line-height:1.9;
    font-size:13px;
}

.codeHelp code{
    color:#58f5b2;
    background:#03070b;
    border:1px solid #1d2a3a;
    padding:3px 7px;
    border-radius:5px;
    font-family:Consolas,monospace;
    direction:ltr;
}


/* ================= TERMINAL ================= */

.terminalOutput{
    margin-top:20px;
    border:1px solid #26384d;
    border-radius:13px;
    overflow:hidden;
    background:#03060a;
    direction:ltr;
    text-align:left;
}

.terminalHeader{
    padding:11px 15px;
    background:#080d14;
    border-bottom:1px solid #1b2939;
    color:#63748a;
    font:11px Consolas,monospace;
}

#terminalText{
    padding:20px;
    min-height:90px;
    color:#58f5b2;
    font:14px/2 Consolas,monospace;
    white-space:pre-wrap;
}

</style>


<script>

function runFatherCode(){

    const code =
        document
        .getElementById("codeInput")
        .value
        .trim();

    const terminal =
        document
        .getElementById("terminalText");


    if(!code){

        terminal.innerHTML =
            '<span style="color:#ffd166">' +
            '> لطفاً اول کدت را بنویس...' +
            '</span>';

        return;
    }


    /*
       صدای تایپ
    */

    clickSound();


    terminal.innerHTML =
        '> Running FatherOS...';


    setTimeout(()=>{

        terminal.innerHTML =
            '> Running FatherOS...\n' +
            '> Executing JavaScript...';

    },500);


    setTimeout(()=>{

        /*
           بررسی console.log
        */

        const match =
            code.match(
                /console\.log\s*\(\s*["'`](.*?)["'`]\s*\)/
            );


        if(match){

            const message =
                match[1];

            terminal.innerHTML =
                '<span style="color:#58f5b2">' +
                '> Code executed successfully ✓' +
                '</span>\n\n' +
                '<span style="color:#fff">' +
                message +
                '</span>';

            createTypingEffect(message);

        }else{

            terminal.innerHTML =
                '<span style="color:#ff5577">' +
                '> Error: کد صحیح نیست.' +
                '</span>\n\n' +
                '<span style="color:#8190a5">' +
                'راهنما: console.log("پیام شما")' +
                '</span>';

        }

    },1000);

}


/* ================= TYPING EFFECT ================= */

function createTypingEffect(message){

    const terminal =
        document.getElementById("terminalText");

    terminal.innerHTML =
        '<span style="color:#58f5b2">' +
        '> Output: ' +
        '</span>';

    let i=0;

    const text=
        document.createElement("span");

    text.style.color="#ffffff";

    terminal.appendChild(text);


    function type(){

        if(i < message.length){

            text.textContent +=
                message[i];

            i++;

            setTimeout(type,45);

        }

    }

    type();

}

</script>
```

<p>
پدر فقط تماشاچی نیست؛ باید یک کد واقعی بنویسد.
</p>

</div>


<div class="challenge">

<div class="challengeTop">

<h3>
🎯 Coding Challenge #001
</h3>

<span class="level">
LEVEL 01 / EASY
</span>

</div>


<div class="progress">
<div class="progressBar" id="progress"></div>
</div>


<p style="color:#9aa7b9">

یک جمله بنویس که با JavaScript در کنسول چاپ شود.

<br>

راهنمایی:

<b style="color:#58f5b2">
console.log()
</b>

استفاده کن.

</p>


<div class="miniCode">

<span class="p">
console
</span>.log(

<span class="g">
"YOUR MESSAGE"
</span>

);

</div>


<div class="inputRow">

<input
id="answer"
placeholder="مثلاً: Happy Programmer's Day Father!"
autocomplete="off"
>

<button
class="btn"
onclick="checkCode()">

RUN CODE ▶

</button>

</div>


<div
class="result"
id="result">
</div>

</div>

</div>

</section>


<!-- ================= SECOND CHALLENGE ================= -->

<section>

<div class="container">

<div class="title">

<small>
04 / SECRET CODE
</small>

<h2>
مرحله دوم؛ کمی سخت‌تر
</h2>

<p>
حالا باید نام برنامه‌نویس این پروژه را چاپ کنی.
</p>

</div>


<div class="challenge">

<div class="challengeTop">

<h3>
🔐 Coding Challenge #002
</h3>

<span class="level">
LEVEL 02 / MEDIUM
</span>

</div>


<p style="color:#9aa7b9">

کدی بنویس که خروجی آن دقیقاً باشد:

</p>


<div class="miniCode">

<span class="g">
Roham
</span>

</div>


<div class="inputRow">

<input
id="answer2"
placeholder='مثلاً: console.log("Roham")'
autocomplete="off"
>

<button
class="btn"
onclick="checkCode2()">

EXECUTE ▶

</button>

</div>


<div
class="result"
id="result2">
</div>

</div>

</div>

</section>


<!-- ================= LETTER ================= -->

<section>

<div class="container">

<div class="title">

<small>
05 / MESSAGE
</small>

<h2>
یک پیام کوتاه
</h2>

</div>


<div class="letter">

پدر جان،<br>

این سایت شاید از نظر فنی یک پروژه‌ی خیلی بزرگ نباشد،
اما برای من یک معنی بزرگ دارد.

خواستم چیزی بسازم که مخصوص خودت باشد؛
چیزی که وقتی می‌بینی، بدانی که به تو افتخار می‌کنم.

<br><br>

<strong>
روز برنامه‌نویس مبارک، پدر. ❤️
</strong>

<br>

ممنون که همیشه الهام‌بخش من بودی.

<br><br>

با عشق،
<strong>
رهام
</strong>

</div>

</div>

</section>


<!-- ================= FINAL ================= -->

<section id="final">

<div class="container final">

<div class="title">

<small>
06 / FINAL BUILD
</small>

<h2>
فایل نهایی آماده است...
</h2>

</div>


<div
class="lock"
id="lock">

🔒

</div>


<button
class="btn"
id="unlock"
onclick="unlock()">

UNLOCK FINAL SURPRISE

</button>


<div
id="finalMsg"
class="hidden">

<h2>
🎉 HAPPY PROGRAMMER'S DAY 🎉
</h2>

<p>
بهترین برنامه‌نویس و بهترین پدر من ❤️
</p>

<p style="color:#58f5b2">

No bugs.
No limits.
Just love.

</p>

</div>

</div>

</section>


<footer>

Built with &lt;/&gt; + ❤️ by Roham
//
Father.exe 2026

</footer>


<script>

/* ==================================================
   TERMINAL BOOT
================================================== */

const bootLines=[

'> initializing Father.exe...',

'> loading memories... <span class="g">OK</span>',

'> connecting to FatherOS... <span class="g">CONNECTED</span>',

'> loading developer-module... <span class="g">OK</span>',

'> checking father-level... <span class="y">LEGENDARY</span>',

'> compiling gratitude... <span class="g">100%</span>',

'> searching for bugs... <span class="g">0 FOUND</span>',

'> loading love-module... <span class="p">∞%</span>',

'> <span class="c">SYSTEM READY.</span>',

'> Welcome, Father <span class="cursor"></span>'

];

let bi=0;
let bc=0;

const boot=document.getElementById("boot");


function bootType(){

    if(bi>=bootLines.length)
        return;

    const line=bootLines[bi];

    if(bc<=line.length){

        boot.innerHTML=
            bootLines
            .slice(0,bi)
            .join("<br>")
            +(bi?"<br>":"")
            +line.slice(0,bc);

        bc++;

        setTimeout(bootType,16);

    }else{

        bi++;
        bc=0;

        setTimeout(bootType,160);

    }

}

bootType();


/* ==================================================
   KEYBOARD SOUND
================================================== */

let audioCtx;


function clickSound(){

    try{

        audioCtx=
            audioCtx ||
            new(window.AudioContext ||
            window.webkitAudioContext)();

        const o=
            audioCtx.createOscillator();

        const g=
            audioCtx.createGain();

        o.type="square";

        o.frequency.value=
            500+
            Math.random()*500;

        g.gain.value=.015;

        o.connect(g);

        g.connect(audioCtx.destination);

        o.start();

        o.stop(
            audioCtx.currentTime+.035
        );

    }catch(e){}

}


/* ==================================================
   CODE HOVER
================================================== */

document
.querySelectorAll(".typeLine")
.forEach(line=>{

    line.addEventListener(
        "mouseenter",
        ()=>{

            clickSound();

            line.style.transform=
                "translateX(-4px)";

            setTimeout(
                ()=>{
                    line.style.transform="";
                },
                180
            );

        }
    );

    line.addEventListener(
        "click",
        clickSound
    );

});


/* ==================================================
   CHALLENGE 01
================================================== */

function checkCode(){

    const input=
        document.getElementById("answer");

    const result=
        document.getElementById("result");

    const progress=
        document.getElementById("progress");

    const value=
        input.value.trim();


    if(!value){

        result.textContent=
            "💡 اول یک جمله بنویس.";

        return;
    }


    clickSound();


    result.innerHTML=
        "▶ Running code...";

    progress.style.width="35%";


    setTimeout(()=>{

        result.innerHTML=
            "✓ Output: "+value;

        progress.style.width="65%";

    },600);


    setTimeout(()=>{

        result.innerHTML=
            "✓ SUCCESS — کد با موفقیت اجرا شد! 🚀";

        progress.style.width="100%";

    },1200);

}


/* ==================================================
   CHALLENGE 02
================================================== */

function checkCode2(){

    const value=
        document
        .getElementById("answer2")
        .value
        .trim();

    const result=
        document.getElementById("result2");


    if(!value){

        result.textContent=
            "💡 یک کد وارد کن.";

        return;

    }


    clickSound();


    const normalized=
        value
        .replace(/\s/g,"")
        .toLowerCase();


    if(
        normalized.includes("console.log") &&
        normalized.includes("roham")
    ){

        result.innerHTML=
            "✓ ACCESS GRANTED — ROHAM DETECTED 🚀";

    }else{

        result.innerHTML=
            "⚠️ کد اجرا نشد. راهنما: console.log(\"Roham\")";

    }

}


/* ==================================================
   FINAL SURPRISE
================================================== */

function unlock(){

    clickSound();


    const lock=
        document.getElementById("lock");

    const button=
        document.getElementById("unlock");

    const finalMsg=
        document.getElementById("finalMsg");


    lock.textContent="🔓";

    lock.classList.add("glow");

    button.style.display="none";

    finalMsg.classList.remove("hidden");


    /* fireworks */

    for(let i=0;i<70;i++){

        const s=
            document.createElement("span");

        const symbols=[
            "💚",
            "✨",
            "💻",
            "❤️",
            "🎉",
            "⚡",
            "⭐"
        ];

        s.textContent=
            symbols[
                Math.floor(
                    Math.random()*symbols.length
                )
            ];


        s.style.cssText=`

            position:fixed;

            left:${Math.random()*100}vw;

            top:-30px;

            font-size:${14+
                Math.random()*25}px;

            z-index:1000;

            pointer-events:none;

            transition:
                transform 2.5s ease,
                opacity 2.5s;

        `;


        document.body.appendChild(s);


        setTimeout(()=>{

            s.style.transform=
                `translateY(${innerHeight+100}px)
                 rotate(${Math.random()*1000-500}deg)`;

            s.style.opacity=0;

        },30);


        setTimeout(
            ()=>s.remove(),
            2700
        );

    }

}

</script>

</body>
</html>
```
