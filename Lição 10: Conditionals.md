# Avaliação

```javascript

var backdrop = createSprite(200,200);
backdrop.setAnimation("sci_fi");
var dinosaur = createSprite(200, 350);
dinosaur.scale = 0.2;
dinosaur.setAnimation("tyrannosaurus");

function draw() {
  //move the dinosaur up
  dinosaur.y = dinosaur.y - 5;

  //if it gets to the sky, turn it into a pterodactyl
  if (dinosaur.y <= 100) {
    dinosaur.setAnimation("pterodactyl");
  }

  //draw everything
  drawSprites();
}

```

# Sem grandes desafios nessa lição

# Desafio

```javascript

var balloon = createSprite(200, 200);
var pop = createSprite(200,200);
balloon.setAnimation("balloon");
balloon.scale = 0.1;

pop.setAnimation("pop");
pop.visible = false;


function draw() {
  // Draw Background
  background("white");
  
  // Update Values
  balloon.scale = balloon.scale + 0.001;
  console.log(balloon.scale);
  if (balloon.scale >= 0.665) {
    balloon.visible = false;
    pop.visible = true;
  }
  if (balloon.height >= 400) {
    //balloon.visible = false;
    //pop.visible = true;
  }

  // Draw Animations
  drawSprites();
}

```
