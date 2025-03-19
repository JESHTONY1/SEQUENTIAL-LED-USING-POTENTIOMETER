#define trigPin 9
#define echoPin 10
#define buzzerPin 13
void setup() {
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
pinMode(buzzerPin, OUTPUT);
Serial.begin(9600);
}
void loop() {
long duration, distance;
digitalWrite(trigPin, LOW);
delayMicroseconds(2);
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);
duration = pulseIn(echoPin, HIGH);
distance = (duration * 0.034) / 2;
if (distance <= 59)
{
digitalWrite(buzzerPin, HIGH);
delay(5000);
digitalWrite(buzzerPin, LOW);
}
else {
digitalWrite(buzzerPin, LOW);
}
{
Serial.print(distance);
Serial.println(" cm");
delay(500);
}
}
