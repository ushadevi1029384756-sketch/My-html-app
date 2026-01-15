<!DOCTYPE html>
<html>
<head>
<title>Click the Button 1,000,000 Times</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
body{
    margin:0;
    font-family: Arial;
    background:#111;
    color:white;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    text-align:center;
}
button{
    padding:20px 40px;
    font-size:22px;
    border:none;
    border-radius:10px;
    background:#00ff88;
    cursor:pointer;
}
button:active{
    transform:scale(0.95);
}
.box{
    width:90%;
    max-width:400px;
}
.code{
    margin-top:15px;
    font-size:18px;
    color:#00ff88;
}
</style>
</head>

<body>
<div class="box">
    <h2>Click the Button<br>1,000,000 Times</h2>
    <p>Reward: ₹30 Redeem Code</p>
    <h3 id="count">0 / 1,000,000</h3>
    <button onclick="clickBtn()">CLICK</button>
    <div class="code" id="reward"></div>
</div>

<script>
let clicks = localStorage.getItem("clicks") 
    ? parseInt(localStorage.getItem("clicks")) 
    : 0;

document.getElementById("count").innerText =
clicks + " / 1,000,000";

function clickBtn(){
    if(clicks < 1000000){
        clicks++;
        localStorage.setItem("clicks", clicks);
        document.getElementById("count").innerText =
        clicks + " / 1,000,000";
    }

    if(clicks === 1000000){
        document.getElementById("reward").innerText =
        "🎉 Reward Unlocked!\nCODE: DEMO-30-RUPEES";
    }
}
</script>
</body>
</html>
