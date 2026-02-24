<!DOCTYPE html>  
<html>  
<head>  
<meta charset="UTF-8">  
<title>Happy Birthday Ibabdat ✨</title>  
  
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>  
  
<style>  
body{  
margin:0;  
padding:0;  
font-family:Arial, sans-serif;  
background:linear-gradient(135deg,#ff9a9e,#fad0c4);  
display:flex;  
justify-content:center;  
align-items:center;  
height:100vh;  
overflow:hidden;  
}  
  
.card{  
background:white;  
padding:25px;  
border-radius:20px;  
width:90%;  
max-width:360px;  
box-shadow:0 15px 35px rgba(0,0,0,0.2);  
text-align:center;  
position:relative;  
z-index:2;  
}  
  
h1{  
color:#ff4d6d;  
margin-bottom:10px;  
}  
  
#text{  
min-height:60px;  
white-space:pre-line;  
transition:0.4s;  
}  
  
button{  
margin-top:15px;  
padding:10px 20px;  
border:none;  
border-radius:10px;  
background:#ff4d6d;  
color:white;  
font-size:15px;  
cursor:pointer;  
}  
  
#slideshow{  
width:100%;  
height:260px;  
border-radius:15px;  
margin-top:15px;  
object-fit:cover;  
display:none;  
animation:fade 1.5s ease-in-out;  
}  
  
@keyframes fade{  
from{opacity:0;}  
to{opacity:1;}  
}  
  
/* Glow effect */  
.glow{  
font-size:22px;  
font-weight:bold;  
color:#ff2e63;  
animation:glow 2s infinite alternate;  
}  
  
@keyframes glow{  
from{  
text-shadow:0 0 10px #ff4d6d, 0 0 20px #ff85a2;  
}  
to{  
text-shadow:0 0 20px #ff2e63, 0 0 40px #ff85a2;  
}  
}  
  
/* balloons */  
.balloon{  
position:absolute;  
bottom:-100px;  
width:35px;  
opacity:0.6;  
animation:float 10s infinite ease-in;  
}  
  
@keyframes float{  
0%{transform:translateY(0);}  
100%{transform:translateY(-120vh);}  
}  
</style>  
</head>  
  
<body>  
  
<audio id="bgMusic" loop>  
<source src="khwab.mp3" type="audio/mpeg">  
</audio>  
  
<img src="https://i.imgur.com/7yUvePI.png" class="balloon" style="left:20%;">  
<img src="https://i.imgur.com/7yUvePI.png" class="balloon" style="left:65%; animation-delay:3s;">  
  
<div class="card">  
<h1>Hey Pari ✨</h1>  
<p id="text">Ready Ibabdat? 💖</p>  
  
<img id="slideshow" src="photo1.jpg">  
  
<button onclick="next()">Next 💌</button>  
  
<div id="finalChoice" style="display:none; margin-top:10px;">  
<button onclick="finalYes()">Best Friend Forever? 💕</button>  
</div>  
  
</div>  
  
<script>  
  
let step=0;  
let musicStarted=false;  
  
let photos=["photo1.jpg","photo2.jpg","photo3.jpg","Photo4.jpg"];  
let currentPhoto=0;  
  
let messages=[  
  
"2 March… ek khaas din 🌸",  
  
"Is din duniya ko mili ek pyari si Pari ✨",  
  
"5 foot ki choti si height,\npar dil sabse bada 💗",  
  
"Jubaan thodi kadvi ho sakti hai,\npar niyat hamesha saaf 😌",  
  
"Ibabdat naam hi kaafi hai…\nkyunki tum waqai special ho 💖",  
  
"Choti si muskaan me duniya basa leti ho,\nThodi si zid me bhi pyaar jata leti ho 💌",  
  
"Aaj tumhara birthday hai 🎂\nAur tum deserve karti ho har khushi ✨",  
  
"Thank you for being you 💕",  
  
"HAPPY BIRTHDAY IBABDAT PARI 💖✨"  
];  
  
function showNextPhoto(){  
let img=document.getElementById("slideshow");  
img.src=photos[currentPhoto];  
img.style.display="block";  
currentPhoto++;  
if(currentPhoto>=photos.length){  
currentPhoto=0;  
}  
}  
  
function next(){  
  
if(!musicStarted){  
document.getElementById("bgMusic").play();  
musicStarted=true;  
}  
  
if(step < messages.length){  
document.getElementById("text").innerText=messages[step];  
showNextPhoto();  
step++;  
}  
  
if(step===messages.length){  
confetti({particleCount:200,spread:130,origin:{y:0.6}});  
document.getElementById("text").innerHTML="<span class='glow'>IBABDAT PARI ✨💖</span><br>Forever Special 🌸";  
document.getElementById("finalChoice").style.display="block";  
document.querySelector("button").style.display="none";  
}  
  
}  
  
function finalYes(){  
document.getElementById("text").innerHTML="<span class='glow'>Forever & Always 💖</span><br>You are truly special ✨";  
confetti({particleCount:250,spread:150});  
}  
  
</script>  
  
</body>  
</html>  
