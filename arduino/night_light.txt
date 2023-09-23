/*
 * Turns on a light if it gets too dark
 */

int analog_pin = A0;
int led_pin = 13;

int threshold = ??;

// the setup function runs once when you press reset or power the board
void setup() {
  pinMode(led_pin, OUTPUT);   // set led pin to output
}

// the loop function runs over and over again forever
void loop() {

  int sensor_value = analogRead(analog_pin);   // read the analog in value

  if(sensor_value > threshold) {               // if sensor value is greater
    digitalWrite(led_pin, HIGH);               // than our threshold, turn
  }                                            // the light on
  else {
    digitalWrite(led_pin, LOW);                // otherwise, turn the light
  }                                            // off

  delay(5);                                    // pause to let ADC settle
}
