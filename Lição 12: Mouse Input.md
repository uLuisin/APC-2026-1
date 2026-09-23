# Avaliação

```javascript

var backdrop = createSprite(200,200);
backdrop.setAnimation("sky");
var creature = createSprite(200,250);
creature.setAnimation("creature");
creature.scale = 0.2;
function draw() {
  //shake the sprite when the mouse is pressed
  if (mouseDown()){
    creature.rotation = randomNumber(-5,5);
    drawSprites();
  }
  else {
    //display the text when the mouse is NOT pressed
    fill("black");
    stroke("white");
    strokeWeight(3);
    textSize(40);
    text("Press the mouse to shake the creature.", 20, 50, 360, 100);

  }

}

```


# Desafio

```javascript

var salt = createSprite (200, 200);
var counter = 0;
salt.setAnimation("salt");
salt.rotation = 150;

function draw() {
  background("skyblue");
  
  // If mouseDidMove, rotate the salt shaker randomly to the left or right
  if (mouseDidMove()) {
    counter = counter + 1;
    salt.rotation = randomNumber(135,165);
    console.log(counter);
    if (counter >= 100) {
      salt.rotation = 0;
    }
  }
  
  drawSprites();
}

```

# Sem grandes dificuldades nessa lição
