# stm32-pt100-tutorial
 Obtaining temperature data from a PT100 sensor using STM32.
 
 To read values from the PT100 sensor, two resistors of 100 ohms and 200 ohms are used. 
 The Vdd is connected to one leg of the 100-ohm resistor, and the ADC pin is connected to the same leg. 
 One leg of the 200-ohm resistor should be connected to the other leg of the 100-ohm resistor, while the other leg of the 200-ohm resistor should be connected to GND. 
 The ADC value obtained from the 200-ohm resistor represents the upper limit, whereas the ADC value obtained when the 100-ohm resistor is connected instead of the 200-ohm resistor represents the lower limit.
 
 Then, the obtained values are used in the equation R Parameter = (R upper limit - R lower limit)/(ADC upper limit - ADC lower limit) to calculate the R Parameter value.
 
 We can calculate the resistance value from the R Parameter using the equation Resistance = (R Parameter * (ADC upper limit - ADC lower limit)) + 100.
 
 The PT100 sensor is a temperature sensor that behaves as a resistor in relation to voltage or temperature. 
 It is designed to have a resistance of 100 ohms at 0 degrees Celsius. 
 Based on this information, considering the upper limit as a 200-ohm resistor, we can obtain temperature data by mapping the ADC values in the range of 0-4095 to resistance values in the range of 100-200 ohms.

In this case, I tried to reach a conclusion by creating my own table. It is important to correctly set up the circuit for this code to work properly.
