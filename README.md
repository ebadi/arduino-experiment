# arduino-experiment
Arduino Experiments


`sudo chmod 666 /dev/ttyUSB0`

```
Tools -> Port -> /dev/ttyUSB0
Tools -> Board -> Arduino Nano 
Tools -> Processor -> ATmega3289P -> ATmega3289P(Old Bootloader)
```

```
int timer = 100;
void setup() {
  randomSeed(analogRead(8));
  for (int thisPin = 0; thisPin < 20; thisPin++) {
    pinMode(thisPin, OUTPUT);
  }
  for (int thisPin = 0; thisPin < 20; thisPin++) {
    digitalWrite(thisPin, HIGH);
    delay(100);
    digitalWrite(thisPin, LOW);
  }
  for (int thisPin = 20; thisPin > 1; thisPin--) {
    digitalWrite(thisPin, HIGH);
    delay(100);
    digitalWrite(thisPin, LOW);
  }
}

void loop() {
  const byte leds[] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20};
  byte led;
  led = leds[random(0, 20)];

  int count = random(0, 5);
  for (int i = 0; i < count; i++) {
    digitalWrite(led + i, HIGH);
  }

  delay(100);
  for (int i = 0; i < count; i++) {
    digitalWrite(led + i, LOW);
  }
  delay(100);
}
```
