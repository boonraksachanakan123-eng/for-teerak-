<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>ครบรอบ 2 เดือน 💗</title>

<style>

*{
    box-sizing:border-box;
    font-family: "Arial", sans-serif;
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
}

.active{
    display:flex;
}


/* หน้าแรก */

#home{
    background:linear-gradient(#ffd6e7,#ffc2dc);
}

h1{
    color:#ff4f91;
    font-size:32px;
}

button{
    border:none;
    padding:18px 45px;
    border-radius:40px;
    background:#ff8fba;
    color:white;
    font-size:22px;
    cursor:pointer;
    margin-top:30px;
    box-shadow:0 5px 15px #d98aa8;
}


/* หัวใจลอย */

.heart{
    position:absolute;
    color:#ff6fa8;
    animation:float 5s linear infinite;
}

@keyframes float{

0%{
transform:translateY(100vh);
opacity:1;
}

100%{
transform:translateY(-20vh);
opacity:0;
}

}


/* หน้าที่2 */

#heartPage{
    background:#ffe0ec;
}

.bigHeart{
    font-size:120px;
    cursor:pointer;
    animation:pulse 1s infinite;
}

@keyframes pulse{
50%{
transform:scale(1.2);
}
}


#photo{
    width:280px;
    border-radius:25px;
    margin-top:20px;
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


/* กล่องของขวัญ */

.box{
    font-size:120px;
    cursor:pointer;
}


.message{
    width:85%;
    color:#ff4f91;
    font-size:20px;
    line-height:1.8;
}


.small{
    position:absolute;
    bottom:30px;
    color:#ff639c;
}

</style>

</head>


<body>


<!-- หน้าแรก -->

<div class="page active" id="home">

<h1>
💗 สุขสันต์วันครบรอบ 2 เดือนน้าาาอ้วน :> 💗
</h1>

<button onclick="nextPage('heartPage')">
🎀 เริ่มต้น
</button>

</div>



<!-- หน้าที่2 -->

<div class="page" id="heartPage">

<div class="bigHeart" onclick="showPhoto()">
❤️
</div>

<h2>
กดหัวใจ💗
</h2>


<img id="photo" src="photo.jpg">


<button id="giftBtn" style="display:none"
onclick="nextPage('giftPage')">

🎁 เปิดของขวัญ

</button>


</div>




<!-- หน้าที่3 -->

<div class="page" id="giftPage">


<div class="box" onclick="openGift()">
🎁
</div>


<div class="message" id="message"></div>


<div class="small">
- จากไอ้ช็อคโกแลตเอง 😋 -
</div>


</div>





<script>


function nextPage(id){

document.querySelectorAll(".page")
.forEach(p=>p.classList.remove("active"));

document.getElementById(id)
.classList.add("active");

}



function showPhoto(){

let photo=document.getElementById("photo");

photo.style.display="block";

document.getElementById("giftBtn")
.style.display="block";

createHearts();

}




function openGift(){

document.querySelector(".box").innerHTML="💗";

let text=
`2เดือนละนะอ้วนน

ขอบคุณสำหรับเวลาที่ผ่านมานะอ้วน

เค้ามีความสุขมั่กมากกตั้งแต่มีอ้วน

อ้วนทำให้วันธรรมดาของเค้าเป็นวันที่พิเศษขึ้นมาา

อยู่เป็นความสุขให้เค้าแบบนี้นานๆนะอ้วน

เค้ารักพี่นะคะอยากมีพี่อยู่ด้วยกันไปนานนานนเล้ยย

รักอ้วนมากมากกก จุ๊บมั้วว🩷`;


let i=0;

let box=document.getElementById("message");


let timer=setInterval(()=>{

box.innerHTML += text[i];

i++;

if(i>=text.length){

clearInterval(timer);

createHearts();

}

},80);


}




function createHearts(){

for(let i=0;i<40;i++){

let h=document.createElement("div");

h.className="heart";

h.innerHTML="💗";

h.style.left=Math.random()*100+"%";

h.style.animationDuration=
(3+Math.random()*4)+"s";


document.body.appendChild(h);


setTimeout(()=>{

h.remove();

},6000);


}

}


</script>


</body>
</html>
