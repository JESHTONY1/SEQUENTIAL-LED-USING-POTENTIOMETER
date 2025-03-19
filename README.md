const int potPin = A0;
const int ledPins[] = {2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13};
const int numLeds = sizeof(ledPins) / sizeof(ledPins[0]);
void setup() {
for (int i = 0; i < numLeds; i++) {
pinMode(ledPins[i], OUTPUT);
}
pinMode(potPin, INPUT);
}
void loop() {
int potValue = analogRead(potPin);
int ledDelay = map(potValue, 0, 1023, 50, 500);
for (int i = 0; i < numLeds; i++) {
digitalWrite(ledPins[i], HIGH);
delay(ledDelay);
digitalWrite(ledPins[i], LOW);
}
}
