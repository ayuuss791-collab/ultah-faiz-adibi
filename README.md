<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Untuk FAIZ ADIBI ❤️</title>

<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Segoe UI', sans-serif;
}

body{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
    color:white;
    overflow:hidden;
    background: linear-gradient(135deg,#ff758c,#ff7eb3,#8e2de2,#4a00e0);
}

.container{
    position:relative;
    z-index:2;
    max-width:350px;
    padding:25px;
    background:rgba(0,0,0,0.4);
    border-radius:20px;
    backdrop-filter:blur(10px);
}

h1{
    font-size:22px;
    margin-bottom:15px;
}

p{
    font-size:16px;
    line-height:1.6;
}

.tap{
    margin-top:20px;
    font-size:13px;
    opacity:0.7;
}

/* STIKER */
.sticker{
    position:absolute;
    font-size:28px;
    animation:floatUp 4s linear forwards;
    z-index:1;
}

@keyframes floatUp{
    0%{transform:translateY(0);opacity:1;}
    100%{transform:translateY(-300px);opacity:0;}
}
</style>
</head>

<body onclick="nextSlide()">

<div class="container" id="content">
    <h1 id="title">Hai FAIZ ADIBI ❤️</h1>
    <p id="text">Aku punya sesuatu buat kamu...</p>
    <div class="tap">Tap di mana saja ✨</div>
</div>

<script>

let slide = 0;

const slides = [
"Katanya 10 Maret itu cuma tanggal biasa... tapi buat aku, itu hari lahirnya laki-laki paling spesial 🤍",
"Kalau ulang tahun itu nambah umur, semoga kamu juga nambah sabar buat hadapi aku yang manja ini 😌",
"Aku nggak minta kamu jadi sempurna. Aku cuma minta kamu tetap jadi kamu… karena itu yang bikin aku jatuh cinta.",
"Dan sebelum masuk ke halaman utama... aku cuma mau bilang: aku bersyukur banget punya kamu 💙"
];

function nextSlide(){
    slide++;

    if(slide <= slides.length){
        document.getElementById("text").innerHTML = slides[slide-1];
        createSticker();
    }

    if(slide === slides.length){
        setTimeout(showMainPage,1000);
    }
}

function showMainPage(){
    document.getElementById("content").innerHTML = `
        <h1>Happy Birthday ❤️</h1>
        <h2 style="color:#ffd369;">FAIZ ADIBI</h2>
        <p>
        10 Maret 2005 kamu lahir ke dunia ini.  
        Semoga umur 21 ini penuh kebahagiaan dan rezeki.  
        Aku bangga punya kamu 🤍
        </p>
    `;

    confetti({particleCount:200,spread:120,origin:{y:0.6}});
    createStickerBurst();

    // PRANK setelah 3 detik
    setTimeout(prankSlide,3000);
}

function prankSlide(){
    document.getElementById("content").innerHTML = `
        <h1>Eh BOONG 😭</h1>
        <p style="font-size:18px;">
        Umur kamu yang bener 22 ya??  
        KTP kamu kamu mudakan ya?? 😏  
        </p>
    `;

    confetti({particleCount:150,spread:150,origin:{y:0.5}});
    createStickerBurst();
}

function createSticker(){
    const emojis = ["💖","✨","🎉","💘","🥰","🌸"];
    const sticker = document.createElement("div");
    sticker.className="sticker";
    sticker.innerText=emojis[Math.floor(Math.random()*emojis.length)];
    sticker.style.left=Math.random()*100+"vw";
    sticker.style.top="80vh";
    document.body.appendChild(sticker);

    setTimeout(()=>sticker.remove(),4000);
}

function createStickerBurst(){
    for(let i=0;i<10;i++){
        createSticker();
    }
}

</script>

</body>
</html>
