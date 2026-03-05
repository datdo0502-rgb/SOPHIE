<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Trò Chơi Bí Mật</title>

<style>
body{
    margin:0;
    padding:0;
    font-family: Arial, sans-serif;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;

    background-image:url("background.jpg");
    background-size:cover;
    background-position:center;
}

.box{
    background:rgba(0,0,0,0.65);
    padding:40px;
    border-radius:15px;
    text-align:center;
    color:white;
    width:400px;
}

input{
    padding:10px;
    width:80%;
    border-radius:8px;
    border:none;
    margin-top:15px;
}

button{
    margin-top:15px;
    padding:10px 20px;
    border:none;
    border-radius:8px;
    background:#ff6fa5;
    color:white;
    font-size:16px;
    cursor:pointer;
}

button:hover{
    background:#ff4f90;
}

#message{
    margin-top:15px;
    color:#ffb3d1;
}
</style>
</head>

<body>

<div class="box">

<h2 id="question">Câu hỏi sẽ hiện ở đây</h2>

<input id="answer" placeholder="Nhập câu trả lời...">

<br>

<button onclick="check()">Trả lời</button>

<p id="message"></p>

</div>

<script>

let questions = [

{
q:"Câu 1: Ngày đầu tiên mình gặp nhau là ngày nào?",
a:"15/08"
},

{
q:"Câu 2: Món ăn mà em thích nhất khi đi với anh?",
a:"lẩu"
},

{
q:"Câu 3: Biệt danh anh hay gọi em là gì?",
a:"bé"
},

{
q:"Câu 4: Ai là người tỏ tình trước?",
a:"anh"
},

{
q:"Câu 5: Màu em thích nhất?",
a:"hồng"
}

];

let current = 0;

function loadQuestion(){
document.getElementById("question").innerText = questions[current].q;
}

function check(){

let user = document.getElementById("answer").value.toLowerCase();
let correct = questions[current].a.toLowerCase();

if(user === correct){

current++;

if(current < questions.length){

document.getElementById("answer").value="";
document.getElementById("message").innerText="Đúng rồi đó ❤️";
loadQuestion();

}else{

document.querySelector(".box").innerHTML = `
<h2>Chúc mừng em đã vượt qua hết câu hỏi ❤️</h2>
<p>Điều đó chứng tỏ chúng ta hiểu nhau khá rõ đó nha.</p>
<p>Chúc em một ngày 8/3 thật vui vẻ, luôn xinh đẹp và hạnh phúc.</p>
<p>Anh thương em ❤️</p>
`;

}

}else{

document.getElementById("message").innerText="Sai rồi nha, thử lại đi 😜";

}

}

loadQuestion();

</script>

</body>
</html>
