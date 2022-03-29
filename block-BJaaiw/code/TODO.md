# Create a 2D breakout game

- Follow the step by step tutorial to create a 2D breakout game.
- Link for tutorial is given below
- https://developer.mozilla.org/en-US/docs/Games/Tutorials/2D_Breakout_game_pure_JavaScript
- Put the code you write in this folder

```js

function Circle(x,y,dx,dy,radius){
     this.x=x;
     this.y=y;
     this.dx = dx;
     this.dy = dy;
     this.radius = radius


     this.draw = function(){
        c.beginPath();
        c.arc(this.x, this.y , this.radius, 0,Math.PI * 2,false);
        c.strokeStyle = 'pink';
        c.stroke();
        c.fill()

     }

     this.update = function(){
        if(this.x + radius > innerWidth || this.x - radius < 0){
            this.dx = -this.dx;
        }
        if(this.y + radius > innerHeight || this.y - radius < 0){
            this.dy = -this.dy
        }
        this.x += this.dx;
        this.y += this.dy;

        this.draw();
 
     }
 
 }


var circleArray =[]

for(var i=0;i<100;i++){ 
     var x = Math.random() * (innerWidth - radius * 2)+ radius;
     var y = Math.random() * (innerHeight - radius * 2)+ radius;
     var dx = (Math.random() - 0.5);
     var dy = (Math.random() - 0.5);

     var radius = 30;
     circleArray.push(new Circle(x,y,dx,dy,radius));

}

   var circle = new Circle(200,200,3,3,30)

  
    function animate(){
        requestAnimationFrame(animate);
        c.clearRect(0,0,innerWidth,innerHeight);

        for (var i = 0; i < circleArray.length; i++){
            circleArray[i].update();

        } 
        
    } 
```
    animate()

