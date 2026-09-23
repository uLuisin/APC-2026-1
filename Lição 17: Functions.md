# Avaliação

```javascript

//var fundo = createSprite(200,200,400,400);
//fundo.setAnimation("rainbow_1");

var coin = createSprite(200,10);
coin.setAnimation("coin_gold_1");
setCoin();

var bunny = createSprite(200,350);
bunny.setAnimation("bunny1_ready_1");
bunny.setCollider("circle",0,0,50);

var score = 0;

function draw() {
  background("white");
  if (score>2) {
    winningBackground();
  }
  
  if(keyDown("left")){
    bunny.x = bunny.x - 2;
  }
  
  if(keyDown("right")){
    bunny.x = bunny.x + 2;
  }
  
  if(bunny.isTouching(coin)) {
    score = score + 1;
    setCoin();
  }
  
  if(coin.y > 400){
    setCoin();
  }
  
  textSize(20);
  text("Score: " + score, 10, 10, 100, 100);
  drawSprites();
}

function setCoin(){
  coin.velocityY = 5;
  coin.x = randomNumber(50,350);
  coin.y = 0;
  
}

function winningBackground() {
  background("lightblue");
  fill("black");
  strokeWeight(3);
  rect(80,200,1,250);
  rect(100,185,1,250);
  rect(110,240,1,250);
  rect(120,210,1,250);
  
  fill("red");
  ellipse(80,200,40,55);
  fill("green");
  ellipse(100,185,40,55);
  fill("blue");
  ellipse(110,240,40,55);
  fill("yellow");
  ellipse(120,210,40,55);
  fill("black");
  
}

```

# Desafio

```javascript

var planetaEx = createSprite(-100,300,50,50);
//planetaEx.setAnimation("emoji_16_1");
planetaEx.scale = 0.1;
planetaEx.velocityX = 4;

var planetaIn = createSprite(-100,300,50,50);
//planetaIn.setAnimation("emoji_16_1");
planetaIn.scale = 0.1;
planetaIn.velocityX = 4;

var sol = createSprite(-100,100);
sol.scale = 0.1;
sol.velocityX = 4;

function draw() {
  if(World.mouseY > 200){
    drawScene1();
  } else {
    drawScene2();
  }
  //drawSprites(); 
}


function drawScene1() {
  var raio1 = randomNumber(1,4);
  var raio2 = randomNumber(1,4);
  var raio3 = randomNumber(1,4);
  background("black");
  fill("white");
  stroke("white");
  strokeWeight(2);
  ellipse(randomNumber(30,370),randomNumber(30,370),raio1,raio1);
  ellipse(randomNumber(30,370),randomNumber(30,370),raio2,raio2);
  ellipse(randomNumber(30,370),randomNumber(30,370),raio3,raio3);
  
  noStroke();
  fill("gray");
  ellipse(200,0,180,180);
  
  fill("lightgreen");

  ellipse(planetaEx.x,planetaEx.y,90,90);
  
  fill("green");

  ellipse(planetaIn.x,planetaIn.y,70,70);
  
  if (planetaEx.x > 500) {
    planetaEx.x = -100;
    planetaIn.x = -100;
  }
  
  //drawSprites();
}



function drawScene2(){
  background("lightblue");
  
  fill("green");
  noStroke();
  ellipse(200,400,400,170);
  
  fill("lightyellow");
  ellipse(sol.x,sol.y,100,100);
  
  if (sol.x > 500) {
    sol.x = -100;
  }
  
}

```

# Alguns bugs em relação ao sprites, alguns simplesmente não eram criado, outros não tinham movimento e alguns tinha "imagens passadas", tudo foi ajustado depois de algumas releituras do códgio.
