# Entry 5
##### April/24/2025

### Content

We're getting closer in where we have to start to build/make our **Freedom Project**. Everyone is probably done with there **MVP**, and is probably almost done with the **Freedom Project**. However, now it is time to start making edits and work on our **Beyond MVP**. So, during the _Spring Break_ my partner's (Caron & Robert) and I started to work on the **MVP**, so right now Robert and I worked on our mini game for the project. The mini game that we made is our **MVP**, and our **Beyond MVP** will be the games menu. So, during this or either next weekend my parthers and I will be working on making the menu, as well combining our codes. We need to combine our codes because we all are working on different tools, and apparently it's kinda hard to combine **Kaboom** with **P5play**. This is will a challenge once my partner and I come across that path.  

The **MVP** was a challenge to make because we needed to make objects fall down, a "basket" that can move and collect the objects, make a scoring, and a game over if the user collected the wrong object. So, much needed to be made and the fact that Robert and I combine that with a different p5play code was also hard. We combined it with a code that I made long ago when I was tinkering, the purpose of the code just makes the background move. So, we combined that with the mini game so that it can make the mini game look cool. 

**THE MVP:**

```JS

        let setting;
        let settingY = 0; 
        let basket;
        let shapes;
        let score = 0;
        let gameOver = false;

        function preload() {
            setting = loadImage("wood.png");
        }

        function setup() {
            createCanvas(600, 400);
            basket = new Sprite(300, 370, 100, 20, 'static');
            basket.color = 'brown';
            shapes = new Group();
            textSize(20);
        }

        function draw() {
            background(240);
            image(setting, 0, settingY, width, height);
            image(setting, 0, settingY + height, width, height);
            settingY--;
            if (settingY < -height) settingY = 0;

            if (gameOver) {
                fill(255, 0, 0);
                textAlign(CENTER, CENTER);
                textSize(40);
                text("GAME OVER", width / 2, height / 2);
                return;
            }

            basket.x = constrain(mouseX, 50, 550);

            if (frameCount % 30 === 0) {
                let shape = new Sprite(shapes);
                shape.x = random(50, 550);
                shape.y = -20;
                shape.diameter = random(20, 40);
                shape.vel.y = random(2, 5);

                // Randomly assign color and type
                if (random() < 0.3) {
                    shape.color = 'orange';   // deadly
                    shape.isDeadly = true;
                } else {
                    shape.color = 'green';    // safe
                    shape.isDeadly = false;
                }
            }

            for (let shape of shapes) {
                if (shape.overlapping(basket)) {
                    if (shape.isDeadly) {
                        gameOver = true;
                    } else {
                        score++;
                    }
                    shape.remove();
                } else if (shape.y > height + 30) {
                    shape.remove();
                }
            }

            fill(0);
            text("Score: " + score, 10, 20);
        }
```

