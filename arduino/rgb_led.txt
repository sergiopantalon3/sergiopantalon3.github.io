/*
 * blend the colors of an RGB LED
 */

// assign pins based off circuit
int redPin = 3;
int greenPin = 5;
int bluePin = 6;

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize all three pins as outputs.
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  pinMode(bluePin, OUTPUT);

  // set the different levels of red, green and blue to make your color
  analogWrite(redPin, 209);
  analogWrite(greenPin, 5);
  analogWrite(bluePin, 249);
}

// the loop function runs over and over again forever
void loop() {
  // nothing to do here
}
