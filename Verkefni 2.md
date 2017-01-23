Svar við 1. 

public: scope to make that variable/function available from anywhere, other classes and instances of the object.

private: scope when you want your variable/function to be visible in its own class only.

protected: scope when you want to make your variable/function visible in all classes that extend current class including the parent class

Svar við 2.  

Inheritance :
A class can be defined using another class as a foundation. In object-oriented programming terminology, one class can inherit fi elds and methods from another. An object that inherits from another is called a subclass, and the object it inherits from is called a superclass. A subclass extends the superclass.

SpinSpots spots;
SpinArm arm;

void setup() {
  size(640, 360);
  arm = new SpinArm(width/2, height/2, 0.01);
  spots = new SpinSpots(width/2, height/2, -0.02, 90.0);
}

void draw() {
  background(204);
  arm.update();
  arm.display();
  spots.update();
  spots.display();
}

class Spin {
  float x, y, speed;
  float angle = 0.0;
  Spin(float xpos, float ypos, float s) {
    x = xpos;
    y = ypos;
    speed = s;
  }
  void update() {
    angle += speed;
  }
}

class SpinArm extends Spin {
  SpinArm(float x, float y, float s) {
    super(x, y, s);
  }
  void display() {
    strokeWeight(1);
    stroke(0);
    pushMatrix();
    translate(x, y);
    angle += speed;
    rotate(angle);
    line(0, 0, 165, 0);
    popMatrix();
  }
}

class SpinSpots extends Spin {
  float dim;
  SpinSpots(float x, float y, float s, float d) {
    super(x, y, s);
    dim = d;
  }
  void display() {
    noStroke();
    pushMatrix();
    translate(x, y);
    angle += speed;
    rotate(angle);
    ellipse(-dim/2, 0, dim, dim);
    ellipse(dim/2, 0, dim, dim);
    popMatrix();
  }
}
Svar við 3. The PHP Autoloader searches recursively in defined directories for class, trait and interface definitions. Without any further configuration the directory in which the requiring file resides will be used as default class path.

Svar við 5. 

The main advantages of OOP are:

Reusability of code; a well designed object has only one specific function and is therefore completely independent of the environment it is placed in and thus can be reused easily.
Clearer structure of code; again a well designed object has only one specific function which means that all the code supporting that function is located in one place which increase maintainability.
A major disadvantage of OOP is that it requires more lines of code and is therefore more time consuming to produce.
