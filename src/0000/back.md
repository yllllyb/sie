<!DOCTYPE html>
<html><head><meta charset="utf-8"></head><body onkeypress="sw()">
<canvas id="cav" onmousedown="re()"></canvas></body></html>
<script>
window.onload = function(){re();}
var w = window.innerWidth;
var h = window.innerHeight;
var n = w*h/1000;
var c = document.getElementById("cav");
var on = true;
var color = "rgb(11,15,30)";
c.height = h;
c.width = w;
var ctx = c.getContext("2d");
function re(){
ctx.fillStyle=color;
ctx.fillRect(0,0,w,h);
ctx.fillStyle="#FFFFFF";
ctx.strokeStyle="#FFFFFF";
for(var i = 0; i<n; i++){
var x = Math.random()*(w-20)+10;
var y = Math.random()*(h-20)+10;
var r = Math.random();
ctx.beginPath();
ctx.arc(x,y,r,0,2*Math.PI,true);
ctx.fill();
ctx.closePath();
//ctx.fillRect(x,y,r,r);
}}
function sw(){
if(on==true){
	on=false;
	color="rgb(113,164,250)";
}else{
	on=true;
	color="rgb(11,15,30)";
}
	re();
}
</script>