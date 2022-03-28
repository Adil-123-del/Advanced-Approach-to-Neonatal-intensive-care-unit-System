# Advanced-Approach-to-Neonatal-intensive-care-unit-System
#The preterm infant care is one of the most important, delegate and sensitive areas in the Biomedical field. 
#The purpose of this project is to design and implement a control system to regulate and mainly monitor the various parameters inside the incubator or baby cradle. 
#Also, it is used to monitor and control the temp and humidity in the incubator. 
#Microcontroller will be used for implementing the hardware. The closed loop control system is a combination of sensors and actuators that operates synchronously to provide a stable thermal environment inside the
incubator. 
#The system keeps on checking various parameters in a real time incubator or baby cradle and will inform the admin about all values of the baby cradle globally.
#We are use Azure cloud to save our data in this project.
#code:
#include <Servo.h>
Servo myservo;  // create servo object to control a servo
// twelve servo objects can be created on most boards
void setup() { 
pinMode(12,INPUT_PULLUP);
pinMode(13,OUTPUT);
digitalWrite(13,LOW);
Serial.begin(9600);
  myservo.attach(3);  // attaches the servo on pin 9 to the servo object
}
void loop() 
{
  delay(300);
  int ldr1 = analogRead(A0);
    int ldr2 = analogRead(A1);
      int ldr3 = analogRead(A2);
        int ldr4 = analogRead(A3);
      int butval =digitalRead(12);
      
if ( (ldr1<120 ) || (ldr2<120 ) || (ldr3<120 ) || (ldr4<120 ) )
{
  data = 10;
}
else
{
  data = 20;
}
if ((count1 ==50) && (data == 10))
{
 Serial.println("detected");
     myservo.write(0); 
digitalWrite(13,HIGH);
   
}
if ((count1==40) && (data == 20))
{
  Serial.println("not detected");
  digitalWrite(13,LOW);
}  
}
