###  DATE: 04-04-2024

###  NAME: SANJAY SIVARAMAKRISHNAN M
###  ROLL NO : 212223240151
###  DEPARTMENT: AIML
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
~~~
int enable = 6;
int input1 = 3;
int input2 = 4;
void setup()
{
  pinMode(enable, OUTPUT);
  pinMode(input1, OUTPUT);
  pinMode(input2, OUTPUT);
}

void loop()
{
  analogWrite(enable, 10);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(input1, LOW);
  digitalWrite(input2, HIGH);
  delay(5000); // Wait for 1000 millisecond(s)
  digitalWrite(input1, HIGH);
  digitalWrite(input2, LOW);
  delay(5000);
}
~~~

### OUTPUT

## CIRCUIT:
![WhatsApp Image 2024-04-04 at 10 39 09_6e0b255f](https://github.com/sanjaysivaramakrishnan/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151629616/ce472da8-246d-47ac-b6ae-ea31c01a4433)

## SCHEMATIC VIEW:

![WhatsApp Image 2024-04-04 at 10 39 30_715fa984](https://github.com/sanjaysivaramakrishnan/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151629616/a6d448d0-830f-4f04-b197-21cdc21be08e)

### GRAPH AND TABULATION 
![WhatsApp Image 2024-03-21 at 11 45 51_a5902443](https://github.com/sanjaysivaramakrishnan/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151629616/e47de29c-4d19-4ad2-955f-600349460392)

![WhatsApp Image 2024-03-21 at 11 45 51_0fb8f276](https://github.com/sanjaysivaramakrishnan/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151629616/8d161703-d540-4c1f-9836-f74af6f6e740)



### RESULTS AND DISCUSSION 

THUS WE CREATED A DC MOTOR SPEED CONTROL USING ARDUINO
