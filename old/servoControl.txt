#include <Servo.h>
Servo myservo;

int potpin = 0;
int val;
int voltage;

void setup() {
    myservo.attach(13);
    Serial.begin(9600);
    myservo.write(0);
}

void loop() {
val = analogRead(potpin);
val = map(val, 0, 1023, 0, 180);
myservo.write(val);
voltage = analogRead(A5);
delay(100);

Serial.print("Voltage = ");
Serial.println(val);

delay(250);
}
