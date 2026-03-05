
<html lang="vi">

<head>
<meta charset="UTF-8">
<title>Special Gift</title>

<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&display=swap&subset=vietnamese" rel="stylesheet">

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial, sans-serif;
}

body{
height:100vh;
background:url("background.jpg");
background-size:cover;
background-position:center;
overflow:hidden;
}


.title{
font-family:'Dancing Script', cursive;

position:absolute;
top:40px;
left:50%;
transform:translateX(-50%);

font-size:80px;
color:white;
text-align:center;

text-shadow:
0 0 8px #ffb6c9,
0 0 18px #ff8fb1,
0 0 30px #ff6f9f;
}

/* CÂU DƯỚI TIÊU ĐỀ */

.subtitle{
position:absolute;
top:140px;
left:50%;
transform:translateX(-50%);

color:white;
font-size:22px;
font-style:italic;
text-align:center;

text-shadow:0 0 10px rgba(255,255,255,0.6);
}

/* HỘP CÂU HỎI */

.box{
position:absolute;
top:50%;
left:50%;
transform:translate(-50%,-50%);

background:rgba(0,0,0,0.7);
padding:35px;
border-radius:18px;

color:white;
text-align:center;
width:320px;
}

/* CÂU HỎI */

.question{
font-size:20px;
margin-bottom:20px;
}

/* INPUT */

input{
padding:10px;
width:100%;
border:none;
border-radius:8px;
margin-bottom:15px;
}

/* BUTTON */

button{
padding:10px 25px;
background:#ff4f8b;
border:none;
color:white;
border-radius:10px;
font-size:16px;
cursor:pointer;
}

/* TIM BAY */

.heart{
position:fixed;
bottom:-40px;
font-size:20px;
animation:fly 6s linear infinite;
}

@keyframes fly{
0%{
transform:translateY(0);
opacity:1;
}
100%{
transform:translateY(-110vh);
opacity:0;
}
}

</style>
</head>

<body>

<h1 class="title">
A Puzzle Made Just For You
</h1>

<p class="subtitle">
A few questions, a few memories, and a little surprise waiting.
</p>

<div class="box">

<div id="question" class="question">
Câu 1: Ngày đầu tiên mình gặp nhau là ngày nào?
</div>

<input id="answer" placeholder="Nhập câu trả lời">

<button onclick="check()">Trả lời</button>

</div>

<script>

/* CÂU HỎI */

const questions=[
"Câu 1: Ngày đầu tiên mình gặp nhau là ngày nào?",
"Câu 2: Món ăn em thích nhất là gì?",
"Câu 3: Ai là người tỏ tình trước?",
"Câu 4: Lần đầu mình đi chơi ở đâu?",
"Câu 5: Anh hay gọi em bằng biệt danh gì?"
]

const answers=[
"dd/mm/yyyy",
"sushi",
"anh",
"cafe",
"bé"
]

let current=0

function check(){

let input=document.getElementById("answer").value.toLowerCase()

if(input==answers[current]){

current++

if(current==questions.length){

document.querySelector(".box").innerHTML=
"<h2>Chúc em 8/3 thật vui ❤️</h2><br>Anh luôn thương em."

return
}

document.getElementById("question").innerText=questions[current]
document.getElementById("answer").value=""

}else{

alert("Sai rồi nha 😝")

}

}

/* TIM BAY */

function createHeart(){

let heart=document.createElement("div")
heart.className="heart"
heart.innerHTML="❤️"

heart.style.left=Math.random()*100+"vw"
heart.style.fontSize=Math.random()*20+10+"px"
heart.style.animationDuration=Math.random()*3+4+"s"

document.body.appendChild(heart)

setTimeout(()=>{
heart.remove()
},6000)

}

setInterval(createHeart,500)

</script>

</body>
</html>
