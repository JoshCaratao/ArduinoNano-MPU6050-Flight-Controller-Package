Flight Controller Code (All code has either been written by Joshua Caratao or learned and adapted from other helpful resources)

*NOTE: This code runs on a physical Flight Controller consisting of an Arduino Nano and a separate Intertial Measurement Unit (IMU)(MPU 6050). 

This should still work for other arduinos/microcontrollers, however, pins may differ. Additionally, if you are using a microcontroller with its own internal sensors (gyroscope and accelerometer), functions to get those sensor readings will differ.

HOW IT WORKS:

  So far, the flight controller runs a main program called "FlightController" and a separate program for outputting serial data to the terminal and to graph visualizers in the Arduino IDE (for testing purposes)

  Using the I2C communication protocol to allow for proper communication between the Arduino and the IMU, raw data values are taken in and converted to rotational rates and linear accelerations. From these, separate roll, pitch, and yaw angles are calculated using numerical integration(gyroscope) and trigonemetric equations (accelerometer).

  However, because either sensor is unreliable for accurate attitude estimation alone, I implmented a sensor fusion algorithm through a simple complementary filter to combine both sensor measurements into one, more reliable measurement.

  

My overall goals are to successfully, read IMU Data from the MPU-6050 to calculate craft orientation, take in commands from a radio controller, and implement a PID Controller for quadcopter dynamics and self-leveling. 
