/*
 * Send analog input values to the serial monitor
 */

int analog_pin = A0;

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize serial communications at 9600 bps:
  Serial.begin(9600);
}

// the loop function runs over and over again forever
void loop() {
  int sensor_value = analogRead(analog_pin);   // read the analog in value

  Serial.print("sensor = ");                  // send the sensor value
  Serial.println(sensor_value);               // to the serial monitor

  delay(500);                                 // slow down for readabilty
}
