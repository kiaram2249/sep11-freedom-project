# Tool Learning Log

## Tool: **P5play**

## Project: **Gardern Game**

---

### October/18/2024

### Sources

* **Intro to p5play- 1.1 Sprites:** [David Bouchard](https://www.youtube.com/watch?v=ZQ23FHfgA0A) _13:25_
* [P5play](https://p5play.org/)
* [p5.js Web Editor](https://editor.p5js.org/kiaram2249/sketches/VtfUHQrwN)

---

### What are P5play, P5, & p5js?

* **p5js** libraries are code packeages that we can import the arugment in what **P5** already provides for us;
* **P5** is a code library, set of objects and **Functions** written in JavaScript that we can use in order to build our own sketches and programs;
* **P5play** uses a library called _Box 2D_ which is a **physics simulator**;

After we include the **p5js** , we go to our **index.html** so that we can add the two script tags. That's basically how you bring in code libraries into our sketches. We just inclube additional scripts at the beginning. [P5play Intro](https://editor.p5js.org/kiaram2249/sketches/VtfUHQrwN)

```js
<script src="https://p5play.org/v3/planck.min.js"></script>
<script src="https://p5play.org/v3/p5play.js"></script>
```

* ```<script src="https://p5play.org/v3/planck.min.js"></script>``` is a script that includes a libary called **plank** and that is the **physics engine**;
* ```<script src="https://p5play.org/v3/p5play.js"></script>``` is a a libary called **P5** and that's the libary that I will be learning;

---

### Canvas

* **Canvas** is a new Constructor that we can use in order to build a **canvas** and when using **canvas** it comes with few secial abilities;
* When making a canvas we can use a **Function** and write ```new Canvas();```
   * We can use numbers to set up the **width** and **height**;
   * We can also use **window width** and **window height**;

```js
function setup() {
  new Canvas(400, 400);
  new Canvas(windowWidth, windowHeight);
}

function draw() {
  background('pink');
}
```

* Using **canvas** down the road will be very useful because **canvas** haves nice features. For instance, we can use **canvas** so that we can be able to do some pixel art games;
* We can also use **canvas** to do NE tricks, such as specifying an aspect ratio for the **canvas** instead of having specific dimensions; 

```js
function setup() {
  new Canvas("1:1");
  new Canvas("2:1");
}

function draw() {
  background('pink');
}
```

---

### Introduction of Sprites

* **Sprite** is an element in the simulated world of **P5play**;
* It's something that exists on the screen;
* Something that's going to move around;
* Something that's going to have **Physics simulation** applied to it;
   * (_All the game objects in P5play are going to be Sprite objects_);
* Since **Sprite** are objects we can put them into **variables**;

**Local**
(_The **let ball** variable is a **local** variable meaning that we can only be able to access it inside setup_); 

```js
function setup() {
  new Canvas(400, 400);
  let ball = new Sprite();
}

function draw() {
  background('pink');
}
```

**Global**
(_We declare it as a **global** variable but putting **let ball;** outside and ontop of the **function**, and then we changed the inside of the **function** by deleting the **let**. Making it now call **ball = new Sprite()**_);

```js
let ball;
function setup() {
  new Canvas(400, 400);
  ball = new Sprite();
}

function draw() {
  background('pink');
}
```

* On default the _new Sprite_ **P5play** makes a few assumptions; 
   * Making the object center of the screen (_default coordinate is in the center_);
   * Making a box as the default with a specific dimension;
   * Giving the **Sprite** a random color everytime we hit run/play;

--- 

### Changing the Sprite's attibutes

* **Sprites** are **JavaScript** objects, so they have attibutes that we can change;
* **Sprites** have **Functions** that we can use on them;

For instance, we can set up a diameter attribute to a **Sprite** changing the shape type of it. As well we can chnage the vaule in how big we want the shape to be. We can make it bigger or smaller.

```js
let ball;

function setup() {
  new Canvas(400, 400);
  ball = new Sprite();
  ball.diameter = 50;
}

function draw() {
  background('pink');
}
```

* **Sprites** have positions, so they have a **(x, y)** attribute. So we can change the coordinates and the location of the shape of the **sprite**;
   * ```ball.x = 200;```
   * ```ball.y = 300;```
* We don't just have to use numbers in order to set up the **(x,y)** coordinates. We can use **width** and **height** to set up the **(x,y)**;
   * ```ball.x = width/2 - 200;```
   * ```ball.y = height/2;```

(_In P5play.org it shows other different attribute that we can change of our **Sprite** into_);

![image](https://github.com/user-attachments/assets/ffb291ad-9c89-400f-9ae5-c86b5df6364a)

---

### Motion (velocity)

* **Sprites** have speed in **P5play** and that's going to be called the **Velocity**;
   * The **velocity** has a **x** and a **y**
   * **Speed X** and **Speed Y**

```js
let ball;

function setup() {
  new Canvas(400, 400);
  ball = new Sprite();
  ball.diameter = 50;
  ball.fill = 'yellow';
  ball.velocity.x = 1;
}

function draw() {
  background('pink');
}
```

---

### October/21/2024

### Sources

* [P5play](https://p5play.org/)
* [p5.js Web Editor](https://editor.p5js.org/kiaram2249/sketches/VtfUHQrwN)
* [My Tinkering](https://editor.p5js.org/kiaram2249/sketches/SHS_kRs9k)

---

```js
let ball;

function setup() {
  new Canvas(400, 400);
  ball = new Sprite();
  ball.diameter = 60;
  ball.fill = 'pink';
  ball.x = width/2-200;
  ball.y = height/2;
  ball.textSize = 10;
  ball.text = "Hit the balls";
  
  for (let i=0; i < 15; i++) {
    let block = new Sprite(width/2 + random(-5, 5), height/2 +random(-5, 5), 40, 40);
  block.diameter = 50;
  block.textSize = 12;
  block.text = "15 ball";
}
  
let wall = new Sprite(width, height/2, 20, height); 
  wall.fill = 'pink';
  wall.collider = 'static';
  
let top = new Sprite()
top.y = 400;
top.fill = 'pink';
top.w = 350;
top.collider = 'static';
  
}

function draw() {
  background('black');
}

function mousePressed(){
  ball.moveTo(mouseX, mouseY, 8);
}
```

* Today I just wanted to learn the other variables that **P5play** has. Today, I went and learnt about **sprite.collider** , **sprite.moveTo(mouseX, mouseY)**, and adding text inside of the shape or sprite. I reused the same code from last tinkering and just added on. I used **P5js Web editor** to tinker and make this code.
   * Next time I want to use a different mouse tool, in where you can just move your mouse without any clicking invalue and your sprite/shape can still move around the preview. 
* I realize that **mouse** can make my freedom project game active. Since when you click on the preview the pink ball moves in any direction. If follows in where you click your mouse at. This is a goo way to make the game active for users since they will be clicking vegtables, fruits, and etc from the garden.
* The **collider** is also useful because it makes the sprite stay in one place. So, even if another sprite/shape hits the sprite that has a collider. That shape will not more at all no matter how many times you hit it. It's useful because it can help other sprites/shape not to wonder around off the previw. Also, if I wanted something to stay on the preview, I can just use the collider.
* The **text** is good because I can add dialogue and label sprites/shapes if I wanted too. This can come in handy when I want to do those two things. It can help out the game because I can label the fruits, vegtables, the garden, the bugs, and etc. If I can I can try to see if I can use **sprite.text** without putting text inside the shape/sprite. Maybe I can add text onto the canvas instead.

---

### November/4/2024

### Sources 

* [P5play](https://p5play.org/)
* [p5.js Web Editor](https://editor.p5js.org/kiaram2249/sketches/VtfUHQrwN)
* [My Tinkering](https://editor.p5js.org/kiaram2249/sketches/T9TrKPQgg)

---

* Today in class I wanted to try and make a design of our game by using **P5play**. I wanted to try and see if I can make a garden by using the **sprites** that are given in **P5play**. So, far I made some type of garden that looks like a farm from Minecraft. I realize **P5play** can be use for pixel arts, maybe this can be good design for like a mini garden look out. What I mean by that, maybe this design be used as a little out look in the corner when the user is in a different room of the game. It's almost like the little map from Minecraft that users see in the a corner.
    * Right now I realize I can't look through everything in the **P5play** website because I need to make a account. So, when I go back to school I can try and ask about it to my teacher. However, I can probably ask one of my peers who is also doing **P5play**.
* Next time, I will try and see if I can add some type of animation too the design and many add new shapes once I make an account with **P5play**. 

```js
function setup() {
  new Canvas(400, 400);
  
  dirt0 = new Sprite();
  
  dirt0.fill = 'brown';
  dirt0.width = 30;
  dirt0.height = 1000;
  dirt0.x = 385;
  dirt0.collider = 'static';
  
  
  dirt1 = new Sprite();
  
  dirt1.height = 1000;
  dirt1.width = 30;
  dirt1.fill = 'brown';
  dirt1.x = 328;
  dirt1.collider = 'static';
  
  water = new Sprite();
  
  water.height = 1000;
  water.width = 30;
  water.fill = 'teal';
  water.x = 358;
  water.collider = 'static';
  
  cates = new Sprite();
  cates.w = 100;
  cates.x = 50;
  cates.y = 25;
  cates.fill = 'olive';
  cates.text = "supplies"
  cates.textSize = 20;
}

function draw() {
  background('green');
}
```

--- 

### November/18/2024

### Sources 

* [P5play](https://p5play.org/)
* [p5.js Web Editor](https://editor.p5js.org/kiaram2249/sketches/VtfUHQrwN)
* [David Bouchard](https://www.youtube.com/watch?v=boyuLp3T9NI)
* [My Tinkering](https://editor.p5js.org/kiaram2249/sketches/JnEDLMSff)

---

* My last tinkering I wanted to make a background by using the different **sprites** that are given in **P5play**. I wanted to make a mini garden look out. But, with todays tinkering I realize that I could make that, I could make but make it even better. I could make it better because I can use images that I downloaded as backgrounds.
* I can make this into a little look out or maybe a mini story mode introduction for our game. I don't what I can inclube this into our game, but these are my little ideas of it.
* Today in tinker I learnt how to download background images and use them onto **P5play**. However, not just a background I also inclubed a little farmer as the users character to play around with.
    * Somethings that I want to improve on is to make a **scroll**. Meaning when the user is moving the character and it's going of the the screen, the image will continue on with the character, making it look like the character is walking around in long distances.
    * Another thing that I want to improve on is when the user moves the character. I want to fix the mouse movement because when I was seeing if the mouse movemnent was working, I realize that the character will still move once you take your mouse off the screen. I want to fix that and make sure that the character only moves when you have the mouse on the screen. I don't want the character to keeps on moving when the the user is moving the mouse away from the screen. The character should stop once the mouse is not on it.
    * Something that I'm thinking about doing is making something like this while making it active. What I mean by that is while the user is moving the character they can collet rewards on the way. I don't think **P5play** can do that, but maybe with **Kaboom** I could do something like that. I have to ask my partners for help with that, since they are learning **Kaboom**.
 
```js
let farmer;
let farmerImg;

let gardenBackgroundImg;

function preload() {
  gardenBackgroundImg = loadImage("garden.jpg");
  
  farmerImg = loadImage("file.png");
}

function setup() {
  new Canvas(1600, 1440, "pixelated");
  
  farmer = new Sprite();
  farmer.image = farmerImg;
  
  mouse.visible = false;
}

function draw() {
 image(gardenBackgroundImg, 0, 0);
 background(gardenBackgroundImg);
 farmer.moveTo(mouse, 3);
}
```

---

### December/2/2024

### Sources

* [P5play](https://p5play.org/)
* [p5.js Web Editor](https://editor.p5js.org/kiaram2249/sketches/VtfUHQrwN)

---

* I know that I'm not thinking by not using **p5.js**, but I really wanted to write down my ideas that I could do for my groups **Freedom Project**. Today I to build an idea of making something that the user can interact in the furture of my next tinkering. I want to make a  mini pratice game before they play the actual game. What I mean by this, is that I want to make a mini tutorial, where the user will read the rules and have a mini practice round. The game will be pixal looking in a way, but it will be something. So, I would do this while my partners will make the actual game.
   * I want the game to be, where the farmer needs to collect all the fruits and vegtables that are falling from the ground. The player would have to try and collect all the falling fruits/vegtables. The more they have the better it is for them to sell their products.
   * This is just a mini tutorial, so the user will play this mini tutorial before starting the actual game. The tutorial will have direction in how to play, and when the user is done reading they will then begin the tutorial.
   * This tutorial will have 3 different rounds. I say different because each round will have a different difficulty levels. 

**The idea for the Tutorial:**

![image](https://github.com/user-attachments/assets/5097ec0d-c95b-41e5-b20e-8255f497d1bb)

* I can use the learning from tinkering November 18 because with that tinkering I was able to make the farmer move, everytime the user put their mouse on the screen.
   * I would just need to know how to make the farmer look left and right, as well I would need to know how to make all the fruits/vegtables fall off down the screen.
   * I would also need the help from one of my partners, to see if **Kaboom** or **Phaser** can help me make this tutorial active for the user.
   * I would probably need `if else` statments, maybe some `for loops` or `while loops` so that the tutorial can keep on going.
* So, in my next tinker I will try and see if I can make this tutorial game idea into a reality.

---

### December/30/2024

### Sources 

* [P5play](https://p5play.org/)
* [p5.js Web Editor](https://editor.p5js.org/kiaram2249/sketches/VtfUHQrwN)
* [My Tinkering](https://editor.p5js.org/kiaram2249/sketches/PuV7uMNjj)

---

* `loadAnimation` is provided by **P5play** and it's important because `loadAnimation` has three different modes: **sequence**, **list**, and **sprite sheet**. The animation helps create the image to look like that they are going in a motion.
* This was perfect for me because I remember trying to make something the same on my other tinkering before. However, I wasn't able to make the player move the other direction when the user moved their mouse. But with todays tinkering I was able to learn how to make the player face different directions.
* I used an `if` statement, so when the user moved the mouse to the left or the right, the player will face that direction.
**Example Code**
```JS
if(pmouseX > mouseX) player.scale.x = -1; //will make the player face to the left
if(pmouseX < mouseX) player.scale.x = 1; //will make the player face to the right
```

* With that code I'm able to make the player face left or right. But the part that I am more proud of is making the player move in motions. The animation was really wonderful because it made the player look like that it was walking. Something that I want to fix or improve is when the user stops playing around with the player, the player will stop moving. I say this because even when I'm not moving the player with the mouse, the player is still going in motion in the starting position.
   * I don't want the player to be in motion when it's not being used around by the user. So, for next tinkering I will find a way for that issue that I want to fix. However, maybe I need to create another motion where it can look like the player is not moving. Or 


```JS
let player;
let farmerPlayerAni;
// let backgroundImg;

function preload() {
   // let seq = imageSequence("assets/farmerPlayer-", 4); 
   // console.log(seq);
  
  // backgroundImg = loadImage("garden.jpg");
  
  farmerPlayerAni = loadAnimation(['assets/farmerPlayer-0.png', 'assets/farmerPlayer-1.png', 'assets/farmerPlayer-2.png', 'assets/farmerPlayer-3.png']);
}

function setup() {
  new Canvas(windowWidth, windowHeight);
  
  player = new Sprite();
  player.addAni(farmerPlayerAni);
  player.w = 40;
  player.h = 75;
  // player.debug = true;
}

function draw() {
  background('black');
  // image(backgroundImg, 0, 0); 
  // background(backgroundImg);
  mouse.visible = false;
  player.moveTowards(mouse,1);
  
// set the player orientation
  if(pmouseX > mouseX) player.scale.x = -1;
  if(pmouseX < mouseX) player.scale.x = 1;
}

// function imageSequence(prefix, numberOfFrames, ext=".png") {
//   let sequence = [];
//   for (let i = 0; i < numberOfFrames; i++) {
//     sequence[i] = prefix + i + ext;
//   }
//   return sequence;
// }
```













<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
