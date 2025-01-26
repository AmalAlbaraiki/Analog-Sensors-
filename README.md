# Analog-Sensors-
LDR Sensor
Introduction
The Light Dependent Resistor (LDR) sensor is a device that changes its electrical resistance in response to the intensity of light falling on it. This sensor is widely used in applications such as automatic lighting systems, light level sensing, and illumination control.
Objectives
This report aims to analyze the design and programming of an LDR sensor circuit connected to an Arduino board, explaining how light intensity is measured and converted into digital signals for controlling various devices.
Components Used
1.	Arduino Uno Board
2.	LDR Sensor (Photoresistor)
3.	Resistor (10kΩ)
4.	LED Light
5.	Connecting Wires
6.	Breadboard
Working Principle
The LDR sensor operates on the principle that its resistance decreases when exposed to light and increases in darkness. It is connected with a fixed resistor to form a voltage divider circuit, where the resulting voltage is proportional to the amount of light falling on the sensor.
Circuit Design Steps
1.	Connect one terminal of the LDR sensor to the 5V supply and the other terminal to an analog input pin (A0) on the Arduino, with a resistor connected to ground (GND).
2.	Connect an LED to digital pin (D3) via an appropriate resistor.
3.	Upload the programming code to the Arduino board to read values from the sensor and determine the light level.
Code Implementation
int LDRpin = A0;
int LED = 3;
void setup() {
  Serial.begin(9600);
  pinMode(LED, OUTPUT);
}
void loop() {
  int lightLevel = analogRead(LDRpin);
  Serial.println(lightLevel);
  if (lightLevel < 500) {
    digitalWrite(LED, HIGH);
  } else {
    digitalWrite(LED, LOW);
  }
  delay(500);
}
Performance Analysis
•	When the light intensity is low (LDR reading below 500), the LED turns on.
•	When the light intensity is high (LDR reading above 500), the LED turns off.
Results and Recommendations
•	The experiment demonstrated good responsiveness of the LDR sensor in different lighting conditions.
•	It is recommended to use a variable resistor instead of a fixed one to achieve higher accuracy in measuring light intensity.
•	The sensor can be integrated into smart home systems for automatic lighting control.
Conclusion
The LDR sensor is an effective and easy-to-use tool in Arduino projects related to light detection. It can be employed in various applications to improve energy efficiency.

  
