# Entry 4
##### March/10/2025

### Content

We're getting closer in where we have to start building/making our **Freedom Project**. Everyone is making there plan and assigning role for there parthers, and making sure that everyone is doing there part for the project. So, right now my parther's (**Robert** & **Caron**) are slowly starting to build/make our **Freedom Project** game. We already did our plan so far, but I don't think we made a really good plan, because if you look at the plan it's kinda over the place. The plan just looks like we have ideas but we don't know what to do first with those ideas. However, over time we are slowly starting to realize what we want to be inputted to the game and what we don't want. This is a good thing becuase now we can start building/making our **Freedom Project** with confidence. 

So, my parther's and I are now working on the **MVP** slowly but surely. The bad thing is that I haven't check up on them to see what progress they made so far, but I guess I'll just do that when I come back to school once the weekend is over. But, something that I have been working on is to make the background move. It doesn't sound super crazy but by having a background that moves, it creates an illusion that when the character moves, so that background setting. In simple terms it just looks like that character is move from one place to the next, and it makes there journey to get there more longer. This is something that I have been working on for the **Freedom Project**, I also have been going around asking my other peers for advise/opinions. Currently one of my peers from **period 4 SEP** they are helping me or teaching me how I can use **Kaboom**. I know this isn't my tinkering tool, but it is one of my partners tools. So, with this information that I am learning from my peer, I can just go to my parther (**Caron**) and tell her these amazing tips/tricks.

```JS

let farmSetting;
let settingX = 0;

function preload() {
  farmSetting = loadImage("setting.jpg");

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













