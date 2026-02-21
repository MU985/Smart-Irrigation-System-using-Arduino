#  Smart Irrigation System using Arduino

This project implements a Smart Irrigation System that automatically waters plants based on soil moisture levels. The system monitors soil conditions and controls a water pump to ensure plants receive the required amount of water without manual intervention.

---

## Project Overview
The system uses a soil moisture sensor to detect the water content in the soil. Based on the sensor readings, the Arduino automatically switches the water pump ON or OFF, ensuring efficient irrigation and preventing water wastage.

---

##  Objectives
- Automate plant irrigation
- Monitor soil moisture in real time
- Save water and prevent overwatering
- Reduce manual effort

---

##  Components Used

###  Hardware
- Arduino Uno
- Soil Moisture Sensor
- Relay Module
- Water Pump / Motor
- Jumper Wires
- Power Supply

###  Software
- Arduino IDE
- Embedded C / Arduino Programming

---

##  Working Principle

1. Soil moisture sensor measures moisture level.
2. Sensor sends data to Arduino.
3. Arduino compares value with threshold.
4. If soil is dry → pump turns ON.
5. If soil is wet → pump turns OFF.

---

##  Circuit Connections

- Soil Moisture Sensor → A0  
- Relay Module → Digital Pin 7  
- Pump connected via relay  

*(Add circuit diagram image here if available)*

---

##  Sample Arduino Code

```cpp
int sensorPin = A0;
int relayPin = 7;
int moistureValue;
int threshold = 500;

void setup() {
  pinMode(relayPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  moistureValue = analogRead(sensorPin);
  Serial.println(moistureValue);

  if (moistureValue > threshold) {
    digitalWrite(relayPin, LOW);  // Pump ON
  } else {
    digitalWrite(relayPin, HIGH); // Pump OFF
  }

  delay(1000);
}
