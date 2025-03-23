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
   * I don't want the player to be in motion when it's not being used around by the user. So, for next tinkering I will find a way for that issue that I want to fix. However, maybe I need to create another motion where it can look like the player is not moving. Or maybe I need a `if else` statement in order to make the player move and stop moving when the user isn't moving the player with the mouse.
* When I was able to make the the player face left and right, I wanted to set a garden background but I wasn't able to set that background because there was an error. I try to fix the error but it just wouldn't work, I even try to reuse a code that I did when I was setting a background before. But that didn't work as well, so I just left the background to the color black.
* Something that I learnt is that I need different motions images in order to create that animations feeling to the game. As well I can use `arrays` in order to make the process. 

**The vision that I had:**

![image](https://github.com/user-attachments/assets/e50b031a-3874-40ee-aa08-6a4f0e10ec0a)

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

---

### January/6/2025

### Sources

* [P5play](https://p5play.org/)
* [p5.js Web Editor](https://editor.p5js.org/kiaram2249/sketches/VtfUHQrwN)

---

* Here is another planning idea as for my thinkering. I want to make another planning idea because there's so much things that my partner and I need to talk about. We need to start planning in what we want the game to look like and what things we should add onto the game. I realize my partner and I haven't been talking about these things as much, and we need to because in our group we all have different tools that we are learning. So, we need to know who should make what by using there tool.
* However, an idea that I have is that we can make a mini story mode before the player starts playing the game. Also, maybe having a new intro title as the main introduction for the game. I can probably make that since I seen videos on **YouTube** about making titles by using **P5play**.
   * For the title I want to make the title with a new background, maybe a image of a garden as the background. For the title it should be in a lovely fonts and the color should give a nature vide. The whole tilte should feel welcoming, calming, and feel like that you are a farmer getting ready to take care of your garden.
* As for the game in the garden, one of my partners can make it. They can make the game since their tools in **Phaser** and **Kaboom**. However, for the game the idea that I was having is that the player should catch the falling vegtables/fruits that are falling down in randmon spots.
   * What the player needs to do is catch the vegtables/fruits and avoid the rotten vegtables/fruits.
* Another idea for the game is that the player will need to take care of there crops from the pests. So, how I want to make it is that the player is over looking their garden and if they see a pest crawling around the plants, then all they have to do it press the pest so that they can get off. But they have to work quick because the level will increase, making the speed of the pest move faster.
* Finally the last thing that the players can do in our game is to sell the produces that they have grown, they can sell as much as they want and with the money that they have in the game, they can increase/improve the garden tools that they have. 

**Title Game (possible idea)**

![image](https://github.com/user-attachments/assets/478d3345-7afe-4736-8cd8-8eaeddcf6c54)

**The different pests**

![image](https://github.com/user-attachments/assets/0f8a3796-2a49-474a-836f-0ce424531e12)

---

### March/2/2025

### Sources

* [P5play](https://p5play.org/)
* [YouTube](https://www.youtube.com/)
* [p5.js Web Editor](https://editor.p5js.org/)

---

```JS
let player;
let farmerPlayerAni;

let farmSetting;
let settingX = 0;

function preload() {
  farmSetting = loadImage("setting.jpg");

  farmerPlayerAni = loadAnimation(['assets/farmerPlayer-0.png', 'assets/farmerPlayer-1.png', 'assets/farmerPlayer-2.png', 'assets/farmerPlayer-3.png']);
}

function setup() {
  new Canvas(384, 230, "pixelated");
  
  player = new Sprite();
  player.addAni(farmerPlayerAni);
  player.w = 40;
  player.h = 75;
}

function draw() {
  background('lightgrey');
  mouse.visible = false;
  player.moveTowards(mouse,1);
  
// background setting
  image(farmSetting, int(settingX), 0);
  settingX -= 0.8;

// we double the background setting
  image(farmSetting, int(settingX) + width, 0);

// snap back the background setting to zero
  if(settingX < -width) settingX = 0;
  
// orientation setting
  if(pmouseX > mouseX) player.scale.x = -1;
  if(pmouseX < mouseX) player.scale.x = 1;
}
```

* Since the user player will be wondering area, I wanted to create something that can be useful for my groups **Freedom Project**. So, what I did is basically the same thing that I did from my last learning log. It's the same but the only thing that is different is the background and the outlook. The background moves along with the player, creating an illusion that the player is moving from place to place.
   * This is helpful because I can set up different setting backgrounds, making it look like the player is moving to different places.
   * Plus in the video that I found, I realized that I can put **layers** for the background, creating an even more cool illusion. By having layers I can probably make the made setting as the players farm home and in the back of the main setting I can layer it with animals or people. Creating a warm environment for the user would is gonna play our game.
   * Also, by having layers I can also create an illusion for when the user is gonna sell their protects. Making it look like it's a busy sale place.
* Even though my today's learning log wasn't much, I still think this a good start in somewhere, because I can use the **animation** of the little farmer character and the moving background for many things.
   * Maybe I can use this to make the intro of the game. Honestly I have so many ideas that I don't even know where to start nor how to execute them. 
* Next time for my learning log I can try to make something, by collaberating with my teamates. Maybe we can use what I learn in order to make the intro and the little story mode.
* **Int** is useful because it blends the images together, helping to not show the line that's between the double images. 

---

### March/9/2025

### Sources

* [P5play](https://p5play.org/)
* [p5.js Web Editor](https://editor.p5js.org/kiaram2249/sketches/VtfUHQrwN)

---

* Here's another once a month where I talk about my progress that I did so far and the things that I want to do with my partners for the near future for our **Freedom Project**. So, far in my last learning log I was able to make the background move. What I mean by this was that I was able to make the background to continue on as the user moves the player/character. But it isn't really moving, I just created two backgrounds with the same image and messed around with the **width** by using **if statements**. So, it creates an illusion that the background is moving as the player/character is walking straight ahead.
  * This was important for me to learn/make because this can help with our game. It can make an illusion that the player/character is going from place to place. This can also create an illusion to one of our mini games as well if possible.
* However, so far my partners and I have been communicating much more than before, because before we didn't knew where everyone was at and we were never really talking about our plans/ideas for the **Freedom Project**. But now that has changed because this week we were finally talking about what we truly wanted in our game. Plus we were talking about the two **mini games** that we wanted to add to the **Freedom Project**. This is a good start because the **MVP** is due **April 21**, and my partner and I needs to finalize in what we want to add into our game.
  * All I know is that we need those two mini games, because that's how the user will collect there **fruits/vegtables** and also to protect there **fruits/vegtables** from pests.
  * We also need to build the intro/welcoming of the game with instructions and a mini bio of what the game is about.
  * Must have mini story mode in the very beginning to show and create a setting. I want to ask my partners if we can add this because I want to user to know there player/character and the life sytle that they live in. It's like you're getting to know who your going to play as in the game.
* But right now at this moment one of my peers is helping me, they are helping me in how to use certain elements in order to make something. But, they are showing me this with **Kaboom**, **Kaboom** isn't my tool but it's good for me to learn these kinds of things because I can help my partner **Caron** since she is using that tool. I want to be able to help my partner, in anyway I can because I don't want any of my partners to feel stress while doing the **Freedom Project**.
  * Right now my peer is trying to help with my mini games, giving me tips and hints in how to do it even though it isn't my tool that I am using. But, he did said that I could do it since it is almost the same thing. So, with my next learning log I will try to make it.
  * Plus, in our class we are learning **P5js**. This is useful because my tool is **P5play** and it can help my partner gain an understanding of my tool, maybe they can help me out when we all code together.
 
**Different Settings:**

![image](https://github.com/user-attachments/assets/1078b9ed-4260-4941-82c7-cf7fcf05738f)

* I know there wasn't any new ideas that were talked about, this was more like a reflect for me and to see what I need to do next in order to do my up coming learning log and to see what I need to do as a partner so that we can make our **Freedom Project**.

---


### March/17/2025

### Sources

* [P5play](https://p5play.org/)
* [p5.js Web Editor](https://editor.p5js.org/kiaram2249/sketches/VtfUHQrwN)

---

```JS
let basket; // The basket object
let fallingItems = []; // Items that are falling
let score = 0; // The score for catching items
let itemSpeed = 3; // Speed of falling items
let itemImages = []; // Array to store item images

// Load item images
function preload() {
  itemImages.push(loadImage('apples.png')); // Load apple image
}

// Set up the canvas and initial basket
function setup() {
  createCanvas(500, 400); // Set canvas size
  basket = { x: width / 2, y: height - 50, width: 100, height: 50 }; // Basket at bottom center
  frameRate(30); // Control the game speed
}

// Main drawing loop
function draw() {
  background(200); // Light gray background

  // Move basket with the mouse
  basket.x = mouseX;

  // Drop items every 30 frames
  if (frameCount % 30 === 0) {
    createItem(); // Create a new falling item
  }

  // Update each falling item
  for (let i = fallingItems.length - 1; i >= 0; i--) {
    let item = fallingItems[i];
    item.y += itemSpeed; // Move item down

    // Check if the item hits the basket
    if (
      item.y + item.height > basket.y &&
      item.y < basket.y + basket.height &&
      item.x + item.width > basket.x - basket.width / 2 &&
      item.x < basket.x + basket.width / 2
    ) {
      score++; // Increase score
      fallingItems.splice(i, 1); // Remove the item
    }

    // Remove items that fall off screen
    if (item.y > height) {
      fallingItems.splice(i, 1);
    }
  }

  // Display the score
  textSize(32);
  fill(0);
  textAlign(RIGHT);
  text("Caught: " + score, width - 20, 40);

  // Draw the basket
  rect(basket.x - basket.width / 2, basket.y, basket.width, basket.height);

  // Draw all falling items
  for (let item of fallingItems) {
    image(item.image, item.x, item.y);
  }
}

// Create a new falling item
function createItem() {
  let randomImage = random(itemImages); // Pick a random item image
  let newItem = {
    x: random(50, width - 50), // Random horizontal position
    y: 0, // Start from the top
    width: 50, // Width of the item
    height: 50, // Height of the item
    image: randomImage // Item image
  };
  fallingItems.push(newItem); // Add the item to the falling items list
}
```


<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
