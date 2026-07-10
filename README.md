<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Simple Car Game</title>
<style>
body{
margin:0;
display:flex;
justify-content:center;
background:#444;
overflow:hidden;
}
#game{
width:300px;
height:600px;
background:#666;
position:relative;
overflow:hidden;
border:4px solid white;
}
#road{
position:absolute;
width:10px;
height:600px;
left:145px;
background:repeating-linear-gradient(
white 0 30px,
transparent 30px 60px
);
animation:moveRoad 0.3s linear infinite;
}
@keyframes moveRoad{
from{transform:translateY(0);}
to{transform:translateY(60px);}
}
#car{
width:50px;
height:90px;
background:red;
position:absolute;
bottom:20px;
left:125px;
border-radius:8px;
}
</style>
</head>
<body>

<div id="game">
<div id="road"></div>
<div id="car"></div>
</div>

<script>
const car=document.getElementById("car");
let x=125;

document.addEventListener("keydown",(e)=>{
if(e.key==="ArrowLeft" && x>20){
x-=20;
}
if(e.key==="ArrowRight" && x<230){
x+=20;
}
car.style.left=x+"px";
});
</script>

</body>
</html>
