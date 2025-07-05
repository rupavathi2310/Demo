
🔌 Arduino Code for IR Sensor Detection (ir_sensor_demo.ino)
// IR Sensor Demo Code
int irSensor = 2;     // IR sensor connected to digital pin 2
int led = 13;         // LED connected to digital pin 13

void setup() {
  pinMode(irSensor, INPUT);
  pinMode(led, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int sensorValue = digitalRead(irSensor);

  if (sensorValue == LOW) {  // Object detected (depends on sensor)
    digitalWrite(led, HIGH); // Turn on LED
    Serial.println("Object Detected!");
  } else {
    digitalWrite(led, LOW);  // Turn off LED
    Serial.println("No Object");
  }

  delay(500); // Wait half a second
}

