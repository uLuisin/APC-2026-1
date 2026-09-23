# Avaliação

```javascript

// create sprites
var giraffe = createSprite(50, 50);
giraffe.setAnimation("giraffe");
giraffe.velocityX = 3;
var hippo = createSprite(50, 150);
hippo.setAnimation("hippo");
hippo.velocityX = 3;
var rabbit = createSprite(50, 250);
rabbit.setAnimation("rabbit");
rabbit.velocityX = 3;
var snake = createSprite(50, 350);
snake.setAnimation("snake");
snake.velocityX = 3;
var parrot = createSprite(350, 50);
parrot.setAnimation("parrot");
parrot.velocityX = -3;
var elephant = createSprite(350, 150);
elephant.setAnimation("elephant");
elephant.velocityX = -3;
var monkey = createSprite(350, 250);
monkey.setAnimation("monkey");
monkey.velocityX = -3;
var pig = createSprite(350, 350);
pig.setAnimation("pig");
pig.velocityX = -3;


function draw() {
  giraffe.bounce(parrot);
  elephant.collide(hippo);
  monkey.displace(rabbit);
  snake.bounceOff(pig);
  background("lightblue");
  drawSprites();
}

```

# Desafio

```javascript

// GAME SETUP
// create player, target, and obstacles
var player = createSprite(200, 100);
player.setAnimation("fly_bot");
player.scale = 0.8;


var coin = createSprite(330,365);
coin.setAnimation("coin");
//coin.scale = 0.3;

var rock1 = createSprite(-30,100);
rock1.setAnimation("rock");
rock1.velocityX = 5;

var rock2 = createSprite(300,-30);
rock2.setAnimation("rock");
rock2.velocityY = 5;




function draw() {
  background("lightblue");
  //player.y = randomNumber(97,103);
  // FALLING
  player.velocityY = 8;
  
  // LOOPING
  
  if (rock1.x > 430) {
    rock1.x = -30;
    rock1.y = randomNumber(50,350);
  }
  
  if (rock2.y > 430) {
    rock2.y = -30;
    rock2.x = randomNumber(50,350);
  }
  
  
  // PLAYER CONTROLS
  // change the y velocity when the user clicks "up"
  if (keyDown("up")) {
    player.velocityY = -10;
  }
  
  // decrease the x velocity when user clicks "left"
    if (keyWentDown("left")) {
    player.velocityX = player.velocityX - 1.5;
  }
  // increase the y velocity when the user clicks "right"
    if (keyWentDown("right")) {
    player.velocityX = player.velocityX + 1.5;
  }
  // SPRITE INTERACTIONS
  // reset the coin when the player touches it
  if (player.isTouching(coin)) {
    coin.x = randomNumber(50,350);
    coin.y = randomNumber(50,350);
  }
  
  // make the obstacles push the player
  if ((rock1.isTouching(player))||(rock2.isTouching(player))) {
    rock1.displace(player);
    rock2.displace(player);
  }
  
  
  // DRAW SPRITES
  drawSprites();
  
  // GAME OVER
  if (player.x < -50 || player.x > 450 || player.y < -50 || player.y > 450) {
    background("black");
    textSize(50);
    fill("green");
    text("Game Over!", 50, 200);
  }
  
}

```

# Um dos desafios foi o entendimento e confusão das propriedades dos sprites
