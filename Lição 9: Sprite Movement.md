# Avaliação

```javascript

var orangeFish = createSprite(400, randomNumber(0, 100));
orangeFish.setAnimation("orange_fish");
var blueFish = createSprite(250, randomNumber(0, 200));
blueFish.setAnimation("blue_fish");
var greenFish = createSprite(300, randomNumber(200, 300));
greenFish.setAnimation("green_fish");
var bolha = 400;

function draw() {
  // Draw Background
  background("navy");
  
  // Update Values
  if (keyDown("left")) {
    orangeFish.x = orangeFish.x - 2;
    orangeFish.rotation = randomNumber(-3,2);
    blueFish.x = blueFish.x - 4;
    blueFish.rotation = randomNumber(-5,5);
    greenFish.x = greenFish.x - 1;
    greenFish.rotation = randomNumber(-2,2);
  }
  
  bolha = bolha - 1;
  
  noFill();
  stroke("white");
  strokeWeight(3);
  ellipse(270,bolha+40,10,10);
  ellipse(180,bolha+50,10,10);
  ellipse(130,bolha+10,10,10);
  
  // Draw Animations
  drawSprites();
}

```

# Se eu não me engano o projeto da avaliação foi alterado futuramente, já que devia estar conectado à outras atividades
# por isso ele acabou contemplando certas "features" que ainda não haviam sido aprendidas.

# Desafio

```javascript

var fundo = createSprite(0,0,400,400);
var nave = createSprite(203,327);

nave.setAnimation("ufo_02_1");
fundo.setAnimation("desert_road_1");
nave.scale = 0.02;

fundo.x = 200;
fundo.y = 200;

function draw() {
  fundo.setAnimation("desert_road_1");
  nave.rotation = randomNumber(-10,10);
  nave.scale = nave.scale + 0.02;
  nave.y = nave.y + 0.5;
  drawSprites();
}

```

# Uma nave dirigindo por uma rota em alta velocidade, até bater no espectador
