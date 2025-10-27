const int trigPin = 9;
const int echoPin = 10;

long duration;
float distance;
int count = 0;
bool objectPresent = false;
const int threshold = 10;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.begin(9600);
  Serial.println("Ultrasonic Object Counter Started");
}

void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");

  if (distance < threshold && !objectPresent) {
    objectPresent = true;
    count++;
    Serial.print("Object Detected! Total Count: ");
    Serial.println(count);
  }

  if (distance >= threshold && objectPresent) {
    objectPresent = false;
  }

  delay(100);
}
