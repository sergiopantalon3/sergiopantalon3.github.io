/*
 * blend the colors of an RGB LED
 */

// assign pins based off circuit
int redPin = 3;
int greenPin = 5;
int bluePin = 6;

int red_val = 209;
int green_val = 5;
int blue_val = 249;

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize all three pins as outputs.
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  pinMode(bluePin, OUTPUT);

  // set the different levels of red, green and blue to make your color
  analogWrite(redPin, red_val);
  analogWrite(greenPin, green_val);
  analogWrite(bluePin, blue_val);
}

// the loop function runs over and over again forever
void loop() {
  // nothing to do here
}
