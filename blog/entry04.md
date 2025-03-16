# Entry 4
##### March/10/2025

### Content

We're getting closer in where we have to start building/making our **Freedom Project**. Everyone is making there plan and assigning role for there parthers, and making sure that everyone is doing there part for the project. So, right now my parther's (**Robert** & **Caron**) are slowly starting to build/make our **Freedom Project** game. We already did our plan so far, but I don't think we made a really good plan, because if you look at the plan it's kinda over the place. The plan just looks like we have ideas but we don't know what to do first with those ideas. However, over time we are slowly starting to realize what we want to be inputted to the game and what we don't want. This is a good thing becuase now we can start building/making our **Freedom Project** with confidence. 

So, my parther's and I are now working on the **MVP** slowly but surely. The bad thing is that I haven't check up on them to see what progress they made so far, but I guess I'll just do that when I come back to school once the weekend is over. But, something that I have been working on is to make the background move. It doesn't sound super crazy but by having a background that moves, it creates an illusion that when the character moves, so that background setting. In simple terms it just looks like that character is move from one place to the next, and it makes there journey to get there more longer. This is something that I have been working on for the **Freedom Project**, I also have been going around asking my other peers for advise/opinions. Currently one of my peers from **period 4 SEP** they are helping me or teaching me how I can use [Kaboom](https://kaboomjs.com/). I know this isn't my tinkering tool, but it is one of my partners tools. So, with this information that I am learning from my peer, I can just go to my parther (**Caron**) and tell her these amazing tips/tricks.

```JS

let farmSetting;
let settingX = 0;

function preload() {
  farmSetting = loadImage("setting.jpg");

}

function draw() {
  background('lightgrey');
  
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

### Engineering Design Process

Before I was at step 3 (**Brainstorming**) and step 4 (**Planning**), but now I'm at step 5 (**Creating**) and onto step 6 (**Testing**). I'm at step 5 because my partner's and I are starting to make our **Freedom Project**. We are slowly building/making our way into making this game. We are creating different ways in have to do that, creating different settings, different characters, the different items that we need for the game. This also why we are in step 6 as well, because while creating we are testing to see if it works or not. We are not just creating but also testing as the days go by. Testing to make sure that everything is working in there right place, testing to see if we need more or less of something, just testing as we go in general so that we have a well built product. Now that I am looking at the website for [HSTAT SEP](https://hstatsep.github.io/students/), looking at the **EDP** I realize that I'm also at step 7 (**Improving**) becuase we are improving, not just the game but improving on ourself as well. It's a good thing to make improvements because that just shows that you grew as a better person with an better understanding on something. I would like to say that I think I have improve over time, because I learnt so much about my tool, but also how to work as a better teammate for my partners. 

### Skills

#### Problem decomposition

**Problem decomposition** is one of the skills that I have been learning and need to have because there's so much things that I want to do for the **Freedom Project**, but that would have been so much. So, I needed to break down those ideas into smaller pieces so that I can envison what I want to be feature into the game. I had to break it down so that my ideas can be seen, but so my partner's ideas as well. Also, breaking down on what we should do next for the game helps a lot because we're doing it step by step. It's like building legos, you break down in where you want to start first and from there you start building your way up. That's why this skill is important to have because I need to know how to break things down into doable tasks. 

#### Time management

**Time management** is an important skill to have, especially when we have a time frame and a plan to follow. Keeping our time manged is important because I don't want my partner's and I rushing to finish this **MVP**, just because we weren't responsible of our time. Also, since we made a plan, my partner's and I need to follow that plan because that's the time frame that will help us make our **Freedom Project**. So, I need to start managing my time in a responsible way so that no conflict is created because of poor management. 

#### Growth mindset

Having a well **growth mindset** is good to have because instead of sitting there feeling confused, I need to start going around and asking for help if needed. Also, to be understanding, to have patience, and to be considerate since I am working with other people. 

#### Leadership

Having **leadership** is an important skill to have because I need to support my team members in any way that that I can because this project is a team effort and I don't want no one left behind. We need to make these steps together as a whole in order to make our product by the end of the school year. However, I don't want to be the one taking all over the **leadership**, my partners and I should be all leaders, we should all be equal with each other, and help each other out. We are all leaders to make this game.

### Goals

* To start managing my time wisely because I need to slowly start creating something for our **Freedom Project**.
* To communicate more with my partners because I want to check up on them to see what progress they made so far.
* To be well organized with the different ideas and what steps we take for our project.
* Asking for help if needed instead of struggling on my own.

#### Professionalism

I'm conveying my learning by using all the things that I have learnt from the past and today [``Computer Science 9th, SEP10, & SEP11``] by learning, from **Tiny.cc/fccwd**, from **Html** + **CSS**, from **JavaScript**, and from my friends/peers as well. I have learnt many different kinds of coding and format, and how to use them as well. I am using all of my learning, and coding skills in order to make this third blog. I have used some of the html, as well I used some of the markdown. For instance, I used this * to make my words in bold, and I used _ in order to make some words in italic.
