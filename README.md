# midterm
i'm still new to coding and im still trying to wrap my head around and understand java so a lot of this code is cited with some minor changes by me.
//code from https://alinmeisya.blogspot.com/

int LrectY = 350;
int RrectY = 350;

float ellX=width/2;
float ellY=height/2;

float speedVertical=4;
float speedSide=3;

PFont font;

boolean moveDown=true;
boolean moveRight=true;

int countR=0;
int countL=0;

void setup () {
  
  size (700, 700);
  background(300);
  font = loadFont("thisfont.vlw");
  
}

void draw () {
  
  background (70);
  textFont (font);
  
  fill (400, 0, 0);
  ellipse (ellX, ellY, 30, 30);
  text("score", 300, 40);
  
  fill (0, 255, 0);
  rect (20, LrectY, 20, 200);
  text(countL, 250, 60);
  
  fill (0, 0, 255);
  rect(630, RrectY, 20, 200);
  text(countR, 550, 60);

  //pressing the keys moves the bars up or down
  if (keyPressed == true && key == 'q') {
    LrectY = LrectY - 8;
  }
  
  if (keyPressed == true && key == 'a') {
    LrectY = LrectY + 8;
  }
  
  if (keyPressed == true && key == 'p') {
    RrectY = RrectY - 8;
  }
  
  if (keyPressed == true && key == 'l') {
    RrectY = RrectY + 8;
  }
    
    //ball movements   
   if (moveRight == true)
   {
     ellX = ellX + speedSide;
  }
  else {
    ellX = ellX - speedSide;
  }
  
  if (moveDown == true)
  {
    ellY = ellY + speedVertical;
  }
  else {
    ellY = ellY - speedVertical;
  }
  
    if (ellY <= 10) {
    moveDown = true;
    speedSide = random(5, 10);
  }
    
  if (ellY >= 670) {
    moveDown = false;
    speedSide = random(5, 10);
  }
    
  if (ellX >= 670) {
    countL++;
    ellX=width/2;
    ellY=height/2;
    speedSide = random(5, 10);
  }
    
  if (ellX <= 10) {
    countR++;
    ellX=width/2;
    ellY=height/2;
    speedSide = random(5, 10);

  }
    
  if (ellX >= 615 && ellY > RrectY && ellY < (RrectY + 100)) {
    moveRight = false;
    speedSide = random(5, 10);
      
  }
    
  if (ellX <= 75 && ellY > LrectY && ellY < (LrectY + 100)) {
    moveRight = true;
    speedSide = random(5, 10);
  }
}
    
    
    
    
    
