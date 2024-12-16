# Entry 2
##### 12/9/2024

### Content 

So far I have been able to learn new things about my tool [P5play](https://p5play.org/). I have been tinkering for one month probably a half by now, and I have learnt so much about my tool. For inctance, the first time that I was tinkering I wanted to have a sense about the **Sprites**, because in order for me to make shape for example I would have to need a **sprite**. This was a huge thing for me to learn about because when I was going in depth of **P5play**, I realized that **sprites** is important and that **sprites** is needed for everything. I say this because the next thing that I learnt was **sprite.collider** , **sprite.moveTo(mouseX, mouseY)**, and adding text inside of the shape or sprite. It's important that I need how to do this because it can help with my groups **Freedom Project**. Also, lastly I was able to learn how to set a **backgroud** by using **sprites** and how to set a little character by using a **sprite** as well. However, all of these coding and the different **sprites** that I was able to learn by tinkering will come in handy because while I was learning about these factors/technique, I was ready thinking about how I can incorporate these into the game. 


#### Sprite.collider

The **collider** is useful because it makes the sprite stay in one place. So, even if another sprite/shape hits the sprite that has a collider. That shape will not more at all no matter how many times you hit it. It's useful because it can help other sprites/shape not to wonder around off the previw. This can be helpful for the **Freedom Project** because if I wanted something to stay in one place I can just use the `.collider`. I like this because when using [P5.js Web Editor](https://editor.p5js.org/kiaram2249/sketches/VtfUHQrwN) the shapes kind of more when you press start to see your code. So, using `.collider` can help with not making the shapes or any **sprite** not move. 

```JS
function setup() {
  new Canvas(400, 400);

  let wall = new Sprite(width, height/2, 20, height); 
    wall.fill = 'pink';
    wall.collider = 'static';
    
  let top = new Sprite()
  top.y = 400;
  top.fill = 'pink';
  top.w = 350;
  top.collider = 'static';
}
```

#### Sprite.moveTo(mouseX, mouseY)

The **mouse** can make my **Freedom Project** game active. The `sprite.moveTo` can make the game active because when you move your mouse and click on the screen the object will move to that direction. This can be good for the game because the user can more objects to that direction. I don't think I will use this **sprite** because when I was tinkering this, it was only able to move one sprite object. I wonder if it can happen to more than one sprite. But, if that were to happen then all of the sprite would move at the same time probably making it messy. 

```JS
function mousePressed(){
  ball.moveTo(mouseX, mouseY, 8);
}
```

#### Text in a Sprite

The **text** allows you to add text inside a **sprite**. This can be useful to label things off for the game, and this can help the player to know what is what. 

```JS
 for (let i=0; i < 15; i++) {
    let block = new Sprite(width/2 + random(-5, 5), height/2 +random(-5, 5), 40, 40);
  block.diameter = 50;
  block.textSize = 12;
  block.text = "15 ball";
}
```

With all of these together I was able to make something. I was able to make two **sprites** that wouldn't move, **sprites** that have text inside saying _15 balls_, and a **sprite** that can move everytime the user moves there mouse and clicks on the screen. 
   * The [p5.js Code](https://editor.p5js.org/)

**The Full Code:**

```JS
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

#### Background + Character

I wanted to make a mini garden look out, and I could make it because I can use images that I downloaded as backgrounds. By doing this I can make this into a little look out or maybe a mini story mode introduction for our game. So, I learnt how to download background images and how to put them onto **P5play**. However, I did not just putted a background I also inclubed a little farmer as the users character to play around with. I also used what I learnt from before. I inclubed the **mouse sprite** because I want to the little farmer to move around. 

```JS
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
```

But there's still things that I want to improve on because when you put the mouse onto the screen or on top of the character and move it around, the character will go off screen even though if the user has stop moving around the little farmer. However, this is the full code of what I made with my tinkering. 
   * The [p5.js Code](https://editor.p5js.org/kiaram2249/sketches/JnEDLMSff)

**The Full COde:**

```JS
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

### Engineering Design Process

I am in step 2 because I still have to do research about my tool, `P5play`, I need to find more sources or even videos that I can use so that I can be able to tinker/learn my tool. I should also consider step 3, brainstorm, because my partners and I need to have a heads up in what we want to brainstorm about. We need to brainstorm about the outlook for our game, the factors, the way in how the players will play the game, and can we make in active, etc. However, I think now it is a good time to start considering step 3 because my partners and I can slowly start planning out what we want to put/design our game. We need to do this because we each are learning different tools, so it's important that we talk things out. We need to talk about how we can all use our tool for the **Freedom Project**. We need to know how we want the backgrounds, the characters, the fruits and vegtables, etc to look like. Even the design of how we want the intro of the game to look like as well. 

### Skills

#### Communication

**Communication** is very important for us because we all need to be at the same steps/the same part so that no one will be behind or ahead. Also, **communication** is important because if we wanted to work on the project at home during the weekends/holidays, we need to stay in touch with each other. That's why when we were in our first week talking about the Freedom Project I made a group chat in Discord because we all have discord and we all use it as well. We can use that when we are at home or outside of school. But when we can in school, we can all use Slack to communicate. Even we be on slack on different periods/times, this will be a way for all of to send updates in what we did, any questions that we have, and plan out our next steps. However, I realized that my partners and I ain't communicating as much about the project. We ain't checking up on each other, which isn't a good thing because we need to know if one is having any kind of trouble, if one is slacking off, or about what we can do about the project. So, next time or when I see them again, I will try and commicate with them and check up on them to see where we are all on with the project of the tinkering. Plus this can be a good way for us to really start brainstorming and talking about it to each other. 

### Goal

A goal that I want to have for the winter break, is for my partners and I to start creating the intro of the game. If not I want for us to tinker togther. I want us to tinker together because at some point with the Freedom Project, we need to combine all of the codes, and all the things that we learnt. So, I want to do a test run in how we can all add **Kaboom**, **Phaser** and **P5play** together.

### Professionalism

I'm conveying my learning by using all the things that I have learnt from the past and today [`Computer Science 9th, SEP10, & SEP11`] by learning, from **Tiny.cc/fccwd**, from **Html + CSS**, from **JavaScript**, from **Markdown**, and from my friends/peers as well. I have learnt many different kinds of coding and format, and how to use them as well. I am using all of my learning, and coding skills in order to make this second blog. I have used some of the html, as well I used some of the markdown. For instance, I used this * to make my words in bold, and I used _ in order to make some words in italic.
