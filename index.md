# Obstacle Avoiding Car
Using the Arduino chip and application, I code my robot to not encounter any objects without any remote control.

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Sarika Lakhani | Henry M. Gunn High school | Electrical Engineer | Incoming Junior

![Add pic of final project](add link of pic here)

# Materials
1. Arduino
2. Mini wheel and motor kit
3. Wires
4. Sensor 
5. Piezo Buzzer 
6. Pliers 
7. Solder 
8. Soldering Wires
9. add materials for second and third milestone

# Building Steps 

1. Make the Arduino blink.<br/>
  a. Download the Arduino software on the website arduino.cc<br/>
  b. Connect the USB cord from a computer to an Arduino. (Adapters may be needed depending on computer model)<br/> 
  c. Open the Arduino software<br/>
  d. Go to the top left of your screen. File → Examples → Basics → Blink. This opens a new Arduino window with the code to make an Arduino board blink<br/> 
  e. Go to the top left of your screen. Tools → Board → Arduino/Genuino Uno. This ensures that the code will go to the Arduino Board<br/> 
  f. Go to the top left of your screen. Tools → Port → (Arduino/Genuino Uno). This also ensures that the code will go to the Arduino Boards<br/> 
  g. Upload the code<br/>
  h. If the Arduino Board is not blinking go to the website. https://support.arduino.cc/hc/en-us<br/>
2. Run ultrasonic sensor<br/> 
  a. Collect materials (Female to male jumper wires, Arduino board, and buzzer)<br/> 
  b. Using the ultrasonic sensor, the Arduino, and the jumper wires:<br/>
      - Connect VCC on the ultrasonic sensor to 5V on the Arduino<br/>
      - Connect the Trig pin on the ultrasonic sensor to pin 2 on the Arduino<br/>
      - Connect the Echo pin on the ultrasonic sensor to pin 3 on the Arduino<br/>
      - Connect the GND on the ultrasonic sensor to the GND on the Arduino\
  c. Using the buzzer, the Arduino, and the jumper wires:<br/>
      - Connect the positive pin on the buzzer to pin - 10 on the Arduino<br/> 
      - Connect the negative pin on the buzzer to pin GND on the Arduino<br/>
  d. Copy and paste the following code to your Arduino application. There are comments in the code for clarification<br/>
```
 // initiallized trigger pin and echo
 // initialized trigger pin to 2 and echo pin to 3 because they are connected to those pins on the arduino 
 // initialized the busser pin and the variable that calculates distance 
  int trigger_pin = 2;
  int echo_pin = 3;
  int buzzer_pin = 10;
  int time;
  int distance;

 // the trigger pin is set as output becasue it sends the ultrasonic wave
 // the  echo pin is set as input because it recieves the ultrasonic wave
void setup() {
  
  Serial.begin (9600);
  pinMode (trigger_pin, OUTPUT);
  pinMode (echo_pin, INPUT);
  pinMode (buzzer_pin, OUTPUT);

}

void loop() {
  // Made the trigger pin and echo pin "HIGH" to send and recieve the ultrasonic wave
  // Added the equation to get the distance
  digitalWrite (trigger_pin, HIGH);
  delayMicroseconds (10);
  digitalWrite (trigger_pin, LOW);
  time = pulseIn (echo_pin, HIGH);
  distance = (time * 0.034) / 2;

  if (distance <= 15) {
    // If statement translates to "if there is an object in a distance of 15 or less the buzzer will go off" 
    Serial.println (" Door Open ");
    Serial.println (" Distance= ");
    Serial.println (distance);
    digitalWrite (buzzer_pin, HIGH);
    delay (500);
  }

  else {
    Serial.println (" Door closed ");
    Serial.print (" Distance = ");
    Serial.println (distance);
    digitalWrite (buzzer_pin, LOW);
    delay (500);
  }

}
```
  k. Run the code. Make sure to save it as well. Use this video to check if your board looks and works the same: https://youtu.be/-ZwjPb01SVY<br/>
3. add steps for second milestone
4. add steps for final milestone

# Reflection
- growth
- self discovery
- next steps
- how engineering effects the world

# Final Milestone
third milestone. 

[![Final Milestone]("add video to markdown of third milestone"){:target="_blank" rel="noopener"}

# Second Milestone
My second milestone is driving my motor. I first built my circuit. I have never worked with a motor driver until now, and I have never used batteries in my circuits until now. The first atleast ten times I ran my circuit my motors did not move, and I was making edits to my code. I learned that my code was not the problem but where I put my pins on my Arduino was the problem. I learned that I should have placed my wires on the PWM pins on my Arduino Uno. PWM pins allow different components of my circuit to run at the same time. 

[![Third Milestone]([![Second Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1625233008/video_to_markdown/images/youtube--A50zeyaOhtw-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/A50zeyaOhtw "Second Milestone")){:target="_blank" rel="noopener"}

# First Milestone
My first milestone is testing my ultrasonic sensor. My first step was to learn about how an ultrasonic sensor functions. The sensor emmits ultrasonic sound waves to an object and times the emission and reception of the wave; therefore, the sensor is able to derive the distance from the sensor to the object. After, I was able to code my arduino. My last step was assembly. I connected wires from by sensor to my arduino and the same for my buzzer. 

[![First Milestone][![First Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1624634012/video_to_markdown/images/youtube---ZwjPb01SVY-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/-ZwjPb01SVY "First Milestone") {:target="_blank" rel="noopener"}
