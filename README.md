<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Trò chơi 8/3</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family: Arial, sans-serif;
}

body{
height:100vh;
display:flex;
justify-content:center;
align-items:center;
background:url("background.jpg");
background-size:cover;
background-position:center;
overflow:hidden;
}

/* hộp câu hỏi */

.box{
background:rgba(0,0,0,0.75);
padding:40px;
border-radius:20px;
text-align:center;
color:white;
width:350px;
}

/* câu hỏi */

.question{
font-size:20px;
margin-bottom:20px;
}

/* input */

input{
padding:10px;
width:100%;
border:none;
border-radius:8px;
margin-bottom:15px;
}

/* nút */

button{
padding:10px 25px;
background:#ff4f8b;
border:none;
color:white;
border-radius:10px;
font-size:16px;
cursor:pointer;
}

/* tim bay */

.heart{
position:fixed;
bottom:-50px;
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

<div class="box">

<div id="question" class="question">
Câu 1: Ngày đầu tiên mình gặp nhau là ngày nào?
</div>

<input id="answer" placeholder="Nhập câu trả lời">

<br>

<button onclick="check()">Trả lời</button>

</div>

<script>

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

/* tạo tim bay */

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
