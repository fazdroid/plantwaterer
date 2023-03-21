# plantwaterer
Automated Plant Waterer


For this project, we are not using any library we are just using the basic functions for programming. The code is very simple and easy to use. The explanation of the code is as follows.

We start by defining all the required integers here I used two integers for storing the soil moisture and the converted moisture percentage.

Now, we define the pin mode, here I have used pin 3 as an output and in the next line, I have initialised Serial Monitor for debugging.

I started the loop section by reading the soil moisture. I used the analogRead function of Arduino to read the soil moisture and I stored that in soilMoistureValue. This value varies from 0 to 1023

In the below line, I have converted the sensor values from 0-100 percent for that we use the map function on Arduino. That means that if the soil is dry then the output moisture percentage is 0% and if the soil is extremely wet then the moisture percentage is 100%.

Calibrating our Moisture Sensor 
In the map function, we need to assign the dry value and wet value. To do that we need to monitor that values. You can read that values using the following code:

Upload the above code to your Arduino and open the serial monitor. Then place your soil moisture sensor in dry soil or just hold the sensor in the air and read the value. now put that value in place of 490(second term of map function).

The next step is to place the sensor in wet soil or submerge it in water and read the value and assign that value in place of 1023 (third term of map function). These values will calibrate your sensors correctly to get better results.

After converting the values we can control the pump according to the soil moisture percentage. With the help of ‘If condition’, I write the first condition, if the moisture percentage goes below 10, then the Arduino will turn pin 3 to LOW and the pump will turn on ( our relay module uses the active low signal to trigger) and the Arduino will print pump on message in the serial monitor.

When the moisture percentage goes above 80 percent ( indicating soil is filled with water) the Arduino will turn off the pump and print the ‘pump off’ on the serial monitor.

