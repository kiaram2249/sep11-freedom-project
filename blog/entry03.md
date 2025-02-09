# Entry 3
##### 2/3/2025

#### Content

The last time that I did my blog was before winter break started. I wrote about the progress that I have been making, while learning about **P5play**. I wrote about the different tools that I learnt from tutorials on **YouTube**, and websites such as [P5play] (https://p5play.org/). However, I really need to start on looking at the bigger picture. My partner's (**Caron** & **Robert**) and I need to start discussing about the bigger picture of our game, because we didn't reach our goal that we set last time. This time we really need to act on our goal. We need to start tinkering together because we all have different tools. So, we need to do test trails before starting to build our game, or a plan on who will do what once the days come in where we have to code our game.

Before I begin this is one of my thinkerings that I did. I honestly think this one was my best thinkering yet, because it can be use to be the players avatar. I was able to make this by code by using **P5play** **animation**. By using **animation** I was able to make the farmer look like they were walking. In order for the farmer to look like they were walking, I needed to grab different frames of poses. It's like doing a stop motion, in where you need different poses/positions in order to create the whole motion. After I found the different frames I needed to use **loadAnimation**. **loadAni/loadAnimation** is a function that has three different modes: _sequence, list, and sprite sheet_. I needed to use **loadAnimation** in order to make the farmer start moving, once it was working I than needed to set the farmers orientation. I needed to use an **if statement** as well the **mouse** function. This was important because it will make the farmer direction turn left or right, when the user moved there mouse. The end result was a good outcome since everything was working. Next time I need to see if I can make vegtables/fruits fall randomly since that will be use for one of our mini game. 


**My Tinkering:**

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




















Text

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
