# Avaliação: 

```javascript

var grass = createSprite(200,200);
grass.setAnimation("floating_grass");
var alien = createSprite(180,100);
alien.setAnimation("alien");
alien.scale = 1.3;
var robot = createSprite(300,300);
robot.setAnimation("robot");
robot.scale = 0.2;
drawSprites();

fill("black");
textSize(15);
text("What are u looking 4", 200, 20);
text("The SUN!!!", 300, 180);

```
# Sem grandes dificuldades ainda, exceto por achar um escalas e coordenadas ideias para os sprites.

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
