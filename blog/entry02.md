# Entry 2
##### 12/9/2024

### Content 

So far I have been able to learn new things about my tool [P5play](https://p5play.org/). I have been tinkering for one month probably a half by now, and I have learnt so much about my tool. For inctance, the first time that I was tinkering I wanted to have a sense about the **Sprites**, because in order for me to make shape for example I would have to need a **sprite**. This was a huge thing for me to learn about because when I was going in depth of **P5play**, I realized that **sprites** is important and that **sprites** is needed for everything. I say this because the next thing that I learnt was **sprite.collider** , **sprite.moveTo(mouseX, mouseY)**, and adding text inside of the shape or sprite. It's important that I need how to do this because it can help with my groups **Freedom Project**. Also, lastly I was able to learn how to set a **backgroud** by using **sprites** and how to set a little character by using a **sprite** as well. However, all of these coding and the different **sprites** that I was able to learn by tinkering will come in handy because while I was learning about these factors/technique, I was ready thinking about how I can incorporate these into the game. 

### Sprite.collider

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














Text

[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
