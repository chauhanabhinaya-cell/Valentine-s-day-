# Valentine-s-day-
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Valentine Card</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>

<style>
body{
margin:0;
font-family:Arial;
background:linear-gradient(#ff5fa2,#ff7bb8);
display:flex;
justify-content:center;
align-items:center;
height:100vh;
}

.card{
width:330px;
background:#fff;
border-radius:20px;
padding:20px;
text-align:center;
display:none;
box-shadow:0 10px 25px rgba(0,0,0,.2);
}

.card.active{display:block;}

h2{color:#ff3c86;}
p{color:#444;}

button{
padding:10px 18px;
border:none;
border-radius:20px;
background:#ff3c86;
color:white;
font-size:15px;
cursor:pointer;
}

.no{background:#eee;color:#333;}

ul{text-align:left;padding-left:18px;}

/* last photo animation */
.rotate-img{
width:160px;
height:160px;
border-radius:50%;
object-fit:cover;
animation:spin 6s linear infinite;
margin-top:10px;
}

@keyframes spin{
from{transform:rotate(0deg);}
to{transform:rotate(360deg);}
}
</style>
</head>

<body>

<!-- QR PAGE -->
<div class="card active" id="page0">
<h2>Scan this QR 💌</h2>
<p>Scan to open your Valentine surprise</p>

<div id="qrcode"></div>

<br>
<button onclick="goTo(1)">Already opened ➜</button>
</div>


<!-- PAGE 1 -->
<div class="card" id="page1">
<h2>Will you be my Valentine? 💗</h2>
<p>Think carefully 😌</p>

<button onclick="goTo(2)">Yes</button>
<button class="no" onclick="noClicked()">No</button>
</div>

<!-- PAGE 2 -->
<div class="card" id="page2">
<h2>I knew you'd say YES 💞</h2>
<p>You make my world brighter every day 💖</p>
<button onclick="goTo(3)">Next</button>
</div>

<!-- PAGE 3 -->
<div class="card" id="page3">
<h2>Reasons why I love you 💕</h2>
<ul>
<li>Your smile</li>
<li>Your kindness</li>
<li>Your care</li>
<li>Your honesty</li>
<li>Your heart</li>
</ul>
<button onclick="goTo(4)">Next</button>
</div>

<!-- PAGE 4 -->
<div class="card" id="page4">
<h2>My Valentine promise 💌</h2>
<p>
I promise to stand by you,<br>
make you smile and love you forever ❤️
</p>
<button onclick="goTo(5)">Final</button>
</div>

<!-- PAGE 5 (ROTATING PHOTO) -->
<div class="card" id="page5">
<h2>Happy Valentine's Day 💝</h2>

<img src="your-photo.jpg" class="rotate-img">

<p>You are my always 💗</p>
</div>

<script>

function goTo(n){
document.querySelectorAll(".card").forEach(c=>c.classList.remove("active"));
document.getElementById("page"+n).classList.add("active");
}

function noClicked(){
alert("Nice try 😅 Ab YES hi bacha hai ❤️");
}

/* QR generation */
var siteLink = "https://your-site-link-here.com";   // 🔴 yaha apna link daalna

new QRCode(document.getElementById("qrcode"), {
text: siteLink,
width:180,
height:180
});

</script>

</body>
</html>
