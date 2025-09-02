# Volt and Amp Meter
###### Developed and simulated a Digital Volt and Amp Meter using Arduino UNO in Tinkercad, integrating a regulated power supply unit, a 5V voltage reducer circuit, and a 16x2 LCD display for real-time monitoring. The system measures both voltage and current, processes the readings through Arduino, and displays the values on the LCD. This project demonstrates the application of embedded systems in electrical measurements, ensuring accurate and user-friendly monitoring for lab and industrial applications.
---
## Here is the references...

Circuit Connections in TINKERCAD :-

<img src=https://github.com/lingeshkumarkamaraj/Volt-and-Amp-Meter/blob/main/1.png> 
<img src=https://github.com/lingeshkumarkamaraj/Volt-and-Amp-Meter/blob/main/2.png> 
<img src=https://github.com/lingeshkumarkamaraj/Volt-and-Amp-Meter/blob/main/3.png> 
<img src=https://github.com/lingeshkumarkamaraj/Volt-and-Amp-Meter/blob/main/4.png> 


Working :- 

[<img width="300" height="300" src="https://img.icons8.com/color/96/start.png" alt="video"/>](https://youtu.be/TvNgKR_favU)


---
Code :-
```

#include<LiquidCrystal.h>
LiquidCrystal lcd(7,6,5,4,3,2);

const float Vref = 5.0;
const float R1 = 50000.0;
const float R2 = 10000.0;

void setup()
{
  lcd.begin(16,2);
  pinMode(A0,INPUT);
  lcd.clear();
}

void loop()
{
  int adc = analogRead(A0);
  float Vard = adc*Vref/1023.0;
  double Vin = Vard*(R1+R2)/R2;
  double Im = Vin/(R1+R2);
  float I = Im*1000000;
  
  lcd.setCursor(0,0);
  lcd.print("V= ");
  lcd.print(Vin);
  lcd.print(" V   ");
  
  lcd.setCursor(0,1);
  lcd.print("I= ");
  lcd.print(I);
  lcd.print(" uA   ");
  
  delay(100);
}

```
---
[TINKERCAD LINK](https://www.tinkercad.com/things/2zYB8xLBW9q-volt-and-amp-meter?sharecode=TcIGJ66ilo16gjZnFTfmzAw6AOa656M9fTdyqLPq7l8)
---
