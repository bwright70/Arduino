# Arduino
This is a series of arduino assingments for school
## Table of Contents
* [Blink and Fade](#BlinkandFade)
* [Finite LED](#FiniteLED)

## Blink and Fade 

### Description

The first assignment was make an Led blink and fade. The blink part of the assignment was fairly simple all I had to do was wire the Led to power and ground then make the power go on and off. Fade was more difficult because it required a loop and variables, but I was able to figure it out in the end. 

### Evidence

#### Arduino Code

```C++
int led = 9;
int brightness = 0;
int fade = 5;

void setup() {

  pinMode(led, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  analogWrite
  (led, brightness);
  brightness = brightness + fade;
  for (int i = 0; i < (brightness / 20); i = i + 1) {
  Serial.print("-");
  }
 
 Serial.println("");
 if (brightness <= 0 || brightness >= 200) {
 fade = -fade;
 }
 
 delay(5);
}
```

### Image

### Reflection

This Assignment was fun and fairly easy. I'm not good at coding but it was still alright. In this Assignment I learned:
* How to wire things
* Int (**Variable**)
* pinmode
* Serial.begin (**Connects to Serial Monitor**)
* analogWrite
* **For** Loop
* Serial.print
* **If** Loop
* Delay

Arduino is awesome. I found it really helpful to rename all my Sketchs.  It is going to be a GREAT year in engineering.

---

## Finite LED

### Description

This was the second assignment and was much easier than the first assignment. I was able to do it on my own! 

### Evidence

#### Arduino Code

```C++
int counter = 0;
int led = 4;

void setup() {

  pinMode(led, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  
  counter = counter + 1;
  if(counter >= 6) {
    Serial.print("Yes");
    digitalWrite(led, HIGH);
  } else {
    Serial.print("No");
    digitalWrite(led, LOW);
    delay(1000);
    digitalWrite(led, HIGH);
    delay(1000);
  }
}
```
### Image

### Reflection

This Assignment was fun and fairly easy. I'm not good at coding but it was still alright. In this Assignment I learned:
* If and **Else** loop

Arduino is awesome. I found it really helpful to rename all my Sketchs.  It is going to be a GREAT year in engineering.

---

## Hello Functions 

### Description

This was the third Assignment and the most difficult so far. It introduced HC-SR04 Sensor which senses objects placed in front of the sensor and the distance the object is from the sensor. Along with the HC-SR04 their was also a servo. The requirements of the assignment were to get the HC-SR04 to spin the servo all while using a function as a part of your code. 

### Evidence

#### Arduino Code

```C++
#include <Servo.h>
#define echoPin 2
#define trigPin 3

Servo myServo;

int servoPin = 12;
int loopDistance = 0;

void setup() {
  Serial.begin(9600);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.println("Ultrasonic Sensor HC-SR04 Test");
  myServo.attach(servoPin);
}

void loop() {
  loopDistance = getdis();
  Serial.print("Distance: ");
  Serial.print(loopDistance);
  Serial.println(" cm");
  
  if ((loopDistance < 5)) {
    turnRight();
  }
  else if ((loopDistance > 5) && (loopDistance < 50)) {
    turnLeft();
  }
  else {
    stopServo();
  }
}
int getdis() {
  long duration;
  int distance;

  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);

  distance = duration * 0.034 / 2; // Speed of sound wave divided by 2 (go and back)
  return distance;
}
void stopServo() {
   myServo.write(89);
}
void turnLeft() {
  myServo.write(40);
}
void turnRight() {
  myServo.write(140);
}
```
### Image

[Wiring](Photos/IMG_0292.JPG)

### Reflection
This assignment was difficult but rewarding once I manged to figure it out (with help). In this Assignment I learned:
* HC-SR04 Distance Sensor
* Functions
* Servo Stuff

Arduino is awesome. I found it really helpful to rename all my Sketchs.  It is going to be a GREAT year in engineering.

---
