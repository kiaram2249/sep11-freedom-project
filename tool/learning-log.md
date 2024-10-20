# Tool Learning Log

## Tool: **P5play**

## Project: **Gardern Game**

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
```

* Using **canvas** down the road will be very useful because **canvas** haves nice features. For instance, we can use **canvas** so that we can be able to do some pixel art games.
* We can also use **canvas** to do NE tricks, such as specifying an aspect ratio for the **canvas** instead of having specific dimensions. [Canvas](https://editor.p5js.org/kiaram2249/sketches/VtfUHQrwN)

```js
function setup() {
  new Canvas("1:1");
  new Canvas("2:1");
}
```

---

### Introduction of Sprites

* **Sprite** is an element in the simulated world of **P5play**
* It's something that exists on the screen
* Something that's going to move around
* Something that's going to have **Physics simulation** applied to it
   * (_All the game objects in P5play are going to be Sprite objects_)
* Since **Sprite** are objects we can put them into **variables**

**Local**
(_The **let ball** variable is a **local** variable meaning that we can only be able to access it inside setup_); 

```js
function setup() {
  new Canvas(400, 400);
  let ball = new Sprite();
}
```

**Global**
(_We declare it as a **global** variable but putting **let ball;** outside and ontop of the **function**, and then we changed the inside of the **function** by deleting the **let**. Making it now call **ball = new Sprite();**_)

```js
let ball;
function setup() {
  new Canvas(400, 400);
  ball = new Sprite();
}
```



### X/X/XX:
* Text


<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
