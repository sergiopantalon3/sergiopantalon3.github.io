/*
 * make a push button behave like a switch
 */

// assign pins based off circuit
int button = 2;
int led = 13;

int button_val = HIGH;        // the button starts off not pressed
int last_button_val = HIGH;   // and wasn't pressed before the sketch started
int pressed = false;          // will tell us if the button was just pressed
int led_val = LOW;            // LED starts turned off

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize pin 2 as an input and pin 13 as an output
  pinMode(button, INPUT);
  pinMode(led, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  button_val = digitalRead(button);                   // read the value of pin 2
  
  if(button_val == LOW && last_button_val == HIGH) {  // if the button is pressed but 
    pressed = true;                                   // wasn't pressed last check,
  }                                                   // set the variable 'pressed' to true
  else {            
    pressed = false;                                  // otherwise set it to false
  }

  if(pressed) {                                       // if 'pressed' is true
    if(led_val == LOW) {                              // and led is off,
      led_val = HIGH;                                 // turn led on
    }                                                 // if 'pressed is true
    else {                                            // and led is on,
      led_val = LOW;                                  // turn led off
    }                              
  }

  digitalWrite(led, led_val);                         // write the LED state to the LED

  if(button_val != last_button_val) {                 // if the button has been pressed or 
    delay(50);                                        // released, give the circuit time
  }                                                   // to settle

  last_button_val = button_val;                       // update last_button_val for next loop
}
