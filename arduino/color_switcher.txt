int r_led = 13;
int g_led = 12;
int y_led = 11;

int rgb_r = 5;
int rgb_g = 6;
int rgb_b = 9;

int color_switch = 2;
int color_adjust = 3;
int switch_val = HIGH;
int prev_switch_val = HIGH;
int switch_pressed = false;
int adjust_val = HIGH;

int pot = A0;

int led = r_led;
int rgb = rgb_r;

void setup() {
  // put your setup code here, to run once:
  pinMode(r_led, OUTPUT);
  pinMode(g_led, OUTPUT);
  pinMode(y_led, OUTPUT);

  pinMode(rgb_r, OUTPUT);
  pinMode(rgb_g, OUTPUT);
  pinMode(rgb_b, OUTPUT);

  pinMode(color_switch, INPUT);
  pinMode(color_adjust, INPUT);

  digitalWrite(led, HIGH);

}

void loop() {
  // put your main code here, to run repeatedly:

  switch_val = digitalRead(color_switch);         // read the value of pin 2
  
  if(switch_val == LOW && prev_switch_val == HIGH) {  // if the button is pressed
    switch_pressed = true;                        // but wasn't pressed last
  }                                                   // check, set the variable
  else {                                              // 'pressed' to true, otherwise
    switch_pressed = false;                       // set it to false
  }

  if(switch_pressed) {
    digitalWrite(led, LOW);                                // if 'pressed' is true
    if(led == r_led) {                              // and led is off,
      led = g_led;
      rgb = rgb_g;                                // turn led on
    }                                                 // if 'pressed is true
    else if(led == g_led) {                   // and led is on,
      led = y_led; 
      rgb = rgb_b;                                 // turn led off
    }                                                 // if 'pressed is true
    else if(led == y_led) {                                         // and led is on,
      led = r_led;
      rgb = rgb_r;                                  // turn led off
    }
    digitalWrite(led, HIGH);                            
  }

  if(switch_val != prev_switch_val) {                 // if the button has been pressed or 
    delay(50);                                        // released, give the circuit time
  }                                                   // to settle

  prev_switch_val = switch_val;

  adjust_val = digitalRead(color_adjust);

  if(adjust_val == LOW) {
    int pot_val = analogRead(pot);
    int rgb_val = map(pot_val, 0, 1023, 0, 255);
    analogWrite(rgb, rgb_val);
  }

}
