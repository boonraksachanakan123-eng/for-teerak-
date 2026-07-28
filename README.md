# for-teerak-
<!DOCTYPE html>

<html lang="th">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>ครบรอบ 2 เดือน 💗</title>

<style>

*{

    box-sizing:border-box;

    font-family:"Arial",sans-serif;

}

body{

    margin:0;

    overflow:hidden;

    background:#ffd6e7;

}

.page{

    width:100vw;

    height:100vh;

    display:none;

    justify-content:center;

    align-items:center;

    flex-direction:column;

    text-align:center;

    position:absolute;

}

.active{

    display:flex;

}

h1{

    color:#ff4f9a;

    font-size:32px;

}

button{

    margin-top:30px;

    padding:15px 50px;

    border:none;

    border-radius:50px;

    background:#ff8fc7;

    color:white;

    font-size:22px;

    cursor:pointer;

    box-shadow:0 5px 15px #ff9dcc;

}

.heart{

    font-size:100px;

    cursor:pointer;

    animation:pulse 1s infinite;

}

@keyframes pulse{

    50%{transform:scale(1.2)}

}

.float{

    position:absolute;

    animation:fly 5s linear infinite;

}

@keyframes fly{

    from{

        transform:translateY(100vh);

        opacity:1;

    }

    to{

        transform:translateY(-10vh);

        opacity:0;

    }

}

#photo{

    width:260px;

    border-radius:20px;

    display:none;

    animation:zoom 2s;

}

@keyframes zoom{

    from{

        transform:scale(.5);

        opacity:0;

    }

    to{

        transform:scale(1);

        opacity:1;

    }

}

.gift{

    font-size:120px;

    cursor:pointer;

}

.spark{

    font-size:40px;

    animation:pop 1s infinite;

}

@keyframes pop{

    50%{transform:scale(1.5)}

}

.message{

    width:85%;

    color:#ff4f9a;

    font-size:20px;

    line-height:1.8;

}

.small{

    margin-top:30px;

    color:#ff6fae;

}

</style>

</head>

<body>

<!-- หน้า 1 -->

<div class="page active" id="page1">

<h1>

💗 สุขสันต์วันครบรอบ 2 เดือนน้าาาอ้วน :> 💗

</h1>

<button onclick="next(2)">

🎀 เริ่มต้น

</button>

</div>

<!-- หน้า 2 -->

<div class="page" id="page2">

<h1>

กดหัวใจ💗

</h1>

<div class="heart" onclick="showPhoto()">

❤️

</div>

<img id="photo" src="love.jpg">

<button id="giftBtn" onclick="next(3)" style="display:none">

🎁 เปิดของขวัญ

</button>

</div>

<!-- หน้า 3 -->

<div class="page" id="page3">

<div class="gift" onclick="openGift()">

🎁

</div>

<div id="text" class="message"></div>

<div class="small">

- จากไอ้ช็อคโกแลตเอง 😋 -

</div>

</div>

<script>

function next(page){

document.querySelectorAll(".page")

.forEach(p=>p.classList.remove("active"));

document.getElementById("page"+page)

.classList.add("active");

}

function hearts(){

let h=document.createElement("div");

h.className="float";

h.innerHTML="💗";

h.style.left=Math.random()*100+"vw";

h.style.fontSize=(20+Math.random()*40)+"px";

document.body.appendChild(h);

setTimeout(()=>{

h.remove();

},5000)

}

setInterval(hearts,300);

function showPhoto(){

let photo=document.getElementById("photo");

photo.style.display="block";

document.querySelector(".heart")



document.getElementById("giftBtn")

.style.display="block";

}

let msg=

`2เดือนละนะอ้วนน

ขอบคุณสำหรับเวลาที่ผ่านมานะอ้วน

เค้ามีความสุขมั่กมากกตั้งแต่มีอ้วน

อ้วนทำให้วันธรรมดาของเค้าเป็นวันที่พิเศษขึ้นมาา

อยู่เป็นความสุขให้เค้าแบบนี้นานๆนะอ้วน

เค้ารักพี่นะคะ

อยากมีพี่อยู่ด้วยกันไปนานนานนเล้ยย

รักอ้วนมากมากกก

จุ๊บมั้วว🩷`;

function openGift(){

document.querySelector(".gift")


let i=0;

let box=document.getElementById("text");

let timer=setInterval(()=>{

box.innerHTML+=msg[i];

i++;

if(i>=msg.length)

clearInterval(timer);

},80);

}

</script>

</body>

</html>