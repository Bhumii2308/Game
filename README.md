<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Traffic Light</title>

<style>
body{
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:#222;
}

.traffic-light{
    background:#111;
    padding:20px;
    border-radius:20px;
    width:120px;
}

.light{
    width:80px;
    height:80px;
    margin:15px auto;
    border-radius:50%;
    background:#444;
    transition:.5s;
}

.red.active{
    background:red;
    box-shadow:0 0 30px red;
}

.yellow.active{
    background:yellow;
    box-shadow:0 0 30px yellow;
}

.green.active{
    background:lime;
    box-shadow:0 0 30px lime;
}
</style>
</head>

<body>

<div class="traffic-light">
    <div class="light red"></div>
    <div class="light yellow"></div>
    <div class="light green"></div>
</div>

<script>
const red=document.querySelector(".red");
const yellow=document.querySelector(".yellow");
const green=document.querySelector(".green");

function off(){
    red.classList.remove("active");
    yellow.classList.remove("active");
    green.classList.remove("active");
}

let state=0;

setInterval(()=>{
    off();

    if(state===0){
        red.classList.add("active");
    }
    else if(state===1){
        yellow.classList.add("active");
    }
    else{
        green.classList.add("active");
    }

    state=(state+1)%3;
},2000);
</script>

</body>
</html>
