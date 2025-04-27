# Entry 5
##### April/24/2025

### Content

We're getting closer in where we have to start to build/make our **Freedom Project**. Everyone is probably done with there **MVP**, and is probably almost done with the **Freedom Project**. However, now it is time to start making edits and work on our **Beyond MVP**. So, during the _Spring Break_ my partner's (Caron & Robert) and I started to work on the **MVP**, so right now Robert and I worked on our mini game for the project. The mini game that we made is our **MVP**, and our **Beyond MVP** will be the games menu. So, during this or either next weekend my parthers and I will be working on making the menu, as well combining our codes. We need to combine our codes because we all are working on different tools, and apparently it's kinda hard to combine **Kaboom** with **P5play**. This is will a challenge once my partner and I come across that path.  

* The **MVP** was a challenge to make because we needed to make objects fall down, a "basket" that can move and collect the objects, make a scoring, and a game over if the user collected the wrong object. So, much needed to be made and the fact that Robert and I combine that with a different **p5play** code was also hard. We combined it with a code that I made long ago when I was tinkering, the purpose of the code just makes the background move. So, we combined that with the mini game so that it can make the mini game look cool. 

**THE MVP:**

* [The Mini-Game on P5.js](https://editor.p5js.org/kiaram2249/sketches/KsziL-F5m)

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

* This is our final code for the mini game, it works how we wanted it to work. But, there's some changes that need to be done in order for it to be truly done. For instance, right now there's two different color circles, green being the safe ones to collet and organe being the deadly ones to collet. This is to represent the **Fruit** and the **Trash-bag**. So, later on I need to make a **var** that contains these images and replace the color circles with that. I would have done it before, but I didn't knew how to do it, so I asked one of my friends who is also doing **P5play** to help me. She was able to help me and example what I need in order to make what I want happen.
* As well I probably need to change the speed just a bit because the objects are going a little bit slow, and I need to search a basket image if I want to replace the rectangle with that. Other than that everything is good as it is.


### Engineering Design Process

I am no longer in steps 3 (**Brainstorming**) or in step 4 (**Planning**). Right now I am at step 5 (**Creating**) and in step 6 (**Testing**). I'm at step 5 because my partner's and I worked on the **MVP**, and are now slowly making our way to make our **Beyond MVP** for the **Freedom Project**. We are creating our mini game so that it can be perfect, slowly creating our games meun so that it can be added on later. However, while creating/coding we are also testing it as we moved on. Testing the code is important because we need to see if there are any errors. My partner's and I were doing this when we were making the mini game. So, glad that we did that because we came across many errors. Now that I am lokking at the website for [HSTAT SEP](https://hstatsep.github.io/students/), looking at the **EDP** I realize that I'm also at step 7 (**Improving**) and at step 8 (**Communicate**). I'm slowly going to step 7 because my partner's and I are slowly improving our **Freedom Project**, as well we are improving within ourself. We're also on step 8 because we're all working on our communication skills, since we are communicating within/outside of school. 

### Skills

#### Problem decomposition

**Problem decomposition** is one of the skills that I have been learning and need to have because there's so much things that I want to do for the **Freedom Project**, but that would have been so much. So, I needed to break down those ideas into smaller pieces so that I can envison what I want to be feature into the game. So far, I have been doing good with that because during _Spring break_, Robert and I were able to decided what we want to be input inside the game. Some of our old ideas were cut off, and it'll probably not be inclubed into the game. I'm glad that I have been slowly improving with this skill because now I know how to break things down into smaller/simpler tasks. 

#### Time management

**Time management** is an important skill to have, especially when we have a time frame and a plan to follow. When we had to work on the **MVP**, I have to admit that my partner's and I weren't following the plan that we made. For this we had to work on the **MVP** within two days before school started. I would never do this again because within those two days I was over stress. So, my lesson from that is to never do work last minute. 

#### Communication

**Communication** is a skill that I am improving on over the days, because I have been communicating with my partner's outside of school in order to work of the **Freedom Project**. I need to work on communicating with them in school because I sometimes forget to talk to them about what steps that we should work on. However, outside of school I used **Discord** in order to communicate with them and to work on the project with them. 

### Goals

* To fix the **MVP** and to make improvement on it before the due date of the **Freedom Project** fair.
* To start working on the **Beyond MVP** before _May 20_ because I believe the fair is around _May 27_. So, my partner's and I need to start working on the menu.
* Keep up with my **Time Management** and NOT work on things last minute.
* Asking for help if needed instead of struggling on my own.

### Professionalism

I'm conveying my learning by using all the things that I have learnt from the past and today ```[Computer Science 9th, SEP10, & SEP11]``` by learning, from **Tiny.cc/fccwd**, from **Html** + **CSS**, from **JavaScript**, and from my friends/peers as well. I have learnt many different kinds of coding and format, and how to use them as well. I am using all of my learning, and coding skills in order to make this third blog. I have used some of the html, as well I used some of the markdown. For instance, I used this * to make my words in bold, and I used _ in order to make some words in italic.
