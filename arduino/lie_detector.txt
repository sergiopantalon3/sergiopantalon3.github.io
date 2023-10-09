/*
 * Test our if() statements
 */

// assign pin based off circuit
int red_led = 13;
int green_led = 12;

// these are the variables we'll play around with
int a = true;
int b = false;

// the setup function runs once when you press reset or power the board
void setup() {
  pinMode(red_led, OUTPUT);
  pinMode(green_led, OUTPUT);

  // change the expression inside the if() and look at the results
  if (a) {                       
    digitalWrite(red_led, LOW);
    digitalWrite(green_led, HIGH);
  }
  else {
    digitalWrite(green_led, LOW);
    digitalWrite(red_led, HIGH);
  }
}

// the loop function runs over and over again forever
void loop() {

}
·