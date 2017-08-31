# Led On Off

## Source
~~~
#include <SoftwareSerial.h>
#define ESP_RX 3
#define ESP_TX 1
#define LED_RED 4

char character;

void setup()  {
  pinMode(ESP_RX, INPUT);
  pinMode(ESP_TX, OUTPUT);
  pinMode(LED_RED, OUTPUT);     
  
  digitalWrite(LED_RED, HIGH);
  Serial.begin(9600);
  Serial.println("Hello from Arduino");
}

void loop() {
  if (Serial.available()) {
    character = Serial.read();
    
    if (character=='1') {
      digitalWrite(LED_RED, HIGH);
      Serial.println("LED on");
    } else if (character=='2') {
      digitalWrite(LED_RED, LOW);
      Serial.println("LED off");
    } else {
      Serial.print(character);
    }
  }
}
~~~

## Serial monitor
![Serial](https://github.com/wtopolski/arduino/blob/master/led_on_off/serial_monitor.png "Serial monitor")

## Device configuration
![Device](https://github.com/wtopolski/arduino/blob/master/led_on_off/device_configuration.jpg "Device configuration")
