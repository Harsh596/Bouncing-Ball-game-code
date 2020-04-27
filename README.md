# How to make a bouncing ball game with matter.js!
**First , call matter.js into index.html file**
```javascript
<script src="https://unpkg.com/matter-js@0.14.2/build/matter.min.js"></script>
```
**Second , create constants and variables which will be calling the functions of matter.js in sketch .js**
```javascript
const Engine = Matter.Engine;
const World = Matter.World;
const Bodies = Matter.Bodies;

var engine,world;

function setup(){
var canvas = createCanvas = (800,400);
engine = Engine.create();
world = engine.world;
}

function draw(){
Engine.update(engine);
background(0);
}
```
**In the third step , you have to create two classes , one of ground and the other one of ball.
You can make them by creating a different file and calling them in index.html**
```javascript
<script src = "NAME OF YOUR FILE.js"></script>
```
**or you can make them in sketch.js without calling them in index.html file , but the steps in both cases will be same**
   
**Ground**
```javascript
class NameofClass {
constructor(x,y){
var options = {
isStatic : true,
}
this.body = Bodies.rectangle(x,y,800,30,options);
World.add(world,this.body);
}
display(){
rectMode(CENTER);
rect(this.body.position.x,this.body.position.y,800,30);
}
}
```
**Ball**
```javascript
class NameofClass {
constructor(x,y,radius){
var options = {
restitution : 0.8,
}
this.body = Bodies.circle(x,y,30,options);
World.add(world,this.body);
}
display(){
ellipseMode(RADIUS);
ellipse(this.body.position.x,this.body.position.y,30);
}
}
```
**After this you have to call the functions of the classes in sketch.js functions setup and draw**
```javascript
function setup(){
var canvas = createCanvas = (800,400);
engine = Engine.create();
world = engine.world;

ball  = new NameofClass(200,200);
ground = new NameofClass(200,20);
}

function draw(){
Engine.update(engine);
background(0);
ball.display();
ground.display();
}
```
**And after this enjoy your Bouncing Ball game!**
