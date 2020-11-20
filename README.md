# Arduino
This is a series of arduino assingments for school
## Table of Contents
* [Blink and Fade](#BlinkandFade)

## Blink and Fade 

### Description

The first assignment was make an Led blink and fade. The blink part of the assignment was fairly simple all I had to do was wire the Led to power and ground then make the power go on and off. Fade was more difficult because it required a loop and variables, but I was able to figure it out in the end. 

### Evidence

#### Arduino Code

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

### Image

### Reflection


---
