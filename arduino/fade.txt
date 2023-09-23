/*
 * Gradually fade an LED on and off
 */

// assign pin based off circuit
int led = 9;

int brightness = 0;     // holds the value for how bright the led is
int fade_amount = 5;    // how much the brightness changes each loop

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin 9 as an output.
  pinMode(led, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  analogWrite(led, brightness);                // set the brightness of pin 9
  
  brightness = brightness + fade_amount;       // update the brightness for the next loop

  if (brightness == 0 || brightness == 255) {  // if the LED is all the way off or on
    fade_amount = fade_amount * -1;            // change the direction of the fade
  }
  delay(30);                                   // pause to see the dimming effect
}
