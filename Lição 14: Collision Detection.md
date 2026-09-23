# Avaliação

```javascript

// create the sprites
var horse = createSprite(200, 150);
horse.setAnimation("horse");
var rainbow = createSprite(400, 370);
rainbow.setAnimation("rainbow");
rainbow.velocityX = -5;
rainbow.velocityY = -5;
rainbow.rotateToDirection = true;

function draw() {
  // draw the background
  background("skyblue");

  // change the horse to a unicorn when the rainbow touches it
  if (rainbow.isTouching(horse)) {
    horse.setAnimation("unicorn");
  }
  
  drawSprites();
}

```

# Desafio

```javascript

//GAME SETUP
// Create the sprites
// set velocity for the obstacle and the target
var cenary = createSprite(200,200,400,400);

var star = createSprite(200,-15,30,30);
star.setAnimation("star1_1");
star.scale = 0.10;
star.velocityY = 3;
star.setCollider("circle",0,0,10);

var player = createSprite(200,350,100,100);
player.setAnimation("spacebattle_06_1");
player.scale = 0.2;
player.rotation = -90;

var alien = createSprite(200, 200,100,100);
alien.setAnimation("retroaliens_10_1");
alien.scale = 0.12;
alien.velocityY = 4;

var shot = createSprite(200,350,20,20);
shot.y = player.y;
shot.x = player.x;
shot.setAnimation("shot_1");
shot.velocityY = -9;

var explosion = createSprite(-100,-100,100,100);
explosion.setAnimation("burst13_1");
explosion.scale = 0.20;

//create the variables
var score = 0;
var health = 10;

function draw() {
  // BACKGROUND
  // draw the ground and other background
  cenary.setAnimation("cave_1");
  alien.setAnimation("retroaliens_10_1");

  // SPRITE INTERACTIONS
  // if the player touches the obstacle
  // the health goes down, and the obstacle turns
  if (shot.isTouching(alien)) {
    //World.frameRate = 1;
    alien.setAnimation("burst13_1");
    //World.frameRate = 30;
    alien.y = -15;
    alien.x = randomNumber(20,380);
    shot.y = player.y;
    shot.x = player.x;
    
  }
  
  if (player.isTouching(alien)) {
    alien.setAnimation("burst13_1");
    health = health - 1;
    alien.y = -15;
    alien.x = randomNumber(20,380);
    alien.setAnimation("retroaliens_10_1");
  }

  // if the frog touches the fly
  // the score goes up, the fly resets
  if (player.isTouching(star)) {
    score = score + 1;
    star.y = -20;
    star.x = randomNumber(20,380);
  }

  // JUMPING
  // if the player has reached the ground
  // stop moving down

  // if the player presses the up arrow
  // start moving up
  if (keyDown("right")) {
    player.x = player.x + 10;
  }
  if (keyDown("left")) {
    player.x = player.x - 10;
  }
  if (keyDown("up")) {
    player.y = player.y - 7;
  }
  if (keyDown("down")) {
    player.y = player.y + 7;
  }

  // if the player reaches the top of the jump
  // start moving down

  // LOOPING
  // if the obstacle has gone off the left hand side of the screen, 
  // move it to the right hand side of the screen
  if (shot.y < 50) {
    shot.y = player.y;
    shot.x = player.x;
  }
  
  if (alien.y > 400) {
    alien.y = -15;
    alien.x = randomNumber(20,380);
    health = health - 1;
  }
  
  if (star.y > 400) {
    star.y = -20;
    star.x = randomNumber(20,380);
  }

  // if the target has gone off the left hand side of the screen,
  // move it to the right hand side of the screen

  // DRAW SPRITES
  drawSprites();
  
  // SCOREBOARD
  // add scoreboard and health meter
  fill("white");
  textSize(20);
  text("Health:", 280, 30);
  text (health, 350, 30);
  text("Score:", 20, 30);
  text(score, 90, 30);
  
  if (score > 9) {
    background("black");
    fill("green");
    textSize(50);
    text("You Won!" , 40, 200);   
  }
  // GAME OVER
  // if health runs out
  // show Game over
  if (health < 1) {
    background("black");
    fill("green");
    textSize(50);
    text("Game Over!" , 40, 200);
  }
}

```

# Desafios: tempo e configurar as colisões dos objetos além de definir ordens para os sprites
