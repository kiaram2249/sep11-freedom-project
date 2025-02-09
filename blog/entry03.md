# Entry 3
##### 2/3/2025

#### Content

The last time that I did my blog was before winter break started. I wrote about the progress that I have been making, while learning about **P5play**. I wrote about the different tools that I learnt from tutorials on **YouTube**, and websites such as [P5play](https://p5play.org/). However, I really need to start on looking at the bigger picture. My partner's (**Caron** & **Robert**) and I need to start discussing about the bigger picture of our game, because we didn't reach our goal that we set last time. This time we really need to act on our goal. We need to start tinkering together because we all have different tools. So, we need to do test trails before starting to build our game, or a plan on who will do what once the days come in where we have to code our game.

Before I begin this is one of my thinkerings that I did. I honestly think this one was my best thinkering yet, because it can be use to be the players avatar. I was able to make this by code by using **P5play** **animation**. By using **animation** I was able to make the farmer look like they were walking. In order for the farmer to look like they were walking, I needed to grab different frames of poses. It's like doing a stop motion, in where you need different poses/positions in order to create the whole motion. After I found the different frames I needed to use **loadAnimation**. **loadAni/loadAnimation** is a function that has three different modes: _sequence, list, and sprite sheet_. I needed to use **loadAnimation** in order to make the farmer start moving, once it was working I than needed to set the farmers orientation. I needed to use an **if statement** as well the **mouse** function. This was important because it will make the farmer direction turn left or right, when the user moved their mouse. The end result was a good outcome since everything was working. Next time I need to see if I can make vegtables/fruits fall randomly since that will be use for one of our mini game. 


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

#### Engineering Design Process

I am in step 2 because I still have to do research about my tool, ``P5play``, I need to find more sources or even videos that I can use so that I can be able to tinker/learn my tool. I should also consider step 3, brainstorm, because my partners and I need to have a heads up in what we want to brainstorm about. We need to brainstorm about the outlook for our game, the factors, the way in how the players will play the game, and can we make in active, etc. However, I think now it is a good time to start considering step 3 because my partners and I can slowly start planning out what we want to put/design our game. We need to do this because we each are learning different tools, so it's important that we talk things out. We need to talk about how we can all use our tool for the Freedom Project. We need to know how we want the backgrounds, the characters, the fruits and vegtables, etc to look like. Even the design of how we want the intro of the game to look like as well. We need to start looking at the bigger picture and we need to start build our game. It's like we're trying to finish the whole longest puzzle piece. If we don't come togther and start brainstorming, we will all be lost when the time comes. 

#### Skills

##### Collaboration

I will be learning the skill **collaboration** because I have to start working with my partners in order to make the game. I need to learn this skill because we all need to be working together, it can't be just one person doing all the work. That would be unfair to my parnters and I. That's why I really want to focus or even to remind myself that **collaboration** is key in order for us to make the Garden Game. As I really need to step on my game with this skill because I haven't been checking on my partners if they have been tinkering, or if they have any ideas for the game. 

#### Communication

**Communication** is very important for us because we all need to be at the same steps/the same part so that no one will be behind or ahead. Also, **communication** is important because if we wanted to work on the project at home during the weekends/holidays, we need to stay in touch with each other. That's why when we were in our first week talking about the Freedom Project I made a group chat in Discord because we all have discord and we all use it as well. We can use that when we are at home or outside of school. But when we can in school, we can all use **Slack** to communicate. Even though we have different periods SEP class, slack will be a way to send updates in what we did, any questions that we have, and plan out our next steps. However, I realized that my partners and I ain't communicating as much about the project. We ain't checking up on each other, which isn't a good thing because we need to know if one is having any kind of trouble, if one is slacking off, or about what we can do about the project. So, today I will go to discord and check up on them and see what progress that they made. 

#### Leadership

Having **leadership** is an important skill to have because I need to support my team members in any way that that I can because this project is a team effort and I don't want no one left behind. We need to make these steps together as a whole in order to make our product by the end of the school year. However, I don't want to be the one taking all over the **leadership**, my partners and I should be all leaders, we should all be equal with each other, and help each other out. We are all leaders to make this game. 

#### Organization

I realize that I need to be **organize** when working on the Freedom Project because I need to organize time with my tinkering, but I also need to organize time for my partners. I need to organize time for them since we are working together on this game. I want to make time for them because I want to discuss some ideas to them, and I want to start giving out roles. I want to give out roles because I took inspiration with another group. With that group they are working together, but they already asigned roles in what each person should make for their game. They are slowing building the bigger picture. So, I want to gives roles between my partners and I so that we can slowly build the bigger picture of our project. 

#### Goals

I want my partners and I to start tinkering together and to start making a mini verson of our main game. Maybe we can start by making one of the mini games that we need for our main game. Or we can start making the backgrounds, and the designs that we want to use for the game. If not, I want to at least see the progress that we all made. Hopefully tommorrow I can see the tinkering that they made so far and give ideas to them. 

#### Professionalism

I'm conveying my learning by using all the things that I have learnt from the past and today [``Computer Science 9th, SEP10, & SEP11``] by learning, from **Tiny.cc/fccwd**, from **Html** + **CSS**, from **JavaScript**, and from my friends/peers as well. I have learnt many different kinds of coding and format, and how to use them as well. I am using all of my learning, and coding skills in order to make this third blog. I have used some of the html, as well I used some of the markdown. For instance, I used this * to make my words in bold, and I used _ in order to make some words in italic.
