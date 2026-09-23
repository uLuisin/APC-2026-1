# Avaliação

```javascript

var backdrop = createSprite(200,200);
backdrop.setAnimation("rainbow");
var flyer = createSprite(200,200);
flyer.setAnimation("wing_bot");

function draw() {
  //move left when the left arrow is pressed
  if (keyDown("left")) {
    flyer.x = flyer.x - 3;
  }
  
  //move right when the right arrow is pressed
  if (keyDown("right")) {
    flyer.x = flyer.x + 3;
  }
  
  //move up when the up arrow is pressed
  if (keyDown("up")) {
    flyer.y = flyer.y - 3;
  }
  //move down when the down arrow is pressed
  if (keyDown("down")) {
    flyer.y = flyer.y + 3;
  }
  drawSprites();
}

```

# Desafio

```javascript

var bug = createSprite(200, 200);
bug.setAnimation("fly");

function draw() {
  background("white");

  if (keyDown("up")) {
    bug.rotation = 90; 
    bug.mirrorX(1); // Reseta o espelhamento para a rotação funcionar perfeitamente
    bug.y = bug.y - 5;
  }

  if (keyDown("down")) {
    bug.rotation = 270;
    bug.mirrorX(1); // Reseta o espelhamento 
    bug.y = bug.y + 5;
  }

  if (keyDown("left")) {
    bug.rotation = 0; // Tira a rotação
    bug.mirrorX(1);   // 1 é a orientação original da arte (virado para esquerda)
    bug.x = bug.x - 5;
  }

  if (keyDown("right")) {
    bug.rotation = 0; // Tira a rotação
    bug.mirrorX(-1);  // -1 inverte horizontalmente (virando para a direita)
    bug.x = bug.x + 5;
  }

  drawSprites();
}

```

# A dificuldade do desafio foi fazer o sprite mudar em sentido para a direita, mas sem ficar de cabeça para baixo. O 'rotation' não me permitia uma configuração fácil, eu acabei demorando bastante nesse desafio
