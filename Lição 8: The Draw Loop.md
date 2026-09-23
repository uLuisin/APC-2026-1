# Avaliação

```javascript

//1) Add the draw loop block to the bottom of this program.
//2) Move any blocks that need to be inside the draw loop.

var salt = createSprite(200,200);
salt.setAnimation("salt");
salt.rotation = 180;
background("skyblue");
drawSprites();

function draw() {
  background("skyblue");
  salt.x = randomNumber(195,205);
  salt.y = randomNumber(195,205);
  drawSprites();
}

```

# Sem dificuldades para esta lição.

# Desafio

```javascript

var fundo = createSprite(200,200,400,400);
var cobra_mar = createSprite(100,330,50,50);
background("lightblue");
cobra_mar.setAnimation("eel_1");
fundo.setAnimation("desert_1");
cobra_mar.scale = 0.5;
cobra_mar.rotation = 330;

fill("white");
textSize(20);
stroke("black");
strokeWeight(3);

function draw(){
  
  cobra_mar.rotation = randomNumber(320,340);
  drawSprites();
  text("Eu quero cume!!!!",200,280);
}

```
