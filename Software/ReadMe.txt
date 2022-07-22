Thank you for downloading the YMFC-AL software package. 

Current version: 1.4 April 30, 2017

Content:
YMFC-AL_setup.ino
YMFC-AL_esc_calibrate.ino
YMFC-AL_Flight_controller.ino


Revision update:
=====================================================================================================================================================

Version 1.4 April 30, 2017
The calibration sketch stops working when a character or number is send. When sending a character via the serial monitor of some Arduino IDE’s a line feed is also send. Because the ESC calibration program only expects one character the program stops working.

In the code the line:
data = Serial.read();                                                               //Read the incomming byte.

Is changed into:
data = Serial.read();                                                               //Read the incomming byte.
delay(100);                                                                         //Wait for any other bytes to come in
while(Serial.available() > 0)loop_counter = Serial.read();                          //Empty the Serial buffer.
=====================================================================================================================================================

Version 1.3 October 30, 2016
With the newer Arduino IDE versions (1.6.x and up) the setup program hangs due to optimization of the compiler. This is fixed in this version.

The starting speed of the motors is reduced to 1100us.


=====================================================================================================================================================

Version 1.2 - July 12, 2016
The last code did not fix the complete problem so I had to make another adjustment to the code. The acc_x and acc_y values can also be negative so a simple smaller or greater test does not work.
Therefor I changed the code to:

if(abs(acc_y) < acc_total_vector){                                        //Prevent the asin function to produce a NaN
  angle_pitch_acc = asin((float)acc_y/acc_total_vector)* 57.296;          //Calculate the pitch angle.
}
if(abs(acc_x) < acc_total_vector){                                        //Prevent the asin function to produce a NaN
  angle_roll_acc = asin((float)acc_x/acc_total_vector)* -57.296;          //Calculate the roll angle.
}

This prevents a division by zero and the input value for the asin function will always be smaller than 1.
=====================================================================================================================================================

Version 1.1 - July 11, 2016
There was a NaN (not a number) problem in the code. When flying more aggressive the quadcopter could become uncontrolable. The NaN problem is caused by the following:
When the absolute value of acc_y or acc_x becomes larger that the acc_total_vector the values provided to the asin function is larger than 1 and the asin function produces a NaN.
It recovers when the acc_total_vector becomes larger that the acc_x or acc_y values. But due to the complimentary filter the NaN error persists.
This problem will only occur when flying aggressive / fast descents. 

I changed the code as followed:
from:
angle_pitch_acc = asin((float)acc_y/acc_total_vector)* 57.296;            //Calculate the pitch angle.
angle_roll_acc = asin((float)acc_x/acc_total_vector)* -57.296;            //Calculate the roll angle.

to:
if(acc_y > acc_total_vector){
  angle_pitch_acc = asin((float)acc_y/acc_total_vector)* 57.296;            //Calculate the pitch angle.
}
if(acc_x > acc_total_vector){
  angle_roll_acc = asin((float)acc_x/acc_total_vector)* -57.296;            //Calculate the roll angle.
}
=====================================================================================================================================================

Version 1.0 - July 3, 2016
Release
=====================================================================================================================================================