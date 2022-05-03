# EXPERIMENT-NO--04-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resistor

## AIM: 
To interface an FSR(force sensitive resistor) and scale the output voltage obtained to pressure applied 
 
### COMPONENTS REQUIRED:
1.	FSR  (force sensitive resistor)
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 

### THEORY: 
FSRs are basically a resistor that changes its resistive value (in ohms Ω) depending on how much it is pressed. These sensors are fairly low cost, and easy to use. They also vary some from sensor to sensor perhaps 10%. FSR's resistance changes as more pressure is applied. When there is no pressure, the sensor looks like an infinite resistor (open circuit), as the pressure increases, the resistance goes down. This graph indicates approximately the resistance of the sensor at different force measurements.
 
![image](https://user-images.githubusercontent.com/36288975/163532939-d6888ae1-4068-4d83-86a7-fc4c32d5179e.png)

### FIGURE 01 GRAPH OF FORCE vs RESISTANCE **

![image](https://user-images.githubusercontent.com/36288975/163532957-82d57567-a1c3-48c5-8a87-7ea66d6fca49.png)

### FIGURE 02 FORCE SENSITIVE RESITOR FOIL DISC TYPE  

FSRs are often a polymer with conductive material silk-screened on. That means they're plastic and the connection tab is crimped on somewhat delicate material. The best way to connect to these is to simply plug them into a breadboard.

The easiest way to measure a resistive sensor is to connect one end to power and the other to a pull-down resistor to ground. Then the point between the fixed pull down resistor and the variable FSR resistor is connected to the analog input of a microcontroller such as an Arduino The way this works is that as the resistance of the FSR decreases, the total resistance of the FSR and the pull down resistor decreases from about 100Kohm to 10Kohm. That means that the current flowing through both resistors increases which in turn causes the voltage across the fixed 10K resistor to increase.

 ![image](https://user-images.githubusercontent.com/36288975/163532972-2b909551-12c9-485d-adb1-d1e988d557bd.png)

### TABLE -01 FORCE AND OUTPUT VOLTAGES**
	
  Table -01 indicates the approximate analog voltage based on the sensor force/resistance w/a 5V supply and 10K pull down resistor.

### Vo = Vcc ( R / (R + FSR) )								Eq-01

****Where R= 1KΩ in this experiment 
****That is, the voltage is proportional to the inverse of the FSR resistance.


![image](https://user-images.githubusercontent.com/36288975/163532979-a2a5cb5c-f495-442c-843e-bebb82737a35.png)

### FIGURE-03 CIRCUIT DIAGRAM

![image](https://user-images.githubusercontent.com/74660507/166241830-6732e218-3192-4264-9679-f640c08ecc65.png)

### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select the board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 
10.	Plot the graph for the output voltage vs the resistance 

### PROGRAM 
 ```c
// C++ code
//
int force = 0;

float f = 0;
void setup()
{
  pinMode(A3, INPUT);
  pinMode(8, OUTPUT);
  Serial.begin(9600);

}

void loop()
{
  force= analogRead(A3);
  f = map(force,0,500,0,10);
  //Serial.print("Force =");
  Serial.println(f);
  analogWrite(8, force);
  delay(1000); // Wait for 1000 millisecond(s)
  
}
```
 ### Output:
 ![exp4](https://user-images.githubusercontent.com/75234588/166480908-21d07ba6-d5b1-44e8-8133-bc21ed95dcb7.png)



### TABLE -02 OUTPUT VOLTAGES AND CHANGE IN RESISTANCES

![Screenshot (60)](https://user-images.githubusercontent.com/75234588/166481089-d63f0dff-c9d7-457c-a91a-b8a361aedcaf.png)

![exp 4 table](https://user-images.githubusercontent.com/75234588/166481269-6a26ac81-bbca-4f6d-83e2-0ba481284596.jpeg)





### RESULTS : Arduino uno is interfaced with FSR and output values are indicated on a graph.
