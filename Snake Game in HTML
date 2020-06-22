<html>
 <head> 
  <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no"> 
  <style>
#canvas{
  //background-size: cover;
 background:url("images/road.jpg")
}
input{
  width: 90px;
  height: 90px;
  font-size: 20px;
  border-radius: 100%;
  background: none;
  box-shadow: 5px 5px 10px black;
  outline:none;
}
.right{
  float: left;
  margin-top: 40px;
}
.left{
  float: right;
  width: 120px;
}
</style> 
 </head> 
 <body> 
  <canvas width="300" height="300" id="canvas"> 
  </canvas> 
  <div class="left"> 
   <input type="button" value="up" onclick="du()"> 
   <br> 
   <input type="button" value="down" onclick="dd()"> 
  </div> 
  <div class="right"> 
   <input type="button" value="left" onclick="dl()"> 
   <input type="button" value="right" onclick="dr()"> 
  </div> 
  <script>
canvas = document.getElementById("canvas")
context = canvas.getContext("2d")


//var ss = new Audio();
//ss.src = "file:///storage/emulated/0/Dcoder/sounds/bullet.wav"



var snakeW =10
var snakeH = 10
var dir ="right"
function drawSnake(x,y){
  
  context.fillRect(x*snakeW,y*snakeH,snakeW,snakeH)
  //context.fillStyle="black"
  //context.strokeRect(x*snakeW,y*snakeH,snakeW,snakeH)

}

//drawSnake(0,0)
var len = 4
snake = []
for(var i = len-1;i>=0;i--){
  snake.push({x:i,y:0})
}

function dd(){
  dir="down"
}
function du(){
  dir="up"
}
function dr(){
  dir="right"
}
function dl(){
  dir="left"
}
          //food
var food = {
  x:Math.round(Math.random()*(canvas.width/snakeW-3) +1),   
  y:Math.round(Math.random()*(canvas.height/snakeH-3) +1)  

}
function foodd(x,y){
  context.fillStyle="yellow"
  context.fillRect(x*snakeW,y*snakeH,10,10)

}

function draw(){
  
  context.clearRect(0,0,canvas.width,canvas.height)
  for(var i = 0;i < snake.length;i++){
    var X = snake[i].x
    var Y = snake[i].y
    drawSnake(X,Y)
  }
  foodd(food.x,food.y)
  //snake head
  var snakeX = snake[0].x
  var snakeY = snake[0].y
                //snak
  //context.drawImage(fg,snakeX*snakeW,snakeY*snakeH,10,10)



  if(snakeX<0 || snakeY < 0 || snakeX> canvas.width/snakeW || snakeY > canvas.height/snakeH){
    location.reload()
  }
  
  if(dir==="right"){
    snakeX++
  }
  else if(dir==="left"){
    snakeX--
  }
  else if(dir==="down"){
    snakeY++
  }
  else if(dir==="up"){
    snakeY--
  }
  
  if(snakeX == food.x && snakeY == food.y){
    food = {
      x:Math.round(Math.random()*(canvas.width/snakeW-3) +1),   
      y:Math.round(Math.random()*(canvas.height/snakeH-3) +1)
    }
    //ss.play()
    var newHead = {x:snakeX,y:snakeY}
    
  }
  else{
    snake.pop()
    var newHead = {x:snakeX,y:snakeY}
    }
  snake.unshift(newHead)
}
setInterval(draw,150)

</script> 
 </body>
</html>
