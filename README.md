
<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>MAJ WINGO STATS</title>
<style>
body{margin:0;background:#10152b;color:white;font-family:Arial;text-align:center}
header{padding:22px;background:#18264b;color:#55c8ff;font-size:25px;font-weight:bold}
.box{background:#1c2745;margin:18px;padding:18px;border-radius:14px}
button{padding:12px;margin:5px;border:0;border-radius:8px;font-weight:bold}
.red{background:#ff4268;color:white}
.green{background:#16c784;color:white}
.violet{background:#a66cff;color:white}
.big{background:#398cff;color:white}
.small{background:#ff9e43;color:white}
#history{padding:0;list-style:none}
#history li{padding:10px;border-bottom:1px solid #39445e}
</style>
</head>
<body>
<header>💙 MAJ WINGO STATS 💗</header>
<div class="box">
<h3>রঙ নির্বাচন</h3>
<button class="red" onclick="add('Red')">RED</button>
<button class="green" onclick="add('Green')">GREEN</button>
<button class="violet" onclick="add('Violet')">VIOLET</button>
<h3>সাইজ নির্বাচন</h3>
<button class="big" onclick="add('Big')">BIG</button>
<button class="small" onclick="add('Small')">SMALL</button>
</div>
<div class="box">
<h3>পরিসংখ্যান</h3>
<p id="total">মোট এন্ট্রি: 0</p>
<p id="redCount">Red: 0</p>
<p id="greenCount">Green: 0</p>
<p id="violetCount">Violet: 0</p>
<p id="bigCount">Big: 0</p>
<p id="smallCount">Small: 0</p>
</div>
<div class="box">
<h3>ইতিহাস</h3>
<ul id="history"></ul>
<button onclick="clearAll()">ইতিহাস মুছুন</button>
</div>
<script>
let results=[];
function add(value){
results.push(value);
update();
}
function update(){
document.getElementById('total').textContent='মোট এন্ট্রি: '+results.length;
['Red','Green','Violet','Big','Small'].forEach(v=>{
let id=v.toLowerCase()+'Count';
document.getElementById(id).textContent=v+': '+results.filter(x=>x===v).length;
});
document.getElementById('history').innerHTML=results.slice().reverse().map((v,i)=>'<li>'+(results.length-i)+'. '+v+'</li>').join('');
}
function clearAll(){
results=[];
update();
}
</script>
</body>
</html>
